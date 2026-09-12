# Simple Night Light on Motion - time window + dimmed light, beginner friendly

I wanted a very simple night-light blueprint for hallways, bathrooms or bedrooms.

The idea is intentionally small:

1. Motion is detected.
2. The automation checks whether the current time is inside the configured night window.
3. The light turns on at a low brightness.
4. The automation waits until motion stops.
5. After the configured delay, the light turns off again.

## Why a separate night-light blueprint?

A normal motion-light automation often uses the same brightness all day.

At night, that can be much too bright. This blueprint keeps the logic easy to understand while giving the night period its own low brightness.

## Requirements

- Motion or occupancy sensor
- Dimmable light

## Suggested starting values

- Start time: **22:00**
- End time: **06:00**
- Brightness: **10 %**
- Off delay: **45 seconds**

The time window can cross midnight.

## Blueprint

[Import Blueprint](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2F123trs%2Fwattzahls-home-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fnachtlicht-bei-bewegung.yaml)

[German beginner guide](https://wattzahls.de/home-assistant-blueprints.html)

Feedback is welcome. My goal is to keep this blueprint small enough that a Home Assistant beginner can understand every step.
