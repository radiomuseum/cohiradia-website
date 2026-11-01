---
title: "display_35_config"
nav_exclude: true
_build:
  list: never
  render: always
---

## OPTIONAL: Konfiguration des 3,5"-Display-Treibers {#optional-display-treiber}

**Dieser Abschnitt ist nur nötig, wenn Sie das Raspberry 3,5-Zoll-Touchscreen-Display vom Typ RPI-35LCD verwenden. In allen anderen Fällen können Sie ihn überspringen.**

Im RasPi4-3,5"-Image ist das Display von CUQI vorkonfiguriert. Der Treiber kann sehr einfach für das Raspberry 3,5-Zoll-Touchscreen-Display, Typ RPI-35LCD, umkonfiguriert werden:

1. SSH-Verbindung zum Raspberry Pi mit PuTTY aufbauen.
2. Mit User `pi` und Passwort `pi` einloggen.
3. Bei Verwendung des Raspberry 3,5-Zoll-Touchscreens, Typ RPI-35LCD, eingeben:

```bash
bash config_display_2.sh
```

Die Konfiguration für das CUQI-Display kann mit

```bash
bash config_display_1.sh
```

wiederhergestellt werden.

Bei Bedarf kann der Touchscreen im Raspberry Pi OS im Systemmenü unter „Einstellungen“ – „Touchscreen Kalibrieren“ neu kalibriert werden.
