# Free Home Assistant YAML Generator - 10 simple automation templates, beginner friendly

I built a small browser-based generator for people who are learning Home Assistant automations and want to understand the YAML rather than just copy a large example blindly.

The idea is intentionally simple:

1. Pick an automation template.
2. Enter your own entity IDs and values.
3. Generate the YAML locally in the browser.
4. Review it, copy it into Home Assistant and test it.

There is no login and the entity IDs are not sent to a server.

## Current templates

- Motion -> light, with time window and optional lux threshold
- Window open -> heating off
- Door left open -> mobile notification
- Motion light with manual override
- Cover / awning by sunrise or sunset
- Switch off standby consumers below a power threshold
- Circulation pump on demand
- Washing machine finished notification
- Roller shutter heat protection
- Dimmed night light on motion

## Generator

https://wattzahls.de/home-assistant-automation-generator.html

## Why I made it

Home Assistant's UI is already very capable, but when beginners look at YAML for the first time, triggers, conditions and actions can still feel abstract. The generator is meant as a learning bridge: you can change one value, generate again and immediately see what changed in the YAML.

It is not intended to replace Home Assistant's automation editor, and generated automations should always be reviewed and tested with your own entities.

For unusual logic I also use ChatGPT as a helper after the basic automation exists. The related German beginner series is here:

https://wattzahls.de/home-assistant-mit-ki.html

Feedback is welcome, especially ideas for small automation templates that are useful in everyday life but still easy for beginners to understand.
