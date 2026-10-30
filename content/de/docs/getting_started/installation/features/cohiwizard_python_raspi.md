---
title: "cohiwizard_python_raspi"
nav_exclude: true
_build:
  list: never
  render: always
---

## COHIWizard auf dem Raspberry Pi nachinstallieren

Das vorbereitete Raspberry-Pi-Image enthält das Betriebssystem und den COHI-Player, **der COHIWizard ist darauf jedoch nicht vorinstalliert**. Er muss nach dem ersten Hochfahren direkt auf dem Raspberry Pi aus dem GitHub-Repository nachinstalliert werden:

1. Verbinden Sie den Raspberry Pi mit dem Internet (LAN oder WLAN) und öffnen Sie ein Terminal.

2. Klonen Sie das [COHIWizard-Repository von GitHub](https://github.com/hermy-sf/COHIWizard/tree/main) in ein Verzeichnis Ihrer Wahl:

```bash
git clone https://github.com/hermy-sf/COHIWizard.git
cd COHIWizard
```

3. Folgen Sie den Anweisungen in der [README-Datei](https://github.com/hermy-sf/COHIWizard/blob/main/README.md) unter „Method B“ (Einrichten einer virtuellen Python-Umgebung und Installation der benötigten Pakete).

Achtung: Diese Installation wird nur empfohlen, wenn Sie etwas Erfahrung mit GitHub, Python und der Linux-Kommandozeile haben. Der COHI-Player bleibt auf dem Image weiterhin installiert und kann alternativ genutzt werden.
