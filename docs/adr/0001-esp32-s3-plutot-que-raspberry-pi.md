# ESP32-S3 plutôt que Raspberry Pi comme cerveau du Boîtier

Le Boîtier fonctionne sur batterie et vise à terme une production industrielle. Nous choisissons un microcontrôleur ESP32-S3 (avec PSRAM) plutôt qu'un Raspberry Pi Zero 2 W : faible consommation, démarrage instantané, coût unitaire bas (~3–5 € en volume) et approvisionnement fiable. En contrepartie, le logiciel est plus contraint (pas de Linux, décodage audio et Interface web limités par la mémoire).

## Consequences

- Certains formats de Webradio (HLS / `.m3u8`, codecs exotiques) peuvent ne pas être lisibles ; il faudra vérifier chaque flux visé.
- L'Interface web doit rester légère (servie depuis la mémoire flash du Boîtier).
