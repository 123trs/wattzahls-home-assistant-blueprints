# Simple Washing Machine Finished Notification – power sensor + helper, beginner friendly

I wanted a washing-machine notification blueprint that stays intentionally simple.

A lot of appliance blueprints are very powerful, but for beginners that can also mean a long list of options. This one does one job:

**Detect that the washing machine really started, then notify you when it is actually finished.**

## Why the helper?

A simple “power below 3 W = finished” automation can send false notifications while the appliance is just sitting in standby.

This blueprint therefore uses an input_boolean as a small memory:

1. Power rises above the **running threshold** → helper turns on.
2. Later, power stays below the **finished threshold** for the configured time.
3. Only if the helper is on, the notification is sent.
4. The helper is reset for the next cycle.

No templates, no custom integration, no extra dependency.

## Requirements

- A power sensor for the washing machine
- One input_boolean helper
- Home Assistant Companion App on the phone that should receive the notification

## Import

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2F123trs%2Fwattzahls-home-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fwaschmaschine-fertig.yaml)

**GitHub:**  
https://github.com/123trs/wattzahls-home-assistant-blueprints/blob/main/automation/waschmaschine-fertig.yaml

**German beginner guide / explanation:**  
https://wattzahls.de/home-assistant-blueprints.html

## Suggested starting values

- Running above: **10 W**
- Finished below: **3 W**
- Finished wait: **120 seconds**

Every appliance is different, so watch your power sensor for one complete cycle and adjust the two thresholds if necessary.

## Blueprint YAML

~~~yaml
blueprint:
  name: "WATTZAHLS.DE – Waschmaschine fertig"
  description: >
    Erkennt über die Leistungsaufnahme zuerst einen laufenden Waschgang und später
    das Ende. Ein input_boolean-Helfer verhindert Fehlmeldungen im normalen Standby.
    Anschließend wird eine Benachrichtigung an die Home-Assistant-Companion-App gesendet.
  domain: automation
  source_url: https://github.com/123trs/wattzahls-home-assistant-blueprints/blob/main/automation/waschmaschine-fertig.yaml
  author: WATTZAHLS.DE
  input:
    power_sensor:
      name: Leistungssensor
      description: Sensor mit der aktuellen Leistungsaufnahme der Waschmaschine in Watt.
      selector:
        entity:
          filter:
            domain: sensor
    running_helper:
      name: Helfer "Waschmaschine läuft"
      description: Ein input_boolean, der sich merkt, dass die Maschine wirklich gelaufen ist.
      selector:
        entity:
          filter:
            domain: input_boolean
    running_above:
      name: Startgrenze
      description: Oberhalb dieser Leistung gilt die Waschmaschine als gestartet.
      default: 10
      selector:
        number:
          min: 0.1
          max: 5000
          step: 0.1
          unit_of_measurement: W
          mode: box
    finished_below:
      name: Fertig-Grenze
      description: Unterhalb dieser Leistung kann der Waschgang als beendet gelten.
      default: 3
      selector:
        number:
          min: 0
          max: 500
          step: 0.1
          unit_of_measurement: W
          mode: box
    finished_wait:
      name: Fertig-Wartezeit
      description: So lange muss die Leistung unter der Fertig-Grenze bleiben.
      default: 120
      selector:
        number:
          min: 10
          max: 7200
          unit_of_measurement: seconds
          mode: box
    notify_device:
      name: Handy mit Home-Assistant-App
      description: Gerät, das die Fertig-Meldung erhalten soll.
      selector:
        device:
          filter:
            integration: mobile_app
    notification_title:
      name: Titel
      default: "Waschmaschine fertig"
      selector:
        text:
    notification_message:
      name: Nachricht
      default: "Die Waschmaschine ist fertig."
      selector:
        text:

mode: restart

triggers:
  - trigger: numeric_state
    entity_id: !input power_sensor
    above: !input running_above
    id: running
  - trigger: numeric_state
    entity_id: !input power_sensor
    below: !input finished_below
    for:
      seconds: !input finished_wait
    id: finished

conditions: []

actions:
  - choose:
      - conditions:
          - condition: trigger
            id: running
        sequence:
          - alias: "Laufenden Waschgang merken"
            action: input_boolean.turn_on
            target:
              entity_id: !input running_helper
      - conditions:
          - condition: trigger
            id: finished
          - condition: state
            entity_id: !input running_helper
            state: "on"
        sequence:
          - alias: "Fertig-Meldung senden"
            domain: mobile_app
            type: notify
            device_id: !input notify_device
            title: !input notification_title
            message: !input notification_message
          - alias: "Lauf-Helfer zurücksetzen"
            action: input_boolean.turn_off
            target:
              entity_id: !input running_helper
~~~

## More beginner-friendly examples

If you prefer to first see and modify a plain Home Assistant automation before using a blueprint, I also made a free browser-based YAML generator with simple examples:

https://wattzahls.de/home-assistant-automation-generator.html

The broader German beginner series explains the same building blocks step by step with AI/ChatGPT as a helper:

https://wattzahls.de/home-assistant-mit-ki.html

Feedback is welcome, especially from people using different washing machines or smart plugs. My goal with this blueprint is to keep it small enough that a Home Assistant beginner can still understand every step.
