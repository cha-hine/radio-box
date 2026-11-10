# Liste des composants — Prototype v1

Prototype à base de **modules tout faits**, câblés sur plaque à souder (pas encore de circuit imprimé sur mesure). Les prix sont des **estimations** (AliExpress / Amazon / revendeurs FR, fin 2026) à vérifier à l'achat.

## Électronique

| # | Composant | Référence conseillée | Qté | Prix ≈ | Notes |
|---|---|---|---|---|---|
| 1 | Carte ESP32-S3 | **ESP32-S3-DevKitC-1 N16R8** (16 Mo flash, 8 Mo PSRAM) | 1 | 10 € | La PSRAM est indispensable pour le tampon des Webradios. Sur la N16R8, les GPIO 35–37 sont pris par la PSRAM : ne pas les utiliser. |
| 2 | Amplificateur I2S | **MAX98357A** (module) | 1 | 3 € | 3,2 W sur 4 Ω à 5 V. Alimenté en 5 V (sortie du module de charge), pas directement sur la batterie, pour garder toute la puissance. |
| 3 | Haut-parleur | Large bande **57–66 mm, 4 Ω, 5 W** | 1 | 5–12 € | Impérativement **4 Ω** (en 8 Ω, le MAX98357A ne donne que ~1,8 W). Monté dans une chambre fermée. |
| 4 | Écran | **TFT IPS 2,0" ST7789, 240×320, SPI** | 1 | 5 € | Prendre une version avec broche de rétroéclairage (BL) pilotable, pour la mise en veille. |
| 5 | Molette | **Encodeur rotatif EC11** avec bouton poussoir + bouton de molette | 1 | 2 € | Volume, navigation, validation. |
| 6 | Boutons | Boutons poussoirs **12×12 mm** avec capuchons | 4 | 2 € | Retour/Menu, Précédent, Suivant, Webradio/Playlist. |
| 7 | Interrupteur marche/arrêt | Interrupteur à glissière ou à bascule panneau (≥ 3 A) | 1 | 1 € | À l'arrière ; coupe la sortie batterie. |
| 8 | Lecteur microSD | Module **microSD SPI 3,3 V** (sans régulateur 5 V de préférence) | 1 | 1 € | À placer pour un accès depuis l'arrière. |
| 9 | Carte microSD | 32 Go, classe A1 | 1 | 6 € | Formatée en FAT32. |
| 10 | LED | Ruban **WS2812B 5 V, 60 LED/m** | 1 m | 5 € | Environ 30 LED utilisées (côtés + dessus), à ajuster au modèle 3D. |
| 11 | Adaptateur de niveau LED | **74AHCT125** (ou SN74AHCT1G125) | 1 | 1 € | Les WS2812B en 5 V lisent mal un signal de 3,3 V. |
| 12 | Résistance série LED | 330 Ω | 1 | — | Sur la ligne de données des LED. |
| 13 | Condensateur LED | 1000 µF 10 V électrolytique | 1 | — | En tête du ruban, entre 5 V et masse. |

## Alimentation

| # | Composant | Référence conseillée | Qté | Prix ≈ | Notes |
|---|---|---|---|---|---|
| 14 | Cellules | **18650 3500 mAh** authentiques (Samsung 35E, LG MJ1…), **même modèle et même lot** | 2 | 12 € | En parallèle → ~7000 mAh / ~25 Wh, ~12 h d'écoute estimées. Acheter chez un revendeur sérieux (beaucoup de contrefaçons). |
| 15 | Support ou pack | Support 2×18650 en parallèle, ou pack soudé par points | 1 | 2 € | Ne jamais souder directement au fer sur une cellule. |
| 16 | Protection batterie | Carte de protection **1S** (DW01 + 8205A) | 1 | 1 € | Surcharge, décharge profonde, court-circuit. |
| 17 | Charge + 5 V | Module « power bank » **IP5306 USB-C** (de préférence version I2C) | 1 | 3 € | Charge jusqu'à 2,1 A (~4 h pour une recharge complète), sortie 5 V jusqu'à 2,4 A, lecture pendant la charge. ⚠️ L'IP5306 se coupe tout seul si la consommation est trop faible : la version I2C permet de désactiver ce comportement. |
| 18 | Mesure batterie | 2 résistances 100 kΩ (pont diviseur vers une entrée analogique) | 2 | — | Pour afficher le niveau de batterie. |

## Mécanique

| # | Composant | Référence conseillée | Qté | Prix ≈ | Notes |
|---|---|---|---|---|---|
| 19 | Filament coque | **PETG** couleur au choix | 1 bobine | 20 € | |
| 20 | Filament Diffuseur | **PETG blanc translucide / naturel** | 1 bobine | 20 € | Imprimé par la deuxième buse de la X2D. |
| 21 | Inserts filetés | **Inserts M3** à poser à chaud (M3 × 5,7 mm) | 20 | 5 € | |
| 22 | Vis | M3 × 8 et M3 × 10, tête cylindrique | 20 | 3 € | |
| 23 | Patins | Patins silicone autocollants Ø 10 mm | 4 | 2 € | |
| 24 | Grille haut-parleur | Tissu acoustique ou grille fine (optionnel) | 1 | 3 € | Derrière la Moucharabieh du dessus. |

## Câblage et consommables

| # | Composant | Qté | Notes |
|---|---|---|---|
| 25 | Plaque à souder (perfboard) 7×9 cm | 2 | |
| 26 | Fil silicone 22 AWG (alimentation) et 26 AWG (signaux) | 2 × 5 m | |
| 27 | Connecteurs JST-PH 2,0 mm | 1 kit | Pour pouvoir débrancher batterie, haut-parleur et LED. |
| 28 | Gaine thermorétractable | 1 kit | |
| 29 | Broches mâles et femelles 2,54 mm | 1 kit | Pour rendre la DevKit et les modules amovibles. |

**Total estimé : ~150 €** pour un prototype, filament compris (moins de 100 € sans les bobines entières).

## Bilan électrique (à respecter dans le firmware)

| Poste | Consommation typique | Pic |
|---|---|---|
| ESP32-S3 + Wi-Fi | ~100 mA | ~350 mA |
| Amplificateur + haut-parleur | ~200 mA | ~800 mA |
| Écran (rétroéclairage allumé) | ~30 mA | ~40 mA |
| ~30 LED WS2812B | ~100 mA (Ambiance douce) | **~1,8 A en blanc à fond** |

La sortie 5 V de l'IP5306 est limitée à 2,4 A : le firmware doit **plafonner la luminosité des LED** (par exemple 500 mA au maximum), sinon le Boîtier peut redémarrer tout seul sur un pic de son.
