---
title: Frequenzabdeckung OSMO fl2k
linkTitle: Frequenzabdeckung OSMO fl2k
date: 2026-02-20
weight: 1
description: >

---

## Allgemeines:

Der OSMO-fl2k USB-VGA-Konverter erfreut sich mittlerweile aufgrund seines geringen Preises einer gewissen Beliebtheit als Wiederabe-Signalwandler. Allerdings hat er natürlich seine Einschränkungen. Die begrenzte DAC-Auflösung von 8 Bit wurde bereits im Kapitel ['SNR_Messungen']({{< relref "/docs/documentation/Testberichte/SNR_Messungen/_index.md" >}})  erörtert, sie macht sich erfreulicherweise allerdings bei der Audioqualität kaum bemerkbar.

Eine deutlichere Einschränkung gegenüber dem Flaggschiff STEMLAB ist die begrenzte Sampleingrate (SR) in Kombination mit der Tatsache, dass keine komplexen Daten an den Wandler übertragen werden. Dadurch muss die SR gemäß Nyquist-Theorem mindestens 2x die Basisbandbreite der abzuspielenden Aufzeichnung betragen. Da das OSMO weiters nicht on-board von der Basisbandfrequenz auf die Ziel-HF-Bandbreite hochrechnet, ergeben sich zwei Konsequenzen:

1. Der Computer muss die Basisbandsignale auf die Zielfrequenz hochrechnen, was einiges an Rechenlast für die CPU bedeutet. 
2. Danach muss das Signal mit einer ausreichenden SR über den USB-Port übertragen werden. So beträgt die minimale SR z.B. für das 41m-Band 2 x7.6 = 15.2 MS/s. 

### Perfomance bei PC als Steuercomputer

**Datenübertragung über USB:**
Die Übertragung über den USB-Port kann je nach PC und Betriebssystem durchaus zum Flaschenhals werden. Dies sei hier an einem konkreten Beispiel erläutert:

Das OSMO kann SR von 7.5 MS/s und dann Werte zwischen 10MS/2 bis 100MS/s in Intervallen von 10MS/s bereitstellen, also z.B. 10, 20, 30, ... MS/s. Im Fall des 41m-Bandes müssen also 20MS/s gewählt werden. Damit geht sich auch das 31m-Band noch knapp aus, währen man für das 25m-Band bereits auf 30MS/s umsteigen muss.

**Rechenleistung / CPU:**

Die Rechenleistung kann meist von modernen PCs ohne große Probleme aufgebracht werden. Allerdings ist die optimale Situation gegeben, wenn das Verhältnis zwischen der SR des Dongles und der SR der IQ-Datei eine ganzzahlige Potenz von 2 ist, d. h. 2<sup>N</sup>. Unter dieser
Bedingung können Signale bis zu 5 MHz in der Regel selbst unter Windows problemlos wiedergegeben werden. So sind z. B. MW-Dateien
mit 1250 kS/s und 16 BpS in der Regel gut geeignet.
Bei Abtastraten, die nicht der oben genannten Regel entsprechen (z. B. 500 kS/s), kann das vom COHIWizard für das Umcodieren benutzte ffmpeg langsamer werden und die Pipeline kann blockieren/abstürzen. Auch Aufnahmen mit höhere Auflösungen als 16 Bit (24 und 32 fps) haben sich als problematisch erwiesen.
Wenn die SR niedrig genug ist (z. B. 250 kS/s für LW), treten praktisch nie Probleme auf, selbst wenn sie nicht der 2<sup>N</sup>-Regel entspricht.

Die Probleme können durch Ausschalten der Spektralüberwachung reduziert werden, aber dann funktioniert die Lautstärkeanzeige nicht
mehr, sodass Sie die Verstärkung nur noch „blind“ einstellen können.

**Betriebssystem:**

Generell hat sich der Betrieb des COHIWizard unter LINUX als deutlich stabiler erwiesen als unter Windows. Das zeigt sich deutlich beim Abspielen von KW-Aufzeichnungen. Die folgenden Beobachtungen wurden auf einem Lenovo T590 mit Intel Core i7 mit 32GB Arbeitsspeicher gemacht:

WINDOWS 10/11:

Aufnahmen des 49m-Bandes mit LO um 6 kHz (d. h. Zielabtastrate 20 MS/s) kamen immer wieder mal zum Stillstand, insbesondere beim Lesen von einer externen Festplatte über einen USB-Hub, an den auch der fl2k-Dongle angeschlossen ist. Beim Lesen von der internen SSD konnten gab es bei 20MS/s meist keine Probleme, vorausgesetzt, die ursprüngliche SR beträgt 250 oder 500 kS/s. 

Wenn für die Aufnahme jedoch z.B. ein RSP1a/SDRUno im 49-m-Band verwendet worden war, so führt die von diesem Gerät verwendete SR
333,3 kS/s regelmäßig zu Problemen. Solche Aufzeichnungen sollten daher immer auf z. B. 500 kS/s oder 250 kS/s resampelt werden. Letzteres führt allerdings zu einer Beschneidung des Bandes.
Aufnahmen des 41m- und 31m-Bandes konnten selten ohne Stottern und/oder Abbrüche wiedergegeben werden. In der Regel bleibt der COHIWizard nach einiger
Zeit der Wiedergabe hängen und muss neu gestartet werden.



LINUX (Debian 12 und 13):

Aufnahmen bis ins 31m-Band konnten problemlos über längere Zeit abgespielt werden, auch von einer externen Festplatte und bei eingeschaltetem Spektrum-Monitor. Wiedergabe des 25-m-Bandes (30MS/s) gelangen jedoch nicht ohne Stottern.

Bei LW- und MW-Aufnahmen wurden nie irgendwelche Probleme beobachtet.


### Perfomance bei Raspberry als Steuercomputer

Läßt man den COHIWizard auf einem Raspberry-Pi5 mit 8GB Ram laufen, so können MW- und LW-Aufnahmen praktisch immer problemlos abgespielt werden. Bereits im 49m-Band kommt es aber typischerweise zu Stottern und Flattern, i.e. die Daten können entweder nicht schnell genug umgerechnet werden oder die Übertragung über USB klemmt.

So praktisch der Raspberry-Pi als Standalone-Gerät natürlich ist, so begrenzt ist er leider bezüglich der handlebaren AM-Bänder bei Betrieb des OSMO-fl2k.