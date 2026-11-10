# Liste d'achat — Prototype v1 (livraison à La Réunion)

Relevé du 10/11/2026, à partir de [BOM.md](BOM.md). Prix et stocks à revérifier au moment de commander.

## Où commander

| Source | Livre à La Réunion ? | Remarques |
|---|---|---|
| **AliExpress** | En général oui (AliExpress Standard Shipping), 2 à 4 semaines | Le moins cher, et le seul endroit où l'on trouve **tous** les modules. Vérifier sur chaque annonce que « La Réunion » est proposée à la livraison. |
| **Gotronic** (gotronic.fr) | Oui : « Colissimo International ou Outre-Mer », 5 à 7 jours pour les DOM/TOM, prix calculé selon le poids (affiché seulement au panier) | Catalogue limité pour ce projet (pas de DevKitC-1, pas de MAX98357A, pas d'écran ST7789 trouvés). Le traitement de la TVA pour les DOM n'est pas précisé dans les CGV : vérifier au panier si les prix passent en HT. |
| **Sur place (974)** | — | **Batteries 18650** (boutiques de vape), et éventuellement visserie et patins en quincaillerie. |

> À l'arrivée à La Réunion : TVA locale (8,5 %) et éventuellement octroi de mer, souvent perçus par le transporteur à la livraison.

## Panier AliExpress (tout sauf les batteries)

Les annonces AliExpress changent sans cesse : voici les **termes de recherche exacts** et ce qu'il faut vérifier sur l'annonce.

| # | Rechercher | Qté | À vérifier sur l'annonce |
|---|---|---|---|
| 1 | `ESP32-S3-DevKitC-1 N16R8` | 2 | Bien **N16R8** (16 Mo flash / 8 Mo PSRAM), **pas N16R8V** (version 1,8 V). Avec broches déjà soudées si possible. 2 exemplaires : un de rechange en cas de fausse manœuvre. |
| 2 | `MAX98357A I2S amplifier module` | 2 | Module violet ou noir de 18×18 mm, bornier pour le haut-parleur. |
| 3 | `2.0 inch IPS TFT ST7789 240x320 SPI` | 1 | Contrôleur **ST7789**, résolution **240×320**, broche **BL** présente. |
| 4 | `EC11 rotary encoder module with knob` | 2 | Avec bouton poussoir intégré et capuchon de molette. |
| 5 | `12x12 tactile push button with cap` | 1 lot | Lot de 10 à 25 avec capuchons. |
| 6 | `KCD1 rocker switch` ou `SS12F15 slide switch` | 1 lot | Interrupteur marche/arrêt, ≥ 3 A. |
| 7 | `micro SD card module SPI 3.3V` | 2 | De préférence **sans régulateur 5 V** (module « TF card » minimaliste). |
| 8 | `WS2812B LED strip 60 leds/m 5V IP30` | 1 m | Version **IP30** (sans gaine silicone), plus fine et plus facile à coller derrière le Diffuseur. |
| 9 | `74AHCT125` (DIP-14) | 5 | Format **DIP** pour la plaque à souder. |
| 10 | `IP5306 type-c power bank module` | 2 | Charge par USB-C, sortie 5 V 2,1 à 2,4 A. Idéalement version **I2C** (dite « IP5306_I2C »), sinon prévoir de contourner la coupure automatique à faible charge. |
| 11 | `1S lithium protection board DW01 8205A` | 1 lot | Carte de protection 1 cellule. |
| 12 | `18650 battery holder 2 slot parallel` | 2 | Support **2 cellules en parallèle** (et non en série). |
| 13 | `full range speaker 2.5 inch 4 ohm 5W` (ou `66mm 4ohm 5W`) | 2 | **4 Ω** obligatoire, 5 W, 57 à 66 mm. |
| 14 | `M3 heat set insert brass` | 1 lot | Pour l'impression 3D (M3 × 5,7 mm environ). |
| 15 | `M3 socket head screw kit` | 1 lot | Kit M3 de 6 à 12 mm. |
| 16 | `silicone feet pads 10mm` | 1 lot | Patins. |
| 17 | Résistances 330 Ω et 100 kΩ, condensateurs 1000 µF 10 V | 1 lot chacun | Kits d'assortiment. |
| 18 | `perfboard 7x9`, `JST PH 2.0 kit`, `silicone wire 22AWG 26AWG`, `heat shrink kit`, `2.54mm female header` | 1 de chaque | Consommables. |
| 19 | `micro SD 32GB` | 1 | Marque connue (SanDisk, Samsung) ; les cartes premier prix sur AliExpress sont souvent fausses. |

## Chez Gotronic (optionnel)

Rien d'indispensable : les modules clés n'y sont pas. Utile seulement en dépannage rapide (5 à 7 jours au lieu de 2 à 4 semaines) :

- Haut-parleur + cordon jack 8 Ω / 3 W, code 05523, 12,80 € TTC — ⚠️ **8 Ω, donc moins puissant**, mais utile pour tester tout de suite.
- Le reste du catalogue (boutons, visserie, composants) est à parcourir par catégorie, la recherche du site n'étant pas accessible automatiquement.

## Sur place (974)

| # | Article | Qté | Remarques |
|---|---|---|---|
| 1 | Cellules **18650 3000 à 3500 mAh**, Samsung 35E / 30Q, LG MJ1, Molicel P28A… | 2 | **Même modèle, même lot**, cellules **non protégées à tête plate** (elles tiennent dans les supports standard). Méfiance envers les cellules annoncées à plus de 3500 mAh : ce sont des contrefaçons. |

## Filament

PETG couleur + PETG blanc translucide (natural) : à prendre sur la boutique Bambu Lab, chez un revendeur local, ou sur AliExpress. Les conditions de livraison à La Réunion n'ont pas été vérifiées.
