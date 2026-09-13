# Upstream submission notes

Target repository: https://github.com/EPMatt/awesome-ha-blueprints

Proposed PR title:

Add washing machine finished notification blueprint

Proposed PR body:

This adds a beginner-friendly washing-machine finished notification automation.

The blueprint:
- detects a real wash cycle using a configurable power threshold;
- stores the running state in an input_boolean helper;
- only sends a notification after power remains below the finished threshold for a configurable time;
- prevents standby false positives;
- uses selectors for all required user inputs;
- includes documentation, requirements, tuning guidance, and a changelog.

The original version is already published and discussed in the Home Assistant Community:
https://community.home-assistant.io/t/simple-washing-machine-finished-notification-power-sensor-helper-beginner-friendly/1024799

I intentionally kept the first submission focused and understandable for beginners rather than adding appliance-diagnostic features or extra branches.
