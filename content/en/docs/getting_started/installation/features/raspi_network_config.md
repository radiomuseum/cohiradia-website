---
title: "raspi_network_config"
nav_exclude: true
_build:
  list: never
  render: always
---

## Configuring the network parameters

If you installed the Raspberry Pi from one of the two images, there are three predefined desktop icons for easily configuring the network parameters:

![Desktop icons DHCP, Fixed IP and Link Local](/images/Raspi_COHI_Player_Desktopicons_NW_image001.png)

The **DHCP** icon configures the LAN interface to obtain an IP address automatically in an existing LAN. This setting is recommended if the STEMLAB is also connected to the network or if the fl2k dongle is used. This setting also allows the use of Raspberry Pi Connect and a connection between the Raspberry Pi and a Windows PC via the SAMBA interface.

The **Fixed IP** icon provides the same functionality, but assigns the Raspberry Pi a fixed address on the network, which can be set via `nmtui` or via Raspberry Pi OS. In Raspberry Pi OS, left-click the network icon and select "Advanced Options" → "Edit Connections" (in the screenshot, taken from a German system, this menu item is labelled "Verbindungen bearbeiten"):

![Raspberry Pi OS network menu with the item "Verbindungen bearbeiten" (Edit Connections)](/images/Raspi_Config_Network_screenshot_image002.png)

The **Link Local** icon assigns the Raspberry Pi a free address from the range 169.254.1.0 to 169.254.254.255. Since the STEMLAB also selects a free address in this range, this setting is suitable for a direct connection between the Raspberry Pi and the STEMLAB via an Ethernet cable, without connecting to a LAN.
