# SECF - Shelly-to-ESPHome conversion files

File per convertire gli Shelly Gen4 da ShellyOS a ESPHome, in modo indipendente da terzi.

- **Cosa c'è**: gli YAML dei modelli (`shelly-gen4/configs`), il componente delle partizioni, gli script di build e il workflow che pubblica gli zip di conversione come release (tag `gen4-vX.Y.Z`). L'ultima release è `gen4-v1.0.11`.
- **Cosa non c'è**: i moduli per le lampade Wiz (failsafe, dimmer, limiti di luminosità, ecc.), che stanno nel ramo `modulare-secf` della repo [esphome-shelly-wiz-physical-failsafe](https://github.com/Gionames/esphome-shelly-wiz-physical-failsafe/tree/modulare-secf) e usano questa repo come base.
- **Origine e licenza**: lavoro derivato da [automatous-io/shelly-gen4-esphome](https://github.com/automatous-io/shelly-gen4-esphome) v1.5.2, licenza Apache 2.0 (vedi `NOTICE` e `shelly-gen4/LICENSE`).
- **Toolchain**: gli zip si compilano sempre con ESPHome 2026.8.2 / ESP-IDF 5.5.5 (immagine fissata in `shelly-gen4/.devcontainer/Dockerfile`), così bootloader e partizioni restano identici a quelli di automatous v1.5.2.

## Come si usa

- **Convertire uno Shelly**: scarica dalla release lo zip del tuo modello e caricalo dalla pagina web originale dello Shelly, come descritto in [installazione](shelly-gen4/docs/INSTALL.md); poi segui l'[adozione in Home Assistant](shelly-gen4/docs/ADOPTION.md).
- **Usarla come base nei tuoi YAML ESPHome**: includi un file di `shelly-gen4/configs` fissando il tag della release (mai `main`), poi aggiungi i moduli che ti servono. Per le Wiz, vedi il ramo `modulare-secf` indicato sopra, che ha l'esempio completo.

```yaml
packages:
  base:
    url: https://github.com/Gionames/SECF
    ref: gen4-v1.0.11
    files: [shelly-gen4/configs/shelly-1pm-mini-gen4.yaml]
```

Modelli disponibili in `shelly-gen4/configs`: Shelly 1, 1 Mini, 1PM, 1PM Mini, 2PM, EM Mini e Plug US (Gen4).

Documentazione: [shelly-gen4/README.md](shelly-gen4/README.md), [installazione](shelly-gen4/docs/INSTALL.md), [adozione in Home Assistant](shelly-gen4/docs/ADOPTION.md), [changelog](shelly-gen4/CHANGELOG.md).

Le release sono pre-release non verificate su tutto l'hardware: provare prima su un dispositivo non critico.
