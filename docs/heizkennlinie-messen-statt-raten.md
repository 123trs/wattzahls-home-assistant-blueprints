# Heizkennlinie optimieren: messen statt raten

Eine Heizkennlinie sollte nicht nach Gefühl verstellt werden. Sinnvoller ist ein kleiner, kontrollierter Zyklus aus **messen → ändern → beobachten**.

## Welche Werte helfen?

Für eine erste Beurteilung sind besonders nützlich:

- Außentemperatur
- Vorlauftemperatur
- Rücklauftemperatur
- Raumtemperatur
- Brennerlaufzeiten bzw. Starts
- Pumpenstatus
- gewünschte Raumtemperatur

Mit Home Assistant lassen sich diese Werte gut gemeinsam darstellen und über mehrere Tage vergleichen.

## Neigung und Niveau nicht gleichzeitig ändern

Wenn zwei Parameter gleichzeitig verändert werden, ist später kaum noch erkennbar, welche Änderung wirklich geholfen hat.

Ein einfacher Ansatz:

1. Ausgangszustand dokumentieren.
2. Nur **eine** kleine Änderung vornehmen.
3. Mehrere Heizphasen beobachten.
4. Komfort und Temperaturen vergleichen.
5. Erst danach weiter optimieren.

## Typisches Ziel

Die Vorlauftemperatur soll so niedrig wie möglich sein, ohne dass die gewünschten Raumtemperaturen verfehlt werden. Zu hohe Vorlauftemperaturen kosten Effizienz, zu niedrige Werte führen zu Komfortproblemen.

Unser Rechner hilft, Neigung und Niveau verständlich einzuordnen:

https://wattzahls.de/heizkennlinie-rechner.html

Praxis mit echten Messwerten:

https://wattzahls.de/heizkurve-praxis.html

## Grundsatz

**Nicht fünf Dinge gleichzeitig ändern. Kleine Schritte liefern die besseren Antworten.**
