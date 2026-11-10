# Vérification de compatibilité — Prototype v1

Revue du 10/11/2026 de la commande DigiKey + batteries Accu-Run ([ACHATS.md](ACHATS.md)). Sources : fiches produit Adafruit (6091), Pololu (U3V40F5), catalogue Keystone (1042), schéma KiCad Olimex ESP32-S3-DevKit-LiPo Rev B, fiches DigiKey.

**Verdict : tout est compatible**, à condition de respecter les 4 règles en bas de page (charge, courant, câblage batterie, broches).

## Chaîne d'alimentation

```
USB-C ─► Adafruit 6091 (BQ25185) ─► LOAD ≤ 4,5 V ─► interrupteur ─► Pololu U3V40F5 ─► 5 V ─┬─► ampli MAX98357A
            │                                                                              ├─► ruban LED + 74AHCT125
            └─► BATT ◄─► 2 × Ansmann 18650 en parallèle (Keystone 1042)                    └─► Olimex (broche +5V) ─► 3,3 V ─► écran, encodeur, boutons
```

| Liaison | Vérification | État |
|---|---|---|
| Batteries ↔ chargeur | 6091 prévu pour Li-ion 3,7 V / 4,2 V max ; cellules Ansmann 3,6–3,7 V / 4,2 V. | ✅ |
| Batteries ↔ support | Keystone 1042 : « accepte les cellules avec ou sans circuit de protection » ; retrait sans outil (utile pour le règlement batteries 2027). | ✅ |
| Deux cellules en parallèle | Même modèle, même lot, protégées. Les charger toutes les deux à 100 % **avant** de les relier. | ✅ (précaution) |
| Chargeur → convertisseur 5 V | La sortie LOAD du 6091 ne dépasse jamais 4,5 V ; le Pololu exige une entrée ≤ 5 V et ≤ sa sortie. | ✅ |
| Convertisseur 5 V → charges | Pololu : jusqu'à ~4 A en entrée, sortie ≈ 2,5 à 2,8 A à 3,6 V batterie. Besoin estimé en pointe : ~1,9 A sur le 5 V. | ✅ |
| 5 V → Olimex | Le schéma Olimex a des diodes Schottky 1N5819 sur les entrées 5 V : on peut alimenter par la broche +5V **et** brancher l'USB pour programmer sans conflit. Régulateur 3,3 V intégré (SY8089). | ✅ |
| Chargeur intégré Olimex (BL4054) | Inutilisé : ne **rien** brancher sur le connecteur batterie de l'Olimex. | ✅ (à respecter) |

## Signaux

| Liaison | Vérification | État |
|---|---|---|
| ESP32-S3 → ampli MAX98357A | I2S en 3,3 V accepté, pas de MCLK nécessaire. Ampli en 5 V : 3,2 W sur 4 Ω. | ✅ |
| Ampli → haut-parleur Visaton FR 7 | 4 Ω, 5 W nominal (10 W max) > 3,2 W de l'ampli : le haut-parleur ne sera jamais surchargé. | ✅ |
| ESP32-S3 → écran Adafruit 4311 | ST7789 en SPI, logique 3,3 V. Le lecteur microSD de l'écran partage le même bus SPI avec sa propre broche CS. | ✅ |
| ESP32-S3 → ruban LED (WS2813B) | Les LED en 5 V attendent un signal ≥ 3,5 V ; le **74AHCT125** alimenté en 5 V convertit le 3,3 V de l'ESP32. Résistance 330 Ω en série, condensateur 1000 µF en tête de ruban. | ✅ |
| Encodeur Adafruit 377, boutons 1119 | Contacts simples vers la masse, résistances de rappel internes de l'ESP32. | ✅ |
| Mesure batterie | Pont 100 kΩ / 100 kΩ : 4,2 V → 2,1 V, dans la plage du convertisseur analogique de l'ESP32-S3. | ✅ |
| Logiciel | ESP32-audioI2S (webradio + carte SD, PSRAM requise : ✅ 8 Mo), LovyanGFX (ST7789), FastLED (WS2813). | ✅ |

## ⚠️ Points d'attention

1. **Minuterie de charge de 6 h du 6091.** Le BQ25185 coupe la charge au bout de 6 h, non modifiable. À 1 A, 7 000 mAh demandent environ 7 h : la charge s'arrêterait vers 85-90 %. Et si la carte est réglée à 500 mA (la fiche Adafruit et son guide se contredisent sur la valeur par défaut), elle s'arrêterait vers 45 %.
   → **Régler le cavalier sur 1 A** et **relier la broche CE du 6091 à une broche de l'ESP32**. Le firmware relance la charge (impulsion sur CE) au bout de 5 h 30 si la batterie n'est pas pleine.

2. **Courant de pointe côté batterie.** Volume à fond + LED en blanc + Wi-Fi : environ 2,5 à 3 A tirés sur la batterie. Or le 6091 accepte des pointes de 3 A vers sa sortie.
   → Dans le firmware : **limiter les LED à environ 400 mA** (FastLED `setMaxPowerInVoltsAndMilliamps(5, 400)`) et éviter les pics de volume quand la batterie est faible.

3. **Câblage de la batterie.** Le connecteur JST-PH du 6091 est donné pour environ 2 A.
   → **Souder des fils de 22 AWG** directement sur les pastilles BATT du 6091 et sur les languettes des supports Keystone (qui sont des languettes à souder, CMS).

4. **Broches de l'ESP32-S3 à ne pas utiliser.**
   - GPIO 35, 36 et 37 (prises par la PSRAM octale du module N8R8) ;
   - GPIO 19 et 20 (USB natif) ;
   - GPIO 0, 3, 45 et 46 (broches de démarrage), sauf pour un bouton qui est au repos au démarrage.

   Il faut environ 20 broches : l'Olimex en sort largement assez (2 rangées de 22).

## À vérifier à la réception

- **Ruban Seeed 104990303 :** la fiche du fabricant n'a pas pu être lue. Il s'agit probablement de la version « Grove WS2813 étanche » (gaine silicone, connecteur Grove). Si c'est le cas, couper le connecteur et souder. La gaine diffuse déjà un peu la lumière, mais prend plus de place derrière le Diffuseur.
- **Valeur réelle du courant de charge** sur la carte 6091 (cavalier IS).
- **Longueur exacte des Ansmann** dans le Keystone 1042 : compatibles d'après le catalogue, à confirmer à l'essai.
