# Standby-Strom messen und mit Home Assistant sinnvoll automatisieren

Eine Automation wie „unter 3 Watt → Steckdose aus“ ist nur dann sinnvoll, wenn der Leistungswert vorher **gemessen und verstanden** wurde.

## 1. Erst die Grundlast bestimmen

Am besten nachts oder in einer ruhigen Phase beobachten, wie hoch der stabile Hausverbrauch ist. Kühlschrank, Router, NAS, Switches, Smart-Home-Zentralen, Pumpen und andere Dauerverbraucher gehören dabei zur echten Grundlast und sind nicht automatisch „unnötiger Standby“.

## 2. Stromkreis eingrenzen

Bei unerwartet hoher Grundlast Stromkreise nacheinander abschalten und beobachten, in welchem Bereich der Verbrauch deutlich fällt. So lässt sich die Suche auf Küche, Unterhaltungselektronik, Büro, Keller usw. eingrenzen.

## 3. Steckbare Geräte einzeln messen

Ein Energiekostenmessgerät oder eine Messsteckdose liefert bessere Werte als Schätzungen. Bei zyklischen Verbrauchern wie Kühlschrank oder Gefriergerät nicht nur einen Momentwert ablesen, sondern über einen längeren Zeitraum messen.

Typische Gruppen, die sich summieren:

- TV + Receiver + Soundbar + Subwoofer
- PC-Netzteile + Monitore + Dockingstation
- Kaffeemaschine / Kaffeevollautomat
- Drucker
- ältere Ladegeräte und Netzteile
- aktive Lautsprecher
- Smart-Home- und Netzwerkgeräte

## 4. Erst danach automatisieren

Für Home Assistant kann eine Messsteckdose z. B. abschalten, wenn die Leistung lange genug unter einem sicheren Grenzwert liegt. Das eignet sich **nur für Geräte, die gefahrlos hart vom Strom getrennt werden dürfen**.

Nicht dafür verwenden: PCs, NAS, Speichergeräte oder andere Geräte, die einen geregelten Shutdown brauchen.

Ausführliche Messanleitung:

https://wattzahls.de/stromverbrauch-messen.html

Standby-Kosten direkt berechnen:

https://wattzahls.de/standby-kosten-rechner.html

YAML-Automationen erzeugen:

https://wattzahls.de/home-assistant-automation-generator.html

## Grundsatz

**Messen → verstehen → erst dann automatisieren.**
