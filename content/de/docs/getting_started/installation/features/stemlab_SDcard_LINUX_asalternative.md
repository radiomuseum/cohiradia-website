---
title: "stemlab_SDcard_LINUX"
nav_exclude: true
_build:
  list: never
  render: always
---

#### Wenn Sie LINUX verwenden:

Unter LINUX eignet sich wiederum der [Balena Etcher](https://etcher.balena.io/#download-etcher). Alternativ können Sie die SD-Karte direkt über die Befehlszeile mit den folgenden Befehlen beschreiben:<br/>

Lesen Sie zunächst die gemounteten Partitionen der SD-Karte aus:

```bash
lsblk -f
```
Diese werden z. B. als sda1, sda2 oder ähnlich aufgeführt. Hängen Sie dann die SD-Geräte aus und beginnen Sie mit dem Beschreiben:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE ist dabei das, was Ihr lsblk auflistet, in meinem Beispiel sda. Dann:

```bash
sudo dd if=redpitaya_full.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync
```
Nun wird die Karte beschrieben. Wenn der Vorgang abgeschlossen ist, werfen Sie die Karte aus:

```bash
sudo eject /dev/YOURSDDEVICE
```

**ACHTUNG: dd muss mit großer Vorsicht verwendet werden. Wenn Sie das falsche Ziel angeben, können wichtige Systemlaufwerke gelöscht werden. Überprüfen Sie daher bitte dreimal, was Sie tun!**