# Certification CE — exigences qui pèsent sur la conception

Le Boîtier a du Wi-Fi : c'est un **équipement radio**, il relève de la directive **RED 2014/53/UE**. La RED couvre aussi la sécurité électrique et la compatibilité électromagnétique. La Réunion étant une région ultrapériphérique de l'UE, le marquage CE s'y applique comme en métropole.

> Ce document liste ce qu'il faut **prévoir dès la conception**. Il ne remplace pas un laboratoire d'essais : la liste exacte des normes et le dossier sont à valider avec lui (par exemple LCIE, Emitech, ou un labo accrédité COFRAC).

## Ce qui est certifié

On ne certifie pas le prototype en modules, mais **le produit tel qu'il sera vendu** : circuit imprimé définitif, boîtier définitif, firmware définitif. Le prototype sert à valider le fonctionnement. Une **pré-série** sur circuit imprimé sur mesure part ensuite au laboratoire.

## Normes et textes probablement applicables

| Domaine | Texte / norme | Conséquence pour la conception |
|---|---|---|
| Radio | EN 300 328 (Wi-Fi / BLE 2,4 GHz) | Utiliser un **module radio pré-certifié** (ESP32-S3-WROOM-1 d'Espressif), respecter la zone dégagée autour de l'antenne indiquée par Espressif, ne pas modifier l'antenne. Réduit fortement les essais radio. |
| CEM | EN 301 489-1 et -17, EN 55032 / EN 55035 | Circuit imprimé avec plan de masse, filtrage de l'alimentation et de l'ampli classe D, câbles internes courts. Les fils volants d'un prototype ne passeraient pas. |
| Sécurité | EN 62368-1 | Matière du boîtier (voir plus bas), protection de la batterie, températures de surface. |
| Exposition RF | EN 62311 ou EN 62479 | Généralement simple pour un module Wi-Fi de faible puissance. |
| Cybersécurité | Règlement délégué RED (UE) 2022/30, norme **EN 18031-1**, obligatoire depuis le 1/08/2025 pour les équipements connectés à Internet | Pas de mot de passe par défaut commun (✅ mot de passe choisi à l'installation), mises à jour du firmware **signées**, protection des identifiants Wi-Fi stockés, désactivation des accès de débogage, protection contre la force brute sur l'Interface web. |
| Batterie | Règlement batteries **(UE) 2023/1542** | Cellules avec certificats **UN 38.3** et **IEC 62133-2** fournis par le vendeur. Dès le **18/02/2027**, la batterie d'un appareil portable doit être **retirable et remplaçable par l'utilisateur** avec des outils du commerce : trappe vissée + supports, jamais de cellules soudées. |
| Chargeur universel | Directive (UE) 2022/2380 | Port de charge **USB-C** (✅). Au-delà de 15 W de charge, USB Power Delivery obligatoire (on reste en dessous, à 10 W). Le produit doit pouvoir être vendu **sans chargeur**, avec le pictogramme correspondant. |
| Substances | RoHS 2011/65/UE, REACH | Composants achetés chez des distributeurs officiels qui fournissent les déclarations RoHS (Mouser, DigiKey, LCSC, Farnell…), pas de modules anonymes. |
| Fin de vie | DEEE, filière batteries (REP en France) | Inscription comme producteur auprès d'un éco-organisme DEEE et batteries, marquage poubelle barrée, info-tri (Triman). |
| Marquage et documents | — | Marquage CE, nom et adresse du fabricant, modèle, n° de lot, déclaration UE de conformité, notice de sécurité en français, dossier technique conservé 10 ans. |

## Conséquences sur nos choix

1. **Électronique finale** : circuit imprimé sur mesure avec le module ESP32-S3-WROOM-1 (N16R8 ou N8R8), ampli MAX98357A, puce de charge avec **sonde de température batterie (NTC)** et protection, achetés chez des distributeurs officiels. Les modules AliExpress (IP5306 notamment) ne servent qu'au prototype.
2. **Matière du boîtier** : le PETG standard n'est pas ignifugé. Avec une batterie lithium à l'intérieur, la norme EN 62368-1 exigera probablement une enveloppe classée au feu (UL 94 V-1 ou mieux) autour de la batterie et de l'électronique, ou une barrière interne ignifugée. À trancher avec le laboratoire. Le PETG reste valable pour le prototype.
3. **Batterie** : trappe vissée et supports de cellules, pour la rendre remplaçable par l'utilisateur.
4. **Firmware** : démarrage sécurisé (Secure Boot) et chiffrement de la flash de l'ESP32-S3, mises à jour signées, Interface web protégée contre la force brute ; HTTPS local à évaluer pour EN 18031.
5. **Budget et délai** : prévoir plusieurs milliers d'euros d'essais en laboratoire et quelques semaines. Demander des devis tôt.
