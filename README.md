# TabScrub

Three-finger touchpad tab scrubbing for Chrome on Linux, like on a Chromebook.

Slide three fingers left or right on the touchpad. The tab you would land on lights up in the tab strip while you keep sliding, and it opens when you lift your fingers. Swipe faster to move through more tabs. It stops at the first and last tab instead of wrapping around.

## How it works

Chrome extensions cannot see touchpad swipes, so TabScrub has three small parts:

1. **Gesture** – a Lua gesture in the Hyprland config that tracks finger movement.
2. **Helper** – a tiny local Python service that passes gesture events along.
3. **Chrome extension** – highlights the target tab (`chrome.tabs.highlight`) and opens it on release.

## Requirements

- Linux with [Hyprland](https://hypr.land) 0.55 or newer (Lua config)
- Google Chrome (or a Chromium-based browser)
- Python 3, curl, systemd (user services)

## Status

Early version, works on the author's Arch Linux + Hyprland laptop. Install files and instructions coming soon.

## Tuning

`PX_PER_TAB` (sensitivity), `ACCEL` (speed boost) and `INVERT` (direction) are set at the top of the gesture block.
