# Concevoir dès le départ pour la certification CE

Le Boîtier est destiné à être vendu dans l'UE (y compris à La Réunion) et doit porter le marquage CE au titre de la directive RED. Nous concevons donc le produit final autour d'un module radio pré-certifié (ESP32-S3-WROOM-1), d'un circuit imprimé sur mesure avec des composants traçables, d'une batterie remplaçable par l'utilisateur, et d'un firmware à mises à jour signées. Le prototype en modules sert à valider le fonctionnement ; il n'est pas lui-même certifiable. Détail des exigences : [docs/certification-ce.md](../certification-ce.md).

## Consequences

- Les modules génériques (IP5306, clones AliExpress) sont réservés au prototype et seront remplacés sur le circuit final.
- La matière du boîtier final devra probablement être ignifugée (à valider avec le laboratoire).
- Le choix Arduino/PlatformIO (ADR 0002) devra permettre Secure Boot, chiffrement de la flash et mises à jour signées.
