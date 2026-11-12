# Liste d'achat — Prototype v1 (livraison à La Réunion)

Relevé du 10/11/2026 dans le navigateur (digikey.fr, mouser.fr, accu-run.fr), plus le relevé direct de gotronic.fr fait le même jour. Repart de [BOM.md](BOM.md). Prix et stocks à revérifier au moment de payer.

> **Prototype ≠ produit certifié.** Ces modules servent à valider le fonctionnement. Le produit vendu (certifié CE) utilisera un circuit imprimé sur mesure avec des composants traçables : voir [docs/certification-ce.md](../docs/certification-ce.md). Pour le prototype, on prend quand même des modules **de marque** (Espressif, Olimex, Adafruit, Visaton, Keystone, TI, Ansmann) : mêmes puces que la version finale, fiches techniques et certificats disponibles.

---

## ✅ Décision finale

**Une commande DigiKey (express, livraison gratuite) + 2 batteries chez Accu-Run (La Réunion) + quelques petites fournitures.**

> **Mise à jour du 12/11/2026 : tu as choisi de tout regrouper en une seule commande AliExpress, sans commander chez DigiKey ni Gotronic.** Le panier AliExpress est décrit plus bas (« Panier AliExpress, version du 12/11/2026 ») ; les deux batteries restent à prendre chez Accu-Run. Le plan DigiKey ci-dessous est conservé comme plan B de qualité (pièces de marque, utile pour la certification CE).

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
| 1 | Seeed **104990303**, ruban de LED adressables RGB **60 LED, 1 m** (WS2813B, compatible WS2812) | 1597-1486-ND | 7,35 € | 7,35 € |
| 2 | TI **SN74AHCT125N**, décaleur de niveau (DIP-14) | 296-4655-5-ND | 0,84 € | 1,68 € |
| 2 | Keystone **1042**, support 18650 (UL 94 V-0) | 36-1042-ND | 6,11 € | 12,22 € |
| 10 | Stackpole CF14JT330R, résistance 330 Ω | CF14JT330RCT-ND | 0,024 € | 0,24 € |
| 10 | Stackpole CF14JT100K, résistance 100 kΩ | CF14JT100KCT-ND | 0,024 € | 0,24 € |
| 2 | Nichicon UVR1A102MPD, condensateur 1000 µF 10 V | 493-1025-ND | 0,55 € | 1,10 € |
| 1 | **Charge + 5 V** : voir ci-dessous | | | ≈ 15 € |
| | | | **Total** | **≈ 103 € HT** |

> Le ruban Adafruit 4689 (RGBW, 26,59 €), jugé trop cher, a été remplacé dans le panier par le Seeed 104990303 (29 en stock le 10/11). Autre option moins chère encore en stock : DFRobot FIT0613, 120 LED sur 2 m, WS2812, 10,56 €.

**⚠️ Charge + 5 V : remplacer le PowerBoost.** L'Adafruit 2465 PowerBoost 1000C (1528-1349-ND, 17,71 €), encore dans le panier, est passé en « articles différés » (réassort annoncé le 21/01/2027). Décision : le remplacer par la paire suivante, en stock et plus puissante :

| Qté | Pièce | N° DigiKey | Prix HT | Stock |
|---|---|---|---|---|
| 1 | Adafruit **6091**, chargeur BQ25185 (lecture pendant la charge) | 1528-6091-ND | 6,17 € | 382 |
| 1 | Pololu **U3V40F5**, convertisseur 5 V jusqu'à 3,5 A (entrée 1,3 à 5 V) | 2183-4012-ND | 8,83 € | 304 |

Le Pololu est un **produit marketplace**, expédié par Pololu : des frais de port séparés sont possibles, et la livraison à La Réunion est à vérifier au panier. Ses 3,5 A suffisent pour l'ampli, les LED et le Wi-Fi en même temps, contre 1 A pour le PowerBoost.

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

#### Panier AliExpress (version du 12/11/2026, remplace la première)

Panier invité dans Chrome, pays de livraison **France métropolitaine** : la livraison à La Réunion et ses frais restent à vérifier avec ton adresse 974. Il contient **25 lignes** : sous-total **59,35 €** + livraison **20,62 €** = **79,97 €**.

| Qté | Article | Vendeur | Prix du panier | Prix « normal » | Marque+ |
|---|---|---|---|---|---|
| 2 | Carte ESP32-S3 mini N16R8 (16 Mo flash, 8 Mo PSRAM, 44 broches) | Boutique Keyestudio | 16,90 € (+ 5,53 € de port) | 16,90 € | oui |
| 1 | Ampli I2S MAX98357 (EstarDyn) | EstarDyn | 1,01 € | 9,60 € | oui |
| 1 | Écran 2,0" ST7789V 240×320 SPI (EstarDyn), sans lecteur microSD | EstarDyn | 1,01 € | 17,36 € | oui |
| 3 | Modules lecteur microSD SPI | Shop1105399116 | 1,01 € | 18,63 € | non |
| 5 | Encodeurs EC11 avec bouton poussoir | DQLZV | 1,01 € | 5,78 € | oui |
| 6 | Boutons poussoirs de panneau 16 mm, noirs | DQLZV | 1,01 € | 5,62 € | oui |
| 1 m | Ruban WS2812B 60 LED/m, IP30 | Super LED Store | 1,01 € | 11,90 € | oui |
| 2 | Modules charge/décharge IP5306 (5 V, 2 A) | Your Cee | 1,26 € (+ 5,66 € de port) | 1,64 € | non |
| 5 | Supports de batterie 18650 simples, avec fils | Shenzhen BaoXin | 1,01 € | 6,48 € | non |
| 10 | Circuits SN74HCT125N (DIP-14) | New IC Store | 1,01 € (+ 4,02 € de port) | 1,87 € | non |
| 300 | Kit de résistances 1/4 W, 30 valeurs | Venteny | 1,01 € | 15,34 € | non |
| 20 | Condensateurs 1000 µF 10 V | Hong flagcore | 6,28 € | 6,28 € | non |
| 50 | Inserts laiton M3 × L5 × OD5 | EDGAR GARY | 6,94 € | 6,94 € | oui |
| 55 | Vis M3 × 8 inox DIN912 | EN XIXIAN | 6,67 € | 6,67 € | oui |
| 55 | Vis M3 × 10 inox DIN912 | EN XIXIAN | 6,12 € | 6,12 € | oui |
| 10 paires | Câbles JST-PH 2 broches 15 cm | CHANZON | 1,01 € | 9,51 € | oui |
| 172 | Kit de gaine thermorétractable 2:1 | CHANZON | 1,00 € (+ 7,29 € de port) | 11,50 € | oui |
| 20 | Plaques à souder double face | CHANZON | 2,87 € | 15,88 € | oui |
| 20 | Barrettes 40 broches 2,54 mm, mâles et femelles | CHANZON | 1,13 € | 13,40 € | oui |
| 24 | Patins ronds autocollants Ø 20 mm | Unique House | 1,01 € | 4,10 € | non |
| 10 | Interrupteurs à bascule MTS-102 (6 A 125 V, 3 broches), rouges | Shop1104461129 | 8,16 € | 8,16 € | Choice |
| 1 | Carte microSD SanDisk Ultra 32 Go | AE-3CBrand Store | 13,88 € | 13,88 € | Choice |
| 10 | Capuchons de molette noirs, axe « prune » 6 mm | Lucky JD Store | 0,96 € (+ 2,71 € de port) | 0,96 € | Choice |
| 10 m | Fil silicone UL3239 22 AWG, rouge | SKYGOD | 3,03 € (+ 3,36 € de port) | 3,03 € | Choice |
| 10 m | Fil silicone UL3239 22 AWG, noir | SKYGOD | 3,03 € | 3,03 € | Choice |

> ⚠️ **Les prix à 1,01 € sont des offres « nouveau client », limitées à 1 lot par acheteur et réservées aux premiers achats d'un compte.** Avec un compte qui a déjà acheté, la même commande monte à **environ 240 €** (colonne « prix normal », port compris).

**Ajouts « Choice » du 12/11/2026 :** interrupteur à bascule 6 A (les modèles Marque+ trouvés étaient limités à 0,5 A), carte microSD SanDisk, capuchons de molette et fil silicone. Les cartes microSD vendues sur AliExpress sont souvent contrefaites, même sous le badge Choice : vérifie-la avec H2testw ou F3 à la réception.

**Introuvable ou écarté sur AliExpress :**
- **Haut-parleur** : seulement des modèles de 3 W ou moins, trop petits pour être entendus à 3 m. Le Visaton FR 7 (DigiKey/Mouser) ou le 77 mm 5 W de Gotronic (8 Ω) restent la référence.
- **Filament PETG** : l'eSUN officiel (14,27 €) a 36,34 € de port, et un PETG 1 kg Choice (10,52 €) 32,91 € : une bobine revient à plus de 40 €, contre 24,40 € chez Gotronic. À acheter ailleurs.
- **Fil 26 AWG** : seul le 22 AWG est dans le panier (rouge et noir pour l'alimentation) ; le 26 AWG pour les signaux est à ajouter si besoin.
- **Batteries 18650** : pas d'expédition de batteries lithium seules par la poste, donc Accu-Run (La Réunion).

**Ce que change ce panier sur le montage (voir [COMPATIBILITE.md](COMPATIBILITE.md)) :**
- **Écran sans microSD** : le lecteur microSD devient un module séparé, relié au même bus SPI avec sa propre broche CS.
- **Charge et 5 V par un IP5306** (2,1 A en charge, 3,5 A en sortie) à la place de la paire Adafruit 6091 + Pololu : il supprime la minuterie de charge de 6 h, mais il s'éteint tout seul si la consommation tombe sous environ 45 mA pendant une trentaine de secondes. Je n'ai pas pu vérifier que sa prise est du type USB-C.
- **Boutons de panneau de 16 mm** à la place de boutons 12 mm : les trous de la façade sont à adapter.
- **Pas d'ESP32-S3 Olimex ni de DevKitC-1 officielle** : une carte compatible N16R8, dont le brochage est à vérifier à la réception (les GPIO 35 à 37 restent réservés à la PSRAM).

## Comparatif des plateformes — AliExpress, DigiKey, Mouser, Gotronic

Même liste de pièces, prix du 12/11/2026. **AliExpress** : prix du panier (offre « nouveau client ») puis, entre parenthèses, le prix normal. **DigiKey** : HT. **Mouser** : prix affichés sur mouser.fr. **Gotronic** : TTC. Les cases « — » signalent une pièce absente ou non relevée.

| Pièce (quantité) | AliExpress | DigiKey | Mouser | Gotronic |
|---|---|---|---|---|
| Carte ESP32-S3 avec PSRAM (×2) | 16,90 (16,90) | 16,36 (Olimex, N8R8) | 22,78 (DevKitC-1 N16R8) | 19,80 (Olimex, en rupture) |
| Ampli I2S MAX98357 (×1) | 1,01 (9,60) | 5,28 | 5,12 | 6,50 |
| Écran 2" ST7789 (×1) | 1,01 (17,36), sans microSD | 17,71, avec microSD | 17,03, avec microSD | 24,95, avec microSD |
| Module microSD (×1, si l'écran n'en a pas) | 1,01 (18,63) pour 3 | inclus dans l'écran | inclus dans l'écran | inclus dans l'écran |
| Encodeur rotatif (×2) | 1,01 (5,78) pour 5 | 7,98 (avec molette) | 7,74 (avec molette) | 5,00 (sans molette) |
| Boutons (×4) | 1,01 (5,62) pour 6, panneau 16 mm | 2,22 (10, tactiles 12 mm) | 2,15 (10, tactiles 12 mm) | 7,90 (25) |
| Interrupteur marche/arrêt | 8,16 (8,16) pour 10, 6 A | 2,25 | — | 2,15 |
| Ruban LED 60/m, 1 m | 1,01 (11,90) | 7,35 | 23,18 (RGBW) | 19,60 (2 m) |
| Décaleur de niveau (×2) | 1,01 (1,87) pour 10 | 1,68 | 1,69 | 4,80 |
| Charge + 5 V | 1,26 (1,64) pour 2 IP5306 | 15,00 (6091 + U3V40F5) | 17,16 (PowerBoost, 1 A) | — |
| Supports de batterie 18650 (×2) | 1,01 (6,48) pour 5 | 12,22 (ignifugés) | 10,50 | 3,60 |
| Résistances + condensateur | 7,29 (21,62) | 1,58 | — | — |
| Inserts M3 (×20) | 6,94 (6,94) pour 50 | — | 4,52 | — |
| Vis M3 | 12,79 (12,79) pour 110 | — | — | — |
| Câbles JST-PH | 1,01 (9,51) pour 10 paires | — | — | — |
| Gaine thermorétractable | 1,00 (11,50) + 7,29 de port | — | — | — |
| Plaques à souder | 2,87 (15,88) pour 20 | — | — | — |
| Barrettes 2,54 mm | 1,13 (13,40) | — | — | — |
| Patins | 1,01 (4,10) pour 24 | ≈ 16 (144 minimum) | ≈ 14 (144 minimum) | — |
| Haut-parleur 4 Ω 5 W 66 mm | — (introuvable) | 7,63 | 8,81 (sur commande) | 6,80 (8 Ω) |
| **Total des lignes ci-dessus** | **≈ 80 € (≈ 240 € sans offre nouveau client)**, port compris, avec microSD, fil et interrupteur | **≈ 103 € HT pour l'électronique** | **≈ 131 €** | **≈ 96 € TTC, incomplet** |

**Ce que les chiffres cachent :**
- **AliExpress** n'est avantageux que si ton compte peut profiter de l'offre « nouveau client ». Sans elle, la même commande coûte environ 240 €. Il est aussi le seul à ne pas avoir de haut-parleur correct, et ses délais sont de 2 à 4 semaines (livraison estimée fin novembre à début décembre en France métropolitaine).
- **DigiKey** couvre l'électronique avec des pièces de marque, traçables, en express. C'est la seule base qui prépare vraiment la certification CE.
- **Mouser** revient à peu près au même prix, mais il n'a pas confirmé La Réunion.
- **Gotronic** est le moins cher en apparence, mais il lui manque le haut-parleur 4 Ω, une charge de 2 A et le décaleur de niveau.
- **Qualité des composants** : sur AliExpress, aucune puce (IP5306, 74HCT125) n'est certifiée d'origine. C'est acceptable pour un prototype, pas pour le produit certifié.

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
| 10 | Ruban de LED 60 LED/m | **Seeed 104990303 1 m 7,35 · 29** · DFRobot FIT0613 2 m 10,56 · 77 · Adafruit 4689 RGBW 26,59 · 32 | 2846 RGBW 23,18 · 62 | WS2812 2 m 19,60 · en stock | **DigiKey Seeed 104990303** |
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
| Total | **≈ 103 € HT** | ≈ 131 € | ≈ 96 € TTC, mais sans haut-parleur 4 Ω ni charge/5 V correcte |
| Ce qui manque | Inserts | Haut-parleur sur commande ; protection 1S | Haut-parleur 4 Ω, charge + 5 V ≥ 2 A, décaleur 74AHCT125 |
| Livraison à La Réunion | ✅ confirmée, express | ❓ à vérifier | ✅ Colissimo Outre-Mer, 5 à 7 jours |

**Pourquoi DigiKey :** une seule commande express couvre toute l'électronique, toutes les pièces sont de marque et en stock (en remplaçant le PowerBoost), et la livraison est offerte.

---

## Annexe — plans B

Si DigiKey ne convient plus (rupture, frais imprévus) :

- **Gotronic** : Olimex DevKit-LiPo ([39664](https://www.gotronic.fr/art-carte-esp32-s3-devkit-lipo-49803.htm), 9,90 €), ampli [DFR0954](https://www.gotronic.fr/art-module-ampli-audio-i2s-dfr0954-35876.htm) (6,50 €), écran [ADA4311](https://www.gotronic.fr/art-module-afficheur-ips-tft-2-ada4311-30797.htm) (24,95 €), encodeur [GT055](https://www.gotronic.fr/art-module-encodeur-rotatif-gt055-28502.htm) (2,50 €), [assortiment de 25 boutons](https://www.gotronic.fr/art-boite-de-25-bp-couleur-48902.htm) (7,90 €), interrupteur [DS12LR](https://www.gotronic.fr/art-interrupteur-ds12lr-4437.htm) (2,15 €), [ruban WS2812 2 m](https://www.gotronic.fr/art-ruban-rgb-2-m-120-leds-36115.htm) (19,60 €), [convertisseur de niveaux KY051](https://www.gotronic.fr/art-convertisseur-de-niveaux-4-canaux-ky051-29156.htm) (4,80 €), [coupleur BH18650-1](https://www.gotronic.fr/art-coupleur-d-accu-bh18650-1-5713.htm) (1,80 €), [protection 1S](https://www.gotronic.fr/art-protection-batterie-1s-48852.htm) (3,60 €), [haut-parleur LS01-5 8 Ω](https://www.gotronic.fr/art-haut-parleur-77-mm-ls01-5-28404.htm) (6,80 €).
- **Mouser** : ESP32-S3-DevKitC-1-N16R8 (11,39 €, 62 en stock), et le reste des références Adafruit aux prix du comparatif. Livraison en 974 à vérifier.
- **AliExpress** : module IP5306 (charge + 5 V 2,4 A), haut-parleur 4 Ω 5 W, inserts, vis, patins, consommables. Compter 2 à 4 semaines.
