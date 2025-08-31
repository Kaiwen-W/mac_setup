# GUI Apps:

## Firefox Developer Edition

Extensions

- Easy Screenshot
- React Developer Tools
- uBlock Origin

## Spotify

To disable spotify ads on the client side app:

- `bash <(curl -sSL https://raw.githubusercontent.com/SpotX-Official/SpotX-Bash/main/spotx.sh)`
- https://github.com/SpotX-Official/SpotX-Bash/tree/main

# Add-on / Helper Apps:

For all of the following:

- Start at login -> On
- Show in menubar -> On

## AltTab

Controls

- Shortcut 1

  - Trigger shortcut -> Hold `cmd` and press `Tab`
  - After release -> Focus selected window

  - Show windows from applications -> All apps
  - Show windows from Spaces -> All Spaces
  - Show windows from screens -> Screen showing AltTab
  - Show minimized windows -> Show at the end
  - Show hidden windows -> Show at the end
  - Show fullscreen windows -> Hide
  - Order windows by -> Recently Focused First

- Shortcut 2

  - Trigger shortcut -> Hold `cmd` and press `\``
  - After release -> Focus selected window

  - Show windows from applications -> All apps
  - Show windows from Spaces -> All Spaces
  - Show windows from screens -> All Screens
  - Show minimized windows -> Show at the end
  - Show hidden windows -> Show at the end
  - Show fullscreen windows -> Show
  - Order windows by -> Recently Focused First

- Shortcut 3

  - Trigger shortcut -> Hold `opt` and press `Tab`
  - After release -> Focus selected window

  - Show windows from applications -> Active app
  - Show windows from Spaces -> All Spaces
  - Show windows from screens -> All Screens
  - Show minimized windows -> Show
  - Show hidden windows -> Show
  - Show fullscreen windows -> Show
  - Order windows by -> Recently Focused First

## Amphetamine

Session Defaults

- Default Duration -> Indefinitely
- Forced Sleep -> On, End session when Mac is forced to sleep
- Display Sleep -> On, Allow display sleep
- Closed-Display Mode -> Off, Allow system sleep when display is closed

## DockDoor

General

- Enable Window Switcher -> Off
- Performance Profile -> Snappy

## Karabiner-Elements

Simple Modifications

- For all devices
  - Modifier keys / caps_lock -> Modifier keys / left_option
- 75% knob keyboard
  - Media controls / mute -> Media controls / play_or_pause

Function Keys

- For all devices
  - f1 -> Media controls / display_brightness_decrement
  - f2 -> Media controls / display_brightness_increment
  - f3 -> Media controls / mission_control
  - f4 -> Function keys / f4
  - f5 -> Function keys / f5
  - f6 -> Function keys / f6
  - f7 -> Media controls / rewind
  - f8 -> Media controls / play_or_pause
  - f9 -> Media controls / fast_forward
  - f10 -> Media controls / mute
  - f11 -> Media controls / volume_decrement
  - f12 -> Media controls / volume_increment

Complex Modifications

- Disable cmd+ctrl+opt+shift+. which triggers sys diagnose
  ```
  {
      "description": "Disable command+control+option+shift+. which triggers sysdiagnose",
      "manipulators": [
          {
              "from": {
                  "key_code": "period",
                  "modifiers": { "mandatory": ["command", "control", "option", "shift"] }
              },
              "to": [{ "key_code": "f16" }],
              "type": "basic"
          }
      ]
  }
  ```
- Disable cmd+ctrl+opt+shift+, which triggers WiFi logging
  ```
  {
      "description": "Disable command+control+option+shift+, which triggers WiFi logging.",
      "manipulators": [
          {
              "from": {
                  "key_code": "comma",
                  "modifiers": { "mandatory": ["command", "control", "option", "shift"] }
              },
              "to": [{ "key_code": "f17" }],
              "type": "basic"
          }
      ]
  }
  ```
- Change right_cmd to cmd+ctrl+opt+shift (hyper key)
  ```
  {
      "manipulators": [
          {
              "description": "Change right_command to command+control+option+shift.",
              "from": {
                  "key_code": "right_command",
                  "modifiers": { "optional": ["any"] }
              },
              "to": [
                  {
                      "key_code": "left_shift",
                      "modifiers": ["left_command", "left_control", "left_option"]
                  }
              ],
              "type": "basic"
          }
      ]
  }
  ```

## Linear Mouse

#### Following settings refer to an **EXTERNAL MOUSE** and not the internal trackpad

Scrolling

- Reverse scrolling -> Off
- Modifier Keys
  - Command -> Change Speed (5.00 x)
  - Shift -> Alter Orientation
  - Option -> Zoom

Pointer

- Disable pointer acceleration -> On

Buttons

- Enable universal back and forward -> On

## Raycast

During Onboarding

- Turn off AI Features
- Download the reminders extension

General

- Raycast Hotkey -> `cmd + Space`
- Text Size -> Small
- Window Mode -> Compact

Extensions (`hyper` refers to `ctrl+opt+shift+cmd`)

- Applications
  - Arc -> `hyper + F`
  - Finder -> `hyper + J`
  - Firefox Developer Edition -> `hyper + R`
  - Ghostty -> `hyper + A`
  - Microsoft Word -> `hyper + E`
  - Notion -> `hyper + D`
  - Passwords -> `hyper + P`
  - Preview -> `hyper + W`
  - Spotify / Music -> `hyper + M`
  - Visual Studio Code -> `hyper + S`
- Clipboard History -> `hyper + L`
- Search Files -> `hyper + K`
- Window Switcher
  - Bottom Half -> `ctrl + opt + down arrow`
  - Bottom Left Quarter -> `ctrl + opt + H`
  - Bottom Right Quarter -> `ctrl + opt + T`
  - First Third -> `ctrl + opt + D`
  - First Two Thirds -> `ctrl + opt + F`
  - Last Third -> `ctrl + opt + R`
  - Last Two Thirds -> `ctrl + opt + N`
  - Left Half -> `ctrl + opt + left arrow`
  - Maximize -> `ctrl + opt + enter`
  - Next Display -> `ctrl + opt + cmd + right arrow`
  - Previous Display -> `ctrl + opt + cmd + left arrow`
  - Right Half -> `ctrl + opt + right arrow`
  - Toggle Fullscreen -> `ctrl + opt + \`
  - Top Half -> `ctrl + opt + up arrow`
  - Top Left Quarter -> `ctrl + opt + G`
  - Top Right Quarter -> `ctrl + opt + C`
