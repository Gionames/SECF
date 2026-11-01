# SECF - Shelly-to-ESPHome conversion files

File per convertire gli Shelly Gen4 da ShellyOS a ESPHome, in modo indipendente da terzi.

- **Cosa c'è**: gli YAML dei modelli (`shelly-gen4/configs`), il componente delle partizioni, gli script di build e il workflow che pubblica gli zip di conversione come release (tag `gen4-vX.Y.Z`).
- **Cosa non c'è**: i moduli per le lampade Wiz (failsafe, dimmer, ecc.), che stanno nella repo [esphome-shelly-wiz-physical-failsafe](https://github.com/Gionames/esphome-shelly-wiz-physical-failsafe) e usano questa repo come base.
- **Origine e licenza**: lavoro derivato da [automatous-io/shelly-gen4-esphome](https://github.com/automatous-io/shelly-gen4-esphome) v1.5.2, licenza Apache 2.0 (vedi `NOTICE` e `shelly-gen4/LICENSE`).
- **Toolchain**: gli zip si compilano sempre con ESPHome 2026.8.2 / ESP-IDF 5.5.5 (immagine fissata in `shelly-gen4/.devcontainer/Dockerfile`), così bootloader e partizioni restano identici a quelli di automatous v1.5.2.

Documentazione: [shelly-gen4/README.md](shelly-gen4/README.md), [installazione](shelly-gen4/docs/INSTALL.md), [adozione in Home Assistant](shelly-gen4/docs/ADOPTION.md), [changelog](shelly-gen4/CHANGELOG.md).

Le release sono pre-release non verificate su hardware: provare prima su un dispositivo non critico.
