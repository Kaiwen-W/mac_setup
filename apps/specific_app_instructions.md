# GUI Apps:

## Arc

Extensions

- AdBlockPlus - free ad blocker
- Dark Reader
- Google Translate
- JSON Formatter
- Refined GitHub
- uBlock
- Untrap for YouTube: https://chromewebstore.google.com/detail/untrap-for-youtube-%E2%80%94-bloc/enboaomnljigfhfjfoalacienlhjlfil
- Social Focus: https://chromewebstore.google.com/detail/socialfocus-%E2%80%94-hide-feeds/abocjojdmemdpiffeadpdnicnlhcndcg

Settings

- General
  - Sync Sidebar -> On
  - Automatically update my Arc -> On
- Links
  - Open Little Arc when I press `opt + cmd + N` in any app -> Off
  - Open Little Arc when clicking on links with `opt + cmd` held -> Off
  - Links from other apps open in Little Arc -> Off
- Shortcuts

  - Show/Hide Sidebar -> `cmd + \`

- Icon -> Candy Arc

- Advanced

  - Play Arc sound effects -> Off
  - Haptic feedback when reordering tabs -> Off

  - When opening Arc, restore windows from previous session -> On

## Firefox Developer Edition

Extensions

- Easy Screenshot
- React Developer Tools
- uBlock Origin

## Spotify

To disable spotify ads on the client side app:

- `bash <(curl -sSL https://raw.githubusercontent.com/SpotX-Official/SpotX-Bash/main/spotx.sh)`
- https://github.com/SpotX-Official/SpotX-Bash/tree/main

## Obsidian
Create a new folder called 'Obsidian Vault' in Documents. 

`git clone https://github.com/Kaiwen-W/obsidian-notes.git`


# Add-on / Helper Apps:

For all of the following:

- Start at login -> On
- Show in menubar -> On

## AltTab

Appearance -> Size -> Medium

Controls

- Shortcut 1

  - Trigger shortcut -> Hold `cmd` and press `Tab`
  - After release -> Focus selected window

  - Show windows from applications -> All apps
  - Show windows from Spaces -> All Spaces
  - Show windows from screens -> All Screens
  - Show minimized windows -> Show at the end
  - Show hidden windows -> Show at the end
  - Show fullscreen windows -> Show
  - Order windows by -> Recently Focused First

- Shortcut 2

  - Trigger shortcut -> Hold `opt` and press `Tab`
  - After release -> Focus selected window

  - Show windows from applications -> Active app
  - Show windows from Spaces -> All Spaces
  - Show windows from screens -> All Screens
  - Show minimized windows -> Show
  - Show hidden windows -> Show
  - Show fullscreen windows -> Show
  - Order windows by -> Recently Focused First

#### For all of the above (change to dvorak): Shortcuts when active... ->

- Close window -> ,
- Fullscreen/Defullscreen window -> Enter
- Quit app -> '
- Hide/Show app -> D


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
- Cmd+Opt+Ctrl+Shift + F1/F2 for keyboard brightness
  ```
  {
    "description": "Cmd+Opt+Ctrl+Shift + F1/F2 for keyboard brightness",
    "manipulators": [
        {
            "from": {
                "key_code": "f1",
                "modifiers": { "mandatory": ["left_command", "left_option", "left_control", "left_shift"] }
            },
            "to": [{ "key_code": "illumination_decrement" }],
            "type": "basic"
        },
        {
            "from": {
                "key_code": "f2",
                "modifiers": { "mandatory": ["left_command", "left_option", "left_control", "left_shift"] }
            },
            "to": [{ "key_code": "illumination_increment" }],
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
- Use Raycast Emoji Picker

General

- Raycast Hotkey -> `cmd + Space`
- Text Size -> Small
- Window Mode -> Compact
- Favorites -> Show favourites in compact mode -> Off

Extensions (`hyper` refers to `ctrl+opt+shift+cmd`)

- Applications
  - Arc -> `hyper + F`
  - Finder -> `hyper + J`
  - Comet -> `hyper + R`
  - Ghostty -> `hyper + A`
  - Microsoft Word -> `hyper + E`
  - Obsidian -> `hyper + D`
  - Passwords -> `hyper + P`
  - Preview -> `hyper + W`
  - Spotify / Music -> `hyper + M`
  - Visual Studio Code -> `hyper + S`
  - Reminders -> `hyper + R`
  - Microsoft Outlook -> `hyper C`
  - Slack -> `hyper ;`
  - Discord -> `hyper T`
- Clipboard History -> `hyper + L`
- Search Files -> `hyper + K`
- Window Switcher - note that the letter ones refer to the Dvorak keyboard layout
  - Most important ones:
    - Bottom Half -> `ctrl + opt + down arrow`
    - Left Half -> `ctrl + opt + left arrow`
    - Right Half -> `ctrl + opt + right arrow`
    - Top Half -> `ctrl + opt + up arrow`
    - Maximize -> `ctrl + opt + enter`
    - Next Desktop -> `ctrl + cmd + right arrow`
    - Next Display -> `ctrl + opt + cmd + right arrow`
    - Previous Desktop -> `ctrl + cmd + left arrow`
    - Previous Display -> `ctrl + opt + cmd + left arrow`
    - Toggle Fullscreen -> `ctrl + opt + \`
   
      
  - Less important ones:
    - Bottom Left Quarter -> `ctrl + opt + H`
    - Bottom Right Quarter -> `ctrl + opt + T`
    - First Third -> `ctrl + opt + D`
    - First Two Thirds -> `ctrl + opt + F`
    - Last Third -> `ctrl + opt + R`
    - Last Two Thirds -> `ctrl + opt + N`
    - Top Left Quarter -> `ctrl + opt + G`
    - Top Right Quarter -> `ctrl + opt + C`
