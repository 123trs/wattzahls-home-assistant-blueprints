# Roller Shutter Heat Protection - temperature + sun elevation, beginner friendly

I wanted a simple summer heat-protection blueprint that does not close a roller shutter just because the outside temperature is high.

This blueprint checks two things:

1. Outside temperature is above the configured threshold.
2. Sun elevation is above the configured threshold.

Only when both conditions are true, the roller shutter moves to the selected heat-protection position.

## Why use sun elevation too?

A simple "temperature above 25 C = close shutter" automation can react even when the sun is already low or the window is no longer strongly exposed.

Using sun elevation as a second condition makes the automation more selective while still keeping it easy to understand.

## Requirements

- Outside temperature sensor
- Cover entity with position control
- Home Assistant Sun integration

## Suggested starting values

- Temperature above: **25 C**
- Sun elevation above: **20 degrees**
- Cover position: **30 %**

These values are only a starting point. The best settings depend on window direction, shading and the building.

## Blueprint

[Import Blueprint](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2F123trs%2Fwattzahls-home-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Frollladen-hitzeschutz.yaml)

[German beginner guide](https://wattzahls.de/home-assistant-blueprints.html)

## More beginner-friendly examples

If you prefer to first see and modify a plain Home Assistant automation before using a blueprint, I also made a free browser-based YAML generator with simple examples:

https://wattzahls.de/home-assistant-automation-generator.html

The broader German beginner series explains the same building blocks step by step with AI/ChatGPT as a helper:

https://wattzahls.de/home-assistant-mit-ki.html

Feedback is welcome. My goal is to keep the blueprint simple enough that a Home Assistant beginner can still understand every condition and action.
