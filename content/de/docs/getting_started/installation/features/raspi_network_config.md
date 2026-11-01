---
title: "raspi_network_config"
nav_exclude: true
_build:
  list: never
  render: always
---

## Konfiguration der Netzwerkparameter

Falls Sie die Installation auf dem Raspberry Pi von einem der beiden Images gemacht haben, gibt es auf dem Desktop drei vordefinierte Icons zur einfachen Konfiguration der Netzwerkparameter:

![Desktop-Icons DHCP, Fixed IP und Link Local](/images/Raspi_COHI_Player_Desktopicons_NW_image001.png)

Das Icon **DHCP** konfiguriert das LAN-Interface für den automatischen Bezug einer IP-Adresse in einem existierenden LAN. Diese Einstellung wird empfohlen, wenn das STEMLAB ebenfalls im Netzwerk angeschlossen ist oder der fl2k-Dongle verwendet wird. Diese Einstellung ermöglicht auch die Verwendung von Raspberry Pi Connect und eine Verbindung des Raspberry Pi über das SAMBA-Interface mit einem Windows-PC.

Das Icon **Fixed IP** ermöglicht die gleiche Funktionalität, weist aber dem Raspberry Pi eine fest vorgegebene Adresse im Netzwerk zu, die über `nmtui` oder über das Raspberry Pi OS einstellbar ist. Klicken Sie dazu im Raspberry Pi OS mit der linken Maustaste auf das Netzwerksymbol und wählen Sie „Advanced Options“ → „Verbindungen bearbeiten“:

![Netzwerkmenü von Raspberry Pi OS mit dem Eintrag „Verbindungen bearbeiten“](/images/Raspi_Config_Network_screenshot_image002.png)

Das Icon **Link Local** weist dem Raspberry Pi eine freie Adresse aus dem Adressbereich 169.254.1.0 bis 169.254.254.255 zu. Da das STEMLAB ebenfalls eine freie Adresse in diesem Bereich auswählt, eignet sich diese Einstellung, um eine direkte Verbindung über ein Ethernet-Kabel zwischen Raspberry Pi und STEMLAB ohne Anschluss an ein LAN herzustellen.
