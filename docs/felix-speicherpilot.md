# Felix SpeicherPilot – PV battery + dynamic tariff planning for Home Assistant

A beginner-friendly WATTZAHLS.DE tool for combining **battery SOC, PV forecast, expected consumption, charging efficiency and dynamic electricity prices**.

The goal is deliberately simpler than a full energy optimizer:

- don't charge a home battery from the grid just because one hour is cheap;
- include charging losses;
- compare the cheap price with the price that would otherwise be paid later;
- leave space for expected PV generation;
- calculate a sensible target SOC instead of always charging to 100%;
- generate a Home Assistant YAML starting point with placeholder entities.

## Free calculator

**Felix SpeicherPilot:**  
https://wattzahls.de/speicherpilot.html

German UI, but the calculation logic and units are universal.

## Home Assistant guide

**Batteriespeicher mit Home Assistant automatisch laden:**  
https://wattzahls.de/home-assistant-batteriespeicher-laden.html

The guide explains which entities are typically required and how the decision logic can be translated into an automation.

## Basic calculation idea

A simple approximation for the effective cost of energy stored in the battery is:

```text
effective_charge_price = cheap_grid_price / charging_efficiency
price_advantage = later_grid_price - effective_charge_price
```

Example:

```text
cheap price:       18 ct/kWh
charging efficiency: 92 %
later price:       32 ct/kWh

18 / 0.92 = about 19.6 ct/kWh effective charge price
32 - 19.6 = about 12.4 ct/kWh price spread
```

This is intentionally a planning model, not a universal economic guarantee. Real tariffs, taxes/fees, battery characteristics, cycle costs and manufacturer limits can change the result.

## Target-SOC idea

Instead of blindly charging to 100%, the SpeicherPilot uses a simple model:

1. Keep a configurable minimum reserve.
2. Estimate the remaining energy need after expected PV.
3. Add only the battery energy needed to cover that gap.
4. Cap the result at a configurable maximum grid-charging SOC.

That means the same system may charge higher on a dark winter day and not grid-charge at all before a sunny day.

## Home Assistant architecture

Typical inputs:

```text
sensor.speicher_soc
sensor.pv_prognose_morgen
sensor.strompreis_aktuell
sensor.strompreis_spaeter
```

Typical controllable entities, depending on the inverter/battery integration:

```text
number.speicher_ziel_soc
switch.speicher_netzladen
```

These are placeholders. Actual entity IDs and supported write actions vary by manufacturer and integration.

## Why this exists

Advanced solutions such as EMHASS and MILP-based energy managers are powerful, but many beginners first need a transparent answer to a simpler question:

> "My battery is at 30%, tomorrow looks cloudy, electricity is cheap tonight – how far should I charge?"

The Felix SpeicherPilot is intended as that understandable first layer.

## Related WATTZAHLS.DE articles

- PV-Speicher nachts laden: https://wattzahls.de/pv-speicher-nachts-laden.html
- Dynamischer Stromtarif + Batteriespeicher: https://wattzahls.de/dynamischer-stromtarif-batteriespeicher.html
- Solar overview: https://wattzahls.de/solar.html

## Safety / compatibility

Only enable grid charging if the battery or inverter manufacturer supports it. Do not bypass battery limits, warranty conditions or safety settings.

**WATTZAHLS.DE principle:** Verstehen. Testen. Dann automatisieren.
