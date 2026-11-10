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

Relevé du 10/11/2026. **DigiKey livre bien à La Réunion** (confirmé par toi au panier). Pour Mouser, la livraison à La Réunion n'est pas confirmée : refaire le même test de panier avec une adresse 974.

**Fiabilité des prix :**
- **DigiKey** : prix HT lus sur digikey.fr, mais extraits automatiquement d'un résumé de page. À recontrôler au panier.
- **Mouser** : le site bloque les accès automatiques. Les prix viennent d'aperçus de moteur de recherche, parfois d'un autre site Mouser européen (DE, LT), à une date inconnue.
- **Gotronic** : prix TTC lus directement sur gotronic.fr.

Pour La Réunion, raisonner en HT : la TVA locale de 8,5 % s'applique à l'arrivée.

| BOM | Pièce | DigiKey (€ HT, stock) | Mouser (€, stock) | Gotronic (€ TTC, stock) | Alternative / remarque |
|---|---|---|---|---|---|
| 1 | Espressif ESP32-S3-DevKitC-1-N8R8 (×2) | 13,32 — **rupture, 8 semaines** | **11,44 — 743 en stock** (mouser.fr) | Olimex DevKit-LiPo N8R8 9,90 (réappro. estimé 12/11) ; version EA 12,60 en stock | Chez DigiKey : vérifier la variante ESP32-S3-DEVKITC-1U-N8R8 (antenne externe). |
| 2 | Adafruit 3006 MAX98357A (×2) | 5,14 (prix du site NL, FR non lu) — stock non lu | 5,12 (site DE) — 403 en stock | DFRobot DFR0954 6,50 — en stock (8) | Équivalent : SparkFun DEV-14809 (Gotronic 7,80). |
| 3 | Visaton FR 7 – 4 Ω, 66 mm, 5 W | **7,63 — 502 en stock** | non trouvé | pas de 4 Ω (LS01-5 en 8 Ω, 6,80) | Autre 4 Ω 5 W chez DigiKey : Ole Wolff OWS-525229TA-4 (52 mm). |
| 4 + 8 | Adafruit 4311 écran 2" + microSD | **17,71 — 481 en stock** | non trouvé | 24,95 — en stock | — |
| 5 | Adafruit 377 encodeur + molette (×2) | 3,99 — 87 en stock | non vérifié | GT055 2,50 (sans molette) | — |
| 6 | Boutons 12 mm : Adafruit 1119 (lot de 10) | 2,22 — 349 en stock | non vérifié | Assortiment 25 BP 7,90 | Capuchons Adafruit 1009 : non trouvés chez DigiKey. |
| 7 | Interrupteur marche/arrêt | ZF KRE2ANA1BBD (bascule, 10 A DC) 2,25 — 4 722 en stock | non vérifié | DS12LR 2,15 — en stock | — |
| 9 | Carte microSD 32 Go | 42 à 140 € (cartes industrielles) | non vérifié | — | **À acheter sur place** (SanDisk / Samsung grand public, ~6 €). |
| 10 | Ruban NeoPixel 60 LED/m (Adafruit 2537, 2 m) | 17,71 — **rupture, 18 semaines** | Adafruit 1138 (bobine de 4 m) : stock variable, prix non lu | **Ruban WS2812 2 m 03942 : 19,60 — en stock** | Chez DigiKey : regarder les autres rubans NeoPixel d'Adafruit (2968, 4914…), stock non vérifié. |
| 11 | TI SN74AHCT125N (×2) | 0,84 — 497 (vendeur marketplace) | non vérifié | absent (KY051 4,80 en remplacement) | — |
| 17 | Adafruit 2465 PowerBoost 1000C | ~19,95 $ (agrégateur FindChips, date inconnue) | 17,16 (site LT) — 135 en stock | absent | Sortie limitée à 1 A : ampli branché directement sur la batterie et LED plafonnées. |
| 15 | Keystone 1042 support 18650 V-0 (×2) | **6,11 pièce — 7 020 en stock** | non vérifié | BH18650-1 1,80 pièce | Le Keystone est ignifugé (UL 94 V-0), utile pour la CE. |
| 16 | Protection 1S | non trouvé | non trouvé | **3,60 — en stock** | — |
| 21 | Inserts M3 | Adafruit 4239 / PTSolns 4255 : prix non lus | non vérifié | absent | AliExpress en secours. |
| 23 | Patins 3M Bumpon SJ5302 | ~0,11 pièce (prix par lot) — en stock | non vérifié | absent | — |
| 19–20 | Filament PETG | — | — | 24,40 la bobine | Ou boutique Bambu Lab. |

### Bilan

- **DigiKey seul** couvre presque tout, pour environ **125 € HT**, au-dessus du seuil de 75 € de livraison offerte (si ce seuil s'applique aux DOM). Deux trous : **l'ESP32-S3 et le ruban de LED sont en rupture**.
- **Mouser** a l'ESP32-S3 en stock (743), mais la livraison à La Réunion et la plupart des prix restent à vérifier.
- **Pour éviter de multiplier les commandes :** tout chez DigiKey, sauf l'ESP32-S3 et le ruban de LED, à remplacer par une variante en stock chez DigiKey si elle existe, sinon à prendre chez Gotronic (Olimex N8R8 + ruban 03942). La carte de protection 1S est aussi chez Gotronic.

## Sur place (974)

| BOM | Article | Qté | Remarques |
|---|---|---|---|
| 14 | Cellules **18650 3000 à 3500 mAh**, Samsung 35E / 30Q, LG MJ1, Molicel P28A… | 2 | **Même modèle, même lot**, cellules **non protégées à tête plate** (65 mm, pour les coupleurs BH18650-1). Méfiance au-delà de 3500 mAh (contrefaçons). Gotronic vend des 18650 mais La Poste n'expédie pas de batteries seules. |
| 9 | Carte microSD 32 Go de marque (SanDisk, Samsung) | 1 | Grande surface ou magasin d'informatique. |
