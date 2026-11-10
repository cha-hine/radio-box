# Arduino via PlatformIO pour le prototype et la v1

Nous développons le firmware avec le framework Arduino (via PlatformIO) et des bibliothèques éprouvées (ESP32-audioI2S, LovyanGFX, FastLED) plutôt qu'en ESP-IDF + ESP-ADF pur, pour aller 2 à 3 fois plus vite jusqu'à un prototype fonctionnel. Le framework Arduino tournant sur ESP-IDF, une migration partielle reste possible ; le choix sera réévalué avant l'industrialisation (robustesse, mises à jour automatiques, certification).
