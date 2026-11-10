# Liste d'achat — Prototype v1 (livraison à La Réunion)

Relevé du 10/11/2026 dans le navigateur (digikey.fr, mouser.fr, accu-run.fr), plus le relevé direct de gotronic.fr fait le même jour. Repart de [BOM.md](BOM.md). Prix et stocks à revérifier au moment de payer.

> **Prototype ≠ produit certifié.** Ces modules servent à valider le fonctionnement. Le produit vendu (certifié CE) utilisera un circuit imprimé sur mesure avec des composants traçables : voir [docs/certification-ce.md](../docs/certification-ce.md). Pour le prototype, on prend quand même des modules **de marque** (Espressif, Olimex, Adafruit, Visaton, Keystone, TI, Ansmann) : mêmes puces que la version finale, fiches techniques et certificats disponibles.

---

## ✅ Décision finale

**Une commande DigiKey (express, livraison gratuite) + 2 batteries chez Accu-Run (La Réunion) + quelques petites fournitures.**

### 1. DigiKey — commande principale

Panier rempli le 10/11/2026, chaque ligne marquée avec la référence client `radio-box`. Prix HT, quantité 1.

| Qté | Pièce | N° DigiKey | Prix unit. HT | Total HT |
|---|---|---|---|---|
| 2 | Olimex **ESP32-S3-DevKit-LiPo** (module WROOM-1-N8R8) | 1188-ESP32-S3-DEVKIT-LIPO-ND | 8,18 € | 16,36 € |
| 2 | Adafruit **3006**, ampli I2S MAX98357A | 1528-1696-ND | 5,28 € | 10,56 € |
| 1 | Visaton **FR 7 – 4 Ω**, haut-parleur 66 mm 5 W | 2056-FR7-4OHM-ND | 7,63 € | 7,63 € |
| 1 | Adafruit **4311**, écran 2" ST7789 + lecteur microSD | 1528-4311-ND | 17,71 € | 17,71 € |
| 2 | Adafruit **377**, encodeur rotatif + molette | 1528-2438-ND | 3,99 € | 7,98 € |
| 1 | Adafruit **1119**, 10 boutons tactiles 12 mm | 1528-1119-ND | 2,22 € | 2,22 € |
| 1 | ZF **KRE2ANA1BBD**, interrupteur à bascule | CH932-ND | 2,25 € | 2,25 € |
| 1 | Adafruit **4689**, ruban NeoPixel **RGBW** 60 LED, 1 m | 1528-4689-ND | 26,59 € | 26,59 € |
| 2 | TI **SN74AHCT125N**, décaleur de niveau (DIP-14) | 296-4655-5-ND | 0,84 € | 1,68 € |
| 2 | Keystone **1042**, support 18650 (UL 94 V-0) | 36-1042-ND | 6,11 € | 12,22 € |
| 10 | Stackpole CF14JT330R, résistance 330 Ω | CF14JT330RCT-ND | 0,024 € | 0,24 € |
| 10 | Stackpole CF14JT100K, résistance 100 kΩ | CF14JT100KCT-ND | 0,024 € | 0,24 € |
| 2 | Nichicon UVR1A102MPD, condensateur 1000 µF 10 V | 493-1025-ND | 0,55 € | 1,10 € |
| 1 | **Charge + 5 V** : voir ci-dessous | | | ≈ 15 € |
| | | | **Total** | **≈ 122 € HT** |

**⚠️ Charge + 5 V : remplacer le PowerBoost.** L'Adafruit 2465 PowerBoost 1000C (1528-1349-ND, 17,71 €), encore dans le panier, est passé en « articles différés » (réassort annoncé le 21/01/2027). Décision : le remplacer par la paire suivante, en stock et plus puissante :

| Qté | Pièce | N° DigiKey | Prix HT | Stock |
|---|---|---|---|---|
| 1 | Adafruit **6091**, chargeur BQ25185 (lecture pendant la charge) | 1528-6091-ND | 6,17 € | 382 |
| 1 | Pololu **U3V40F5**, convertisseur 5 V jusqu'à 3,5 A (entrée 1,3 à 5 V) | 2183-4012-ND | 8,83 € | 304 |

Le Pololu est un **produit marketplace**, expédié par Pololu : des frais de port séparés sont possibles, et la livraison à La Réunion est à vérifier au panier. Ses 3,5 A suffisent pour l'ampli, les LED et le Wi-Fi en même temps, contre 1 A pour le PowerBoost.

> Le panier DigiKey contient aussi un clavier Raspberry Pi (2648-SC0197-ND, 15,09 €) qui n'appartient pas au projet.
> La TVA affichée au panier est celle de la métropole (20 %). Pour La Réunion, regarder ce que donne l'adresse 974 au paiement.

### 2. Accu-Run (La Réunion) — batteries

| Qté | Pièce | Prix TTC | Remarques |
|---|---|---|---|
| 2 | [Ansmann Li-ion 18650, 3500 mAh (min. 3350), 12,6 Wh, **protégée**](https://www.accu-run.fr/piles/97-accumulateur-ansmann-lithium-18650-37v-3500mah-4013674118564.html) | 29,00 € (58 € les 2) | « Disponible » ; livraison en 48 à 72 h. |

- **Le circuit de protection intégré** (surcharge, court-circuit, décharge profonde) **remplace la carte de protection 1S** : plus rien à commander chez Gotronic pour l'électronique.
- Marque connue et traçable : bon point pour obtenir les certificats UN 38.3 / IEC 62133 lors de la certification CE.
- ⚠️ **Longueur** : une cellule protégée mesure environ **3 à 4 mm de plus** qu'une 18650 standard de 65 mm. Vérifier qu'elle rentre dans le Keystone 1042 (fiche technique ou essai). Sinon, le support sera intégré au boîtier imprimé en 3D.

### 3. Petites fournitures (hors DigiKey)

| Pièce | Où | Remarques |
|---|---|---|
| Carte microSD 32 Go de marque (SanDisk, Samsung) | Sur place | ~6 € ; chez DigiKey, ce sont des cartes industrielles à 42 € ou plus. |
| Inserts M3 en laiton (×20) | Mouser (Spirol IUTB-M3, 0,23 € pièce dès 10) ou AliExpress | Pour l'impression 3D. |
| Vis M3 × 8 et × 10 | Quincaillerie ou AliExpress | |
| Patins adhésifs | Quincaillerie | Chez DigiKey/Mouser, vendus par 144 au minimum. |
| Plaque à souder, fil silicone 22/26 AWG, connecteurs JST-PH, barrettes 2,54 mm, gaine | Gotronic, AliExpress, ou en stock chez toi | |
| Filament PETG blanc + transparent | Gotronic (24,40 € la bobine) ou boutique Bambu Lab | |
| Capuchons pour boutons 12 mm (optionnel) | Mouser (Adafruit 1009, 5,12 €) ou impression 3D | |

---

## Comparatif DigiKey / Mouser / Gotronic / Accu-Run

- **DigiKey** : livre à La Réunion (confirmé au panier). Prix **HT** (« prix unitaire sans TVA »). Livraison offerte dès 75 €.
- **Mouser** : La Réunion ne figure pas dans la liste « Mouser dans le monde ». La livraison en 974 est **à vérifier au panier**. Prix en €, a priori HT.
- **Gotronic** : prix **TTC**, livraison Colissimo Outre-Mer (5 à 7 jours, prix selon le poids).
- **Accu-Run** : magasin réunionnais, prix TTC.

| BOM | Pièce | DigiKey (€ HT · stock) | Mouser (€ · stock) | Gotronic (€ TTC · stock) | Choix |
|---|---|---|---|---|---|
| 1 | Carte ESP32-S3 avec PSRAM (×2) | DevKitC-1 (N8R8, 1U-N8R8, N32R16V) **toutes en rupture** · **Olimex DevKit-LiPo 8,18 · 250** | DevKitC-1-N16R8 11,39 · 62 · N32R16V 13,67 · 580 | Olimex DevKit-LiPo 9,90 (réappro. estimé 12/11) · EA 12,60 | **DigiKey Olimex** |
| 2 | Ampli MAX98357A (×2) | Adafruit 3006 **5,28 · 3 896** | 5,12 · 745 | DFR0954 6,50 · 8 | **DigiKey** |
| 3 | Haut-parleur 4 Ω 5 W ~66 mm | Visaton FR 7 **7,63 · 502** | Visaton 2015 : 8,81 · sur commande | 8 Ω seulement (LS01-5, 6,80) | **DigiKey** |
| 4 + 8 | Écran 2" ST7789 + microSD | Adafruit 4311 17,71 · 481 | 17,03 · 365 | 24,95 · en stock | **DigiKey** |
| 5 | Encodeur + molette (×2) | Adafruit 377 3,99 · 87 | 3,87 · 72 | GT055 2,50 (sans molette) | **DigiKey** |
| 6 | Boutons 12 mm | Adafruit 1119 2,22 · 349 | 2,15 · 6 | Assortiment 25 BP 7,90 | **DigiKey** |
| 6b | Capuchons de boutons | non trouvé | Adafruit 1009 5,12 · 13 | inclus dans l'assortiment | optionnel |
| 7 | Interrupteur marche/arrêt | ZF KRE2ANA1BBD 2,25 · 4 722 | non relevé | DS12LR 2,15 | **DigiKey** |
| 10 | Ruban de LED 60 LED/m | Adafruit 2537 RGB : **rupture** · **4689 RGBW 1 m 26,59 · 32** | 2846 RGBW 23,18 · 62 | WS2812 2 m 19,60 · en stock | **DigiKey 4689** (RGBW à déclarer dans le code) |
| 11 | Décaleur de niveau | SN74AHCT125N 0,84 · 497 | 0,843 · 2 858 | absent (KY051 4,80) | **DigiKey** |
| 17 | Charge + 5 V | PowerBoost 2465 : **différé (21/01/2027)** · **6091 + U3V40F5 : 15,00** | PowerBoost 17,16 · 11 | absent | **DigiKey 6091 + U3V40F5** |
| 15 | Support 18650 (×2) | Keystone 1042 6,11 | 5,25 · 17 599 | BH18650-1 1,80 (non ignifugé) | **DigiKey** |
| 16 | Protection 1S | non trouvé | non relevé | 3,60 · 43 | **inutile** avec des cellules protégées |
| 14 | Batteries 18650 (×2) | — (pas d'envoi de lithium seul) | — | — | **Accu-Run** : Ansmann 3500 mAh protégée, 29,00 TTC |
| 12–13, 18 | Résistances, condensateur | 0,024 / 0,55 · en stock | non relevé | — | **DigiKey** |
| 21 | Inserts M3 | non relevé | Spirol IUTB-M3 0,318 (0,226 dès 10) · 57 283 | absent | Mouser ou AliExpress |
| 23 | Patins | 3M SJ5302 ~0,11 (par 144) | 0,099 (par 144) | absent | Quincaillerie |
| 9 | Carte microSD 32 Go | 42 à 140 € (industrielles) | non relevé | — | **Sur place** |
| 19–20 | Filament PETG | — | — | 24,40 la bobine | Gotronic ou Bambu Lab |

### Paniers comparés (électronique, hors batteries, microSD et filament)

| | DigiKey | Mouser | Gotronic |
|---|---|---|---|
| Total | **≈ 122 € HT** | ≈ 131 € | ≈ 96 € TTC, mais sans haut-parleur 4 Ω ni charge/5 V correcte |
| Ce qui manque | Inserts | Haut-parleur sur commande ; protection 1S | Haut-parleur 4 Ω, charge + 5 V ≥ 2 A, décaleur 74AHCT125 |
| Livraison à La Réunion | ✅ confirmée, express | ❓ à vérifier | ✅ Colissimo Outre-Mer, 5 à 7 jours |

**Pourquoi DigiKey :** une seule commande express couvre toute l'électronique, toutes les pièces sont de marque et en stock (en remplaçant le PowerBoost), et la livraison est offerte.

---

## Annexe — plans B

Si DigiKey ne convient plus (rupture, frais imprévus) :

- **Gotronic** : Olimex DevKit-LiPo ([39664](https://www.gotronic.fr/art-carte-esp32-s3-devkit-lipo-49803.htm), 9,90 €), ampli [DFR0954](https://www.gotronic.fr/art-module-ampli-audio-i2s-dfr0954-35876.htm) (6,50 €), écran [ADA4311](https://www.gotronic.fr/art-module-afficheur-ips-tft-2-ada4311-30797.htm) (24,95 €), encodeur [GT055](https://www.gotronic.fr/art-module-encodeur-rotatif-gt055-28502.htm) (2,50 €), [assortiment de 25 boutons](https://www.gotronic.fr/art-boite-de-25-bp-couleur-48902.htm) (7,90 €), interrupteur [DS12LR](https://www.gotronic.fr/art-interrupteur-ds12lr-4437.htm) (2,15 €), [ruban WS2812 2 m](https://www.gotronic.fr/art-ruban-rgb-2-m-120-leds-36115.htm) (19,60 €), [convertisseur de niveaux KY051](https://www.gotronic.fr/art-convertisseur-de-niveaux-4-canaux-ky051-29156.htm) (4,80 €), [coupleur BH18650-1](https://www.gotronic.fr/art-coupleur-d-accu-bh18650-1-5713.htm) (1,80 €), [protection 1S](https://www.gotronic.fr/art-protection-batterie-1s-48852.htm) (3,60 €), [haut-parleur LS01-5 8 Ω](https://www.gotronic.fr/art-haut-parleur-77-mm-ls01-5-28404.htm) (6,80 €).
- **Mouser** : ESP32-S3-DevKitC-1-N16R8 (11,39 €, 62 en stock), et le reste des références Adafruit aux prix du comparatif. Livraison en 974 à vérifier.
- **AliExpress** : module IP5306 (charge + 5 V 2,4 A), haut-parleur 4 Ω 5 W, inserts, vis, patins, consommables. Compter 2 à 4 semaines.
