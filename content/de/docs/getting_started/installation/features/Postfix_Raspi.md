---
title: "Postfix Raspberry Pi"
nav_exclude: true
_build:
  list: never
  render: always
---

3. Schreiben Sie das Image mit einer geeigneten Software auf die SD-Karte. **Für Windows** eignen sich [Win32DiskImager](https://win32diskimager.org/) oder [Balena Etcher](https://etcher.balena.io/#download-etcher).<br/>
**Unter Linux** eignet sich [Balena Etcher](https://etcher.balena.io/#download-etcher). Wenn Sie sich für die direkte Verwendung der Befehlszeile entscheiden, geben Sie einfach die folgenden Befehle ein: <br/>

Lesen Sie die gemounteten SD-Kartenpartitionen aus:

```bash
lsblk -f
```
Diese werden z. B. als sda1, sda2 oder ähnlich aufgeführt. Hängen Sie dann die SD-Geräte aus:

```bash
sudo umount /dev/YOURSDDEVICE*
```
YOURSDDEVICE ist dabei das, was Ihr lsblk auflistet, in meinem obigen Beispiel „sda“. Wechseln Sie dann in das Verzeichnis, in das Sie die Image-Datei heruntergeladen haben, und geben Sie Folgendes ein:

```bash
sudo dd if=COHI-RasPi4_V4.1_shrink.img of=/dev/YOURSDDEVICE bs=4M status=progress conv=fsync

```
Nun wird die Karte beschrieben. Wenn der Vorgang abgeschlossen ist, synchronisieren Sie die Karte und werfen Sie sie aus:

```bash
sync
sudo eject /dev/YOURSDDEVICE
```
Anschließend kann sie in den SD-Kartensteckplatz des Raspberry Pi eingesetzt werden, der dann betriebsbereit sein sollte.


**ACHTUNG: dd muss mit großer Vorsicht verwendet werden. Wenn Sie das falsche Ziel angeben, können wichtige Systemlaufwerke gelöscht werden. Überprüfen Sie daher bitte dreimal, was Sie tun!**

<br/>

### Alternative Installation direkt vom Source-Code

Alternativ können Sie für Schritt 2 auch eine individuelle Installation direkt vom [Source-Code auf GITHub](https://github.com/CPG-Archive/COHI-Player/) durchführen. Dies kann interessant sein, wenn Sie auf Ihrem Raspberry Pi bereits ein geeignetes OS (Trixie) installiert haben bzw. lediglich ein Update der COHIA-Player-Software machen möchten. 

**Bei speziellen Fragen zur Software für den Raspberry Pi wenden Sie sich bitte an Claus Peter Gallenmiller: [E-Mail](mailto:cpg-radio@gmx.de).**
