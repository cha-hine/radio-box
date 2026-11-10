# Liste d'achat — Prototype v1 (livraison à La Réunion)

Relevé du 10/11/2026, à partir de [BOM.md](BOM.md). Prix et stocks relevés sur gotronic.fr ce jour, à revérifier au moment de commander.

> **Prototype ≠ produit certifié.** Ces modules servent à valider le fonctionnement. Le produit vendu (et certifié CE) utilisera un circuit imprimé sur mesure avec des composants traçables : voir [docs/certification-ce.md](../docs/certification-ce.md). Pour le prototype, on privilégie néanmoins des modules de marque (Espressif, Olimex, DFRobot, Adafruit) plutôt que des clones : mêmes puces que la version finale, fiches techniques fiables.

## Où commander

| Source | Livre à La Réunion ? | Remarques |
|---|---|---|
| **Gotronic** (gotronic.fr) | Oui : « Colissimo International ou Outre-Mer », 5 à 7 jours pour les DOM/TOM, prix calculé selon le poids (affiché au panier) | Modules de marque, traçables. La plupart des articles sont disponibles. Le traitement de la TVA pour les DOM n'est pas précisé dans les CGV : vérifier au panier si les prix passent en HT. |
| **DigiKey** (digikey.fr) | **Oui** (confirmé au panier), livraison express | Pièces de marque, traçables (logique CE). ESP32-S3 et ruban NeoPixel en rupture le 10/11. Voir le comparatif. |
| **AliExpress** | En général oui, 2 à 4 semaines | Pour les quelques articles absents chez Gotronic. Vérifier sur chaque annonce que « La Réunion » est proposée. |
| **Sur place (974)** | — | Batteries 18650. |

> À l'arrivée à La Réunion : TVA locale (8,5 %) et éventuellement octroi de mer, souvent perçus par le transporteur à la livraison.

## Panier Gotronic

| BOM | Article Gotronic | Code | Prix TTC | Stock (10/11) | Qté | Remarques |
|---|---|---|---|---|---|---|
| 1 | [Carte ESP32-S3-DevKit-LiPo (Olimex)](https://www.gotronic.fr/art-carte-esp32-s3-devkit-lipo-49803.htm) | 39664 | 9,90 € | Rupture, réappro. estimé le 12/11/2026 | 2 | Module **ESP32-S3-WROOM-1-N8R8** (8 Mo flash, 8 Mo PSRAM) : suffisant. Variante en stock : [DevKit-LiPo-EA](https://www.gotronic.fr/art-esp32-s3-devkit-lipo-ea-49804.htm) (code 39665, 12,60 €, antenne externe). La DevKitC-1 officielle Espressif ([code 34324](https://www.gotronic.fr/art-carte-esp32-s3-devkitc-1-s3-8mb--37653.htm), 23,90 €) est en rupture. |
| 2 | [Module ampli audio I2S DFR0954](https://www.gotronic.fr/art-module-ampli-audio-i2s-dfr0954-35876.htm) | 37934 | 6,50 € | En stock (8) | 2 | MAX98357A de DFRobot. Alternative : [SparkFun DEV-14809](https://www.gotronic.fr/art-module-ampli-audio-i2s-dev-14809-35386.htm) (code 37807, 7,80 €). |
| 4 + 8 | [Module afficheur IPS TFT 2" ADA4311 (Adafruit)](https://www.gotronic.fr/art-module-afficheur-ips-tft-2-ada4311-30797.htm) | 36519 | 24,95 € | En stock | 1 | ST7789, 320×240, rétroéclairage PWM, **lecteur microSD intégré** : remplace le module microSD séparé. |
| 5 | [Module encodeur rotatif GT055 + bouton-poussoir](https://www.gotronic.fr/art-module-encodeur-rotatif-gt055-28502.htm) | 36032 | 2,50 € | En stock | 2 | Livré sans écrou ; prévoir un bouton de molette (axe à vérifier). |
| 6 | [Assortiment de 25 boutons-poussoirs](https://www.gotronic.fr/art-boite-de-25-bp-couleur-48902.htm) | 07139 | 7,90 € | En stock (51) | 1 | Ronds, 4 picots, capuchons 5 couleurs. Taille non indiquée sur la fiche. |
| 7 | [Interrupteur à bascule DS12LR](https://www.gotronic.fr/art-interrupteur-ds12lr-4437.htm) | 07395 | 2,15 € | En stock (22) | 1 | Rond, perçage 20,5 mm, LED rouge (résistance de limitation nécessaire). |
| 10 | [Ruban RGB 2 m – 120 LED WS2812 (blanc)](https://www.gotronic.fr/art-ruban-rgb-2-m-120-leds-36115.htm) | 03942 | 19,60 € | En stock | 1 | Adressable, sécable entre chaque LED, adhésif. |
| 11 | [Convertisseur de niveaux 4 canaux KY051](https://www.gotronic.fr/art-convertisseur-de-niveaux-4-canaux-ky051-29156.htm) | 36266 | 4,80 € | En stock | 1 | Remplace le 74AHCT125 (absent du catalogue). Vérifier sur la fiche technique qu'il tient au moins 1 MHz (signal des LED à 800 kHz). |
| 15 | [Coupleur d'accu BH18650-1](https://www.gotronic.fr/art-coupleur-d-accu-bh18650-1-5713.htm) | 09588 | 1,80 € | En stock | 2 | Deux supports simples câblés **en parallèle** : plus sûr qu'un support double, souvent câblé en série. |
| 16 | [Module de protection BMS 1S](https://www.gotronic.fr/art-protection-batterie-1s-48852.htm) | 39401 | 3,60 € | En stock (43) | 1 | 3,7 V / 5 A. |
| 3 | [Haut-parleur 77 mm LS01-5](https://www.gotronic.fr/art-haut-parleur-77-mm-ls01-5-28404.htm) | 28714 | 6,80 € | En stock (33) | 1 | ⚠️ **8 Ω** : environ 1,8 W avec le MAX98357A au lieu de 3,2 W. Bon pour tester ; un 4 Ω (AliExpress) sera plus fort. Gotronic n'a pas de 4 Ω de cette taille. |
| 19 | [PETG 1,75 mm 750 g blanc signal](https://www.gotronic.fr/art-bobine-de-fil-petg-1-75-mm-petg175bc-39210.htm) | 45560 | 24,40 € | En stock | 1 | Coque du prototype (voir la remarque CE sur la matière). |
| 20 | [PETG 1,75 mm 750 g transparent](https://www.gotronic.fr/art-bobine-de-fil-petg-1-75-mm-petg175tr-39211.htm) | 45564 | 24,40 € | En stock | 1 | Diffuseur. |

**Sous-total Gotronic : ~145 €** (dont ~49 € de filament), hors frais de port outre-mer.

### Charge et 5 V : pas de bon équivalent chez Gotronic

Gotronic n'a pas de module « charge + 5 V ≥ 2 A + lecture pendant la charge » comme l'IP5306. Ce qui existe :

- [Chargeur Li-Ion 18650 USB Type-C GT065](https://www.gotronic.fr/art-chargeur-accu-li-usb-c-47569.htm) (code 39139, 2,90 €) + [Booster 5 V U1V11F5 (Pololu)](https://www.gotronic.fr/art-booster-5-v-u1v11f5-21751.htm) (code 32794, 8,80 €) : **1,2 A maximum**, trop juste pour l'ampli, les LED et le Wi-Fi ensemble.
- [Module UPS 5 V pour batterie 18650](https://www.gotronic.fr/art-module-ups-5v-1-x-18650-48848.htm) (code 39396, 5,50 €) : la fiche ne donne ni le courant de charge ni le courant de sortie.

→ Pour le prototype, prendre **l'IP5306 sur AliExpress** (ci-dessous).

## Complément AliExpress

| BOM | Rechercher | Qté | À vérifier sur l'annonce |
|---|---|---|---|
| 17 | `IP5306 type-c power bank module` | 2 | Charge par USB-C, sortie 5 V 2,1 à 2,4 A. De préférence version **I2C** (« IP5306_I2C »). |
| 3 | `full range speaker 2.5 inch 4 ohm 5W` | 2 | **4 Ω**, 5 W, 57 à 66 mm (version plus puissante que le 8 Ω de Gotronic). |
| 21 | `M3 heat set insert brass` | 1 lot | M3 × 5,7 mm environ (absents chez Gotronic). |
| 22 | `M3 socket head screw kit` | 1 lot | Kit M3 de 6 à 12 mm. |
| 23 | `silicone feet pads 10mm` | 1 lot | Patins (absents chez Gotronic). |
| 5 | `potentiometer knob 6mm` | 2 | Bouton de molette : axe à adapter à l'encodeur GT055. |
| 25–29 | `perfboard 7x9`, `JST PH 2.0 kit`, `silicone wire 22AWG 26AWG`, `heat shrink kit`, `2.54mm female header` | 1 de chaque | Consommables (aussi trouvables chez Gotronic par catégorie). |
| 12–13, 18 | Résistances 330 Ω et 100 kΩ, condensateur 1000 µF 10 V | 1 lot chacun | Kits d'assortiment. |

## Comparatif DigiKey / Mouser / Gotronic

Relevé du **10/11/2026 dans ton navigateur** (digikey.fr et mouser.fr, prix à l'unité pour une quantité de 1). Gotronic : relevé direct sur gotronic.fr le même jour.

- **DigiKey** livre à La Réunion (confirmé par toi au panier). Prix **HT** : la page affiche « prix unitaire sans TVA ».
- **Mouser** : La Réunion ne figure pas dans la liste « Mouser dans le monde » (la France y passe par « Mouser Europe »). La livraison en 974 reste **à vérifier au panier**. Prix en € affichés sur mouser.fr, a priori HT.
- **Gotronic** : prix TTC, livraison Colissimo Outre-Mer.

| BOM | Pièce | DigiKey (€ HT · stock) | Mouser (€ · stock) | Gotronic (€ TTC · stock) | Remarque |
|---|---|---|---|---|---|
| 1 | Carte ESP32-S3 avec PSRAM (×2) | DevKitC-1 N8R8 / 1U-N8R8 / N32R16V : **toutes en rupture**. **Olimex ESP32-S3-DevKit-LiPo (N8R8) : 8,18 · 250** | **ESP32-S3-DevKitC-1-N16R8 : 11,39 · 62** (504 attendus le 07/12) · N32R16V 13,67 · 580 | Olimex DevKit-LiPo 9,90 (réappro. estimé 12/11) · EA 12,60 | L'Olimex utilise le même module WROOM-1-N8R8, et intègre un chargeur LiPo. |
| 2 | Ampli MAX98357A Adafruit 3006 (×2) | **5,28 · 3 896** | 5,12 · 745 | DFR0954 6,50 · 8 | — |
| 3 | Haut-parleur Visaton FR 7 – 4 Ω, 66 mm, 5 W | **7,63 · 502** | Visaton 2015 (6,5 cm large bande) : 8,81 · sur commande | pas de 4 Ω (8 Ω : 6,80) | DigiKey est le seul à l'avoir en stock. |
| 4 + 8 | Écran 2" ST7789 + microSD Adafruit 4311 | 17,71 · 481 | **17,03 · 365** | 24,95 · en stock | — |
| 5 | Encodeur + molette Adafruit 377 (×2) | 3,99 · 87 | **3,87 · 72** | GT055 2,50 (sans molette) | — |
| 6 | Boutons 12 mm Adafruit 1119 (lot de 10) | 2,22 · 349 | 2,15 · 6 (30 attendus le 13/11) | Assortiment 25 BP 7,90 | — |
| 6b | Capuchons Adafruit 1009 (15 boutons colorés) | non trouvé | **5,12 · 13** | (inclus dans l'assortiment Gotronic) | — |
| 7 | Interrupteur marche/arrêt | ZF KRE2ANA1BBD 2,25 · 4 722 | non relevé | DS12LR 2,15 · en stock | — |
| 10 | Ruban de LED adressables 60 LED/m | 2537 RGB 2 m : **rupture**. En stock : **4689 RGBW 1 m, 26,59 · 32** | 2846 RGBW blanc : 23,18 · 62 · 1138 (4 m) : 85,83 sur commande | **Ruban WS2812 2 m 03942 : 19,60 · en stock** | RGBW = une LED blanche en plus : compatible, mais à déclarer dans le code. |
| 11 | Décaleur de niveau TI SN74AHCT125N (×2) | 0,84 · 497 | **0,843 · 2 858** | absent (KY051 4,80) | — |
| 17 | Charge + 5 V Adafruit PowerBoost 1000C | 17,71 · **2** | 17,16 · 11 | absent | Sortie 1 A maximum (voir plus haut). |
| 15 | Support 18650 Keystone 1042, UL 94 V-0 (×2) | 6,11 · en stock | **5,25 · 17 599** | BH18650-1 1,80 | — |
| 16 | Protection batterie 1S | non trouvé | non relevé | **3,60 · 43** | — |
| 21 | Inserts M3 laiton | non relevé | **Spirol IUTB-M3 : 0,318 pièce (0,226 dès 10) · 57 283** | absent | Inserts pour thermo-insertion, compatibles avec l'impression 3D. |
| 23 | Patins 3M Bumpon SJ5302 | ~0,11 pièce (par lot) | 0,099 pièce par feuille de 144 · 196 128 | absent | Une feuille de 144 suffit pour des années. |
| 9 | Carte microSD 32 Go | 42 à 140 € (cartes industrielles) | non relevé | — | **À acheter sur place** (~6 €). |
| 19–20 | Filament PETG | — | — | 24,40 la bobine | Ou boutique Bambu Lab. |

### Paniers comparés (pièces électroniques, hors microSD et filament)

| | DigiKey | Mouser |
|---|---|---|
| Total estimé | **≈ 123 € HT** | **≈ 131 €** (haut-parleur compris) |
| Manque | Protection 1S, inserts | Protection 1S ; haut-parleur seulement sur commande |
| Livraison à La Réunion | ✅ confirmée | ❓ à vérifier |
| Seuil de livraison offerte | 75 € (affiché sur le site) | non relevé |

### Recommandation

**Tout chez DigiKey** en une commande express :
- Olimex ESP32-S3-DevKit-LiPo ×2, Adafruit 3006 ×2, Visaton FR 7 – 4 Ω, Adafruit 4311, Adafruit 377 ×2, Adafruit 1119, interrupteur ZF KRE2ANA1BBD, ruban Adafruit 4689 (RGBW), SN74AHCT125N ×2, PowerBoost 1000C (plus que 2 en stock), Keystone 1042 ×2 + patins.
- **Reste :** la carte de protection 1S (Gotronic, ou cellules protégées), les inserts M3 (AliExpress / Gotronic par catégorie, ou Mouser) et, sur place, les batteries et la carte microSD.

## Sur place (974)

| BOM | Article | Qté | Remarques |
|---|---|---|---|
| 14 | Cellules **18650 3000 à 3500 mAh**, Samsung 35E / 30Q, LG MJ1, Molicel P28A… | 2 | **Même modèle, même lot**, cellules **non protégées à tête plate** (65 mm, pour les coupleurs BH18650-1). Méfiance au-delà de 3500 mAh (contrefaçons). Gotronic vend des 18650 mais La Poste n'expédie pas de batteries seules. |
| 9 | Carte microSD 32 Go de marque (SanDisk, Samsung) | 1 | Grande surface ou magasin d'informatique. |
