# WATTZAHLS.DE – Home Assistant Blueprints

**Kostenlose Home-Assistant-Blueprints, YAML-Automationen und Schritt-für-Schritt-Anleitungen für Einsteiger.**  
Alle Beispiele stammen aus echter Smart-Home-Praxis und sind so aufgebaut, dass man nicht nur kopiert, sondern versteht, was passiert.

➡️ **Blueprints & Anleitung:** https://wattzahls.de/home-assistant-blueprints.html  
➡️ **Home Assistant mit KI & ChatGPT – kompletter Einsteigerkurs:** https://wattzahls.de/home-assistant-mit-ki.html  
➡️ **Home Assistant Automation mit ChatGPT erstellen:** https://wattzahls.de/home-assistant-automation-chatgpt.html  
➡️ **Kostenloser Home Assistant YAML Generator:** https://wattzahls.de/home-assistant-automation-generator.html  
➡️ **Eigene Home Assistant Custom Integration mit ChatGPT erstellen:** https://wattzahls.de/home-assistant-custom-integration-chatgpt.html  
➡️ **Felix Speicherkapitän – PV-Speicher + dynamischer Tarif + HA-YAML:** https://wattzahls.de/speicherkapitaen.html

## Schnellstart

| Lösung | Wofür? | Direkt |
|---|---|---|
| 🌙 Nachtlicht | Bewegung + Zeitfenster + Helligkeit + Nachlauf | Blueprint unten importieren |
| 🧺 Waschmaschine fertig | Meldung nach echtem Waschgang statt Standby-Fehlalarm | Blueprint unten importieren |
| ☀️ Rollladen Hitzeschutz | Temperatur + Sonnenhöhe + Zielposition | Blueprint unten importieren |
| 💬 ChatGPT Automation | Wunsch in Alltagssprache planen, mit echten Entity-IDs und Test-Workflow | https://wattzahls.de/home-assistant-automation-chatgpt.html |
| ⚙️ YAML Generator | 10 einfache Automations-Rezepte ohne YAML-Frust | https://wattzahls.de/home-assistant-automation-generator.html |
| 🤖 Home Assistant mit KI | Vom ersten Start bis zu Automationen, Integrationen und Fehlersuche | https://wattzahls.de/home-assistant-mit-ki.html |
| 🔋 Felix Speicherkapitän | PV-Prognose, SOC und dynamischen Tarif zu Ziel-SOC + HA-YAML verbinden | https://wattzahls.de/speicherkapitaen.html |

Einfache, nachvollziehbare Home-Assistant-Blueprints aus der Praxis von **WATTZAHLS.DE**.

Die Vorlagen sind bewusst überschaubar gehalten: wenige Eingaben, klarer Zweck und keine unnötige Magie.

## 🌙 Nachtlicht bei Bewegung

Bewegungssensor und Licht auswählen, Nacht-Zeitfenster, Helligkeit und Nachlauf festlegen.

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2F123trs%2Fwattzahls-home-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fnachtlicht-bei-bewegung.yaml)

Quelle: https://wattzahls.de/blueprints/automation/wattzahls/nachtlicht-bei-bewegung.yaml

## 🧺 Waschmaschine fertig

Erkennt zuerst einen echten Waschgang und meldet anschließend zuverlässig „fertig“. Ein input_boolean verhindert Standby-Fehlmeldungen.

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2F123trs%2Fwattzahls-home-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fwaschmaschine-fertig.yaml)

Quelle: https://wattzahls.de/blueprints/automation/wattzahls/waschmaschine-fertig.yaml

## ☀️ Rollladen Hitzeschutz

Außentemperatur und Sonnenhöhe müssen gleichzeitig über den Grenzwerten liegen. Dann fährt der Rollladen auf die gewünschte Zielposition.

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2F123trs%2Fwattzahls-home-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Frollladen-hitzeschutz.yaml)

Quelle: https://wattzahls.de/blueprints/automation/wattzahls/rollladen-hitzeschutz.yaml
## 🔋 Felix Speicherkapitän

Der **Felix Speicherkapitän** ist unser kostenloses Werkzeug für PV-Speicher mit dynamischem Stromtarif. Er berechnet aus SOC, PV-Prognose, Verbrauch, Wirkungsgrad und Strompreisen ein sinnvolles Ziel-SOC und erzeugt anschließend ein Home-Assistant-YAML-Grundgerüst.

➡️ **Rechner:** https://wattzahls.de/speicherkapitaen.html  
➡️ **Technische Erklärung im Repo:** [docs/felix-speicherkapitaen.md](docs/felix-speicherkapitaen.md)  
➡️ **Home-Assistant-Anleitung:** https://wattzahls.de/home-assistant-batteriespeicher-laden.html

## Home Assistant Community

Die Waschmaschinen-Vorlage ist auch im offiziellen Home Assistant Blueprints Exchange veröffentlicht:

https://community.home-assistant.io/t/simple-washing-machine-finished-notification-power-sensor-helper-beginner-friendly/1024799

Die Rollladen-Hitzeschutz-Vorlage ebenfalls:

https://community.home-assistant.io/t/roller-shutter-heat-protection-temperature-sun-elevation-beginner-friendly/1024818

Der kostenlose Home Assistant YAML Generator wird in **Share your Projects!** vorgestellt:

https://community.home-assistant.io/t/free-home-assistant-yaml-generator-10-simple-automation-templates-beginner-friendly/1024901

Der **Felix Speicherkapitän** wird hier vorgestellt:

https://community.home-assistant.io/t/felix-speicherkapitan-pv-battery-dynamic-tariff-calculator-for-home-assistant/1025143

Diskussion zur Preis-/PV-Logik im Photovoltaikforum:

https://www.photovoltaikforum.com/thread/238861-stromspeicher-mit-dynamischen-g%C3%BCnstigem-netzstrom-laden-tibber-zu-hochpreis-phas/?postID=4877191#post4877191

## Anleitungen & kostenlose Werkzeuge

Ausführliche Erklärung und Einsteiger-Anleitung zu den Blueprints:

https://wattzahls.de/home-assistant-blueprints.html

Die komplette Serie **„Home Assistant mit KI & ChatGPT – ohne Vorkenntnisse“**:

https://wattzahls.de/home-assistant-mit-ki.html

Praxisanleitung: **Home Assistant Automation mit ChatGPT erstellen – ohne YAML-Vorkenntnisse**:

https://wattzahls.de/home-assistant-automation-chatgpt.html

Kostenloser **Home Assistant YAML Generator** mit Vorlagen für Licht, Heizung, Rollladen, Waschmaschine und mehr:

https://wattzahls.de/home-assistant-automation-generator.html

Praxisanleitung: **Home Assistant Custom Integration mit ChatGPT erstellen**:

https://wattzahls.de/home-assistant-custom-integration-chatgpt.html

Alle Home-Assistant-Integrationen einfach erklärt:

https://wattzahls.de/home-assistant-integrationen.html

## Weitere Praxis-Dokumente im Repo

- [Home Assistant Integrationen für Einsteiger](docs/home-assistant-integrationen-einstieg.md) – offizieller Weg zuerst, Custom Integration erst bei echtem Bedarf
- [Standby-Strom messen und mit Home Assistant automatisieren](docs/standby-strom-messen-und-automatisieren.md) – erst messen, dann Grenzwerte und Abschaltung bauen
- [Heizkennlinie optimieren: messen statt raten](docs/heizkennlinie-messen-statt-raten.md) – kleine Änderungen mit echten Messwerten bewerten

## Grundsatz

**Verstehen. Testen. Dann automatisieren.**

Die Vorlagen sollen Home Assistant leichter zugänglich machen. Sie ersetzen nicht das Prüfen der eigenen Geräte, Entitäten und Sicherheitsanforderungen.
