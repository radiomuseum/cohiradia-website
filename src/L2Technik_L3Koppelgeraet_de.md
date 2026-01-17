---
title: Koppelgeräte
---

# Allgemeines und Gefahrenhinweise

**ACHTUNG**: Der Antenneneingang vieler alter Röhrenempfänger ist häufig keineswegs berührungssicher im Sinne moderner Sicherheitsforschriften für elektrische Geräte. 
Bei sogenannten Allstromgeräten liegt bekanntermaßen das Chassis an einem der Leiter des Netzsteckers und ist somit nach dem Anstecken ans Netz je nach Einsteckrichtung 
entweder mit dem Nullleiter oder dem Phasenleiter verbunden. Es kann demnach gegen Erde eine Spannung von 230V in Europa annehmen. Normalerweise sind zwar die Eingänge für 
Erde und Antenne durch Kondensatoren vom Chassis und damit damit galvanisch gekoppelten Teilen getrennt, aber der vergleichsweise hohen Kapazitäten können sie durchaus merkliche Ströme bei Netzfrequenz übertragen. So ergeben z.B. 10nF bei 230V und 50Hz etwa 0.72 mA Strom. Das ist bei Berührung jedenfalls bereits fühlbar. An den unbelasteten Eingängen  kann jedenfalls die Netzspannung anliegen. 

Bei Direktanschluss der Erdungsbuchse an den Schutzleiter-Kontakt einer Steckdose kann bei einigen Modellen sogar der FI-Schalter ausgelöst werden, was auf deutlich größere Kapazitäten oder gar defekte Koppelelemente hinweist. Auch bei anderen Geräten kann es aufgrund parasitärer Kapazitäten zwischen Netz und Röhrenkreis zu durchaus hohen Wechselspannungen gegen Erde kommen. 

Wie in [anderen Artikeln](https://www.radiomuseum.org/forum/radios_mit_gefaehrlicher_stromversorgung.html?language_id=1) des RM ausführlich behandelt, sollten solche Radios nicht leichtfertig ans Netz geschlossen werden, optimal wäre ein Schutz-Trenntrafo. 

Aufgrund dieser Sachlage **wird ausdrücklich davon abgeraten, den Ausgang des Signalwandlers (STEMLAB, fl2k-Dongle, ...) direkt mit dem Antenneneingang zu verbinden**. Dabei kann nicht nur der Signalwandler beschädigt oder zerstört werden, sondern es ist auch für damit hantierende Personen gefährlich, entsprechende leitfähige Teile zu berühren. Abhilfe schafft ein Hf‐Trenntransformator mit geeignetem Übersetzungsverhältnis vom 50 $\Omega$‐Ausgang des STEMLAB auf das Radio. Üblicherweise funktioniert eine Impedanztransformation 1:9 bis 1:16 (Windungsverhältnis 1:3 bzw. 1:4) für typische Röhrengeräte.

Bei Radiogeräten, die entweder über Ferritantennen oder Rahmenantennen verfügen ist eine rein induktive Ankopplung über eine Sendespule und eine geeignete Treiberstufe bei niedriger Sendeleistung (Einhaltung der Bestimmungen für Störstrahlung !) möglich.

# Kopplung durch Hf-Transformatoren

Dabei ist aber zu beachten, dass der Trafo ausreichende Isolationsfestigkeit zwischen (treiberseitiger) Primär- und (radioseitiger) Sekudärseite hat. Gut eignen sich Ringkernübertrager, bei denen die Sekundärseite mit kunststoffisoliertem Draht ausgeführt ist, bei dem die Isolierung der Netzspannung verläßlich standhält. Der Draht kann im Dienste einer guten magnetischen Kopplung dünn sein, da hier keine nennenswerten Ströme übertragen werden.

Die Primärseite kann aus kupferlackisoliertem Draht bestehen. Diese Isolierstrategie wird deshalb empfohlen, weil viele gängige Ferritkerne einen gewisse elektrischische Leitfähigkeit aufweisen, und somit bei schadhafter Isolierung keine ausreichende galvanische Trennung besteht.  

Es ist jedenfalls darauf zu achten, dass die beiden Wicklungen vollständig galvanisch getrennt sind, und keine gemeinsame Masse besitzen. Auf diese Details sollte man insbesondere achten, wenn man kommerziell erhältliche Baluns oder Ununs aus der Amaterufunktechnik verwenden möchte. 

Als Ferrite eignen sich generell solche, die den von Amidon gelisteten Materialien 77 (LW,MW) und 43 (funktioniert auch gut für KW-Bänder) entsprechen. Einer bequemen Baugröße ist z.B. FT114 oder FT140. 

Erfolgreiche Anwendung fanden z.B. Übertrager mit 43/FT114-Ringkern und einem Windungsverhältnis 15 : 60 an einem Minerva375A und an einem Hornyphon W248U. Aber auch 43/FT114 mit 15 : 30 funktioniert noch brauchbar. Damit wurden LW, MW und auch KW auf 49m erfolgreich eingekoppelt. F. Wolf berichtet über einen Ringkern FT240/77, Windungsverhältnis 10 : 30, der erfolgreich an einem LOEWE Opta‐Kantate mit mit einem amplitudenmodulierten Signalgenerator RF1 von HEATHKIT und einem CD‐Player. Das Ergebnis wurde als sehr zufriedenstellend eingestuft.

G. Gauert berichtet, dass bei einigen alten Geräten die Antenne erheblich zur Resonatorkapazität beiträgt und daher die bloße Ankopplung des Signalwandlers über einen Transformator zu unerwünschten Dämpfungen und Frequenzverschiebungen des Abstimmkreises führen kann. Auch erhebliche Signalstörungen können die Folge sein. Diese Erkenntnisse konnte H. Scharfetter mit einem Atwaterkent 10 aus dem Jahr 1924 bestätigen. In solchen Fällen empfiehlt es sich im MW-Band, eine Serie aus einem 220pF‐Kondensator und einem Widerstand (470 - 2200 $\Omega$) zwischen den Trafo‐Ausgang und den Antenneneingang des Radios zu schalten. Diese Maßnahme kann das Problem in der Regel beheben oder zumindest signifikant abmildern.

# Induktive Kopplung 
