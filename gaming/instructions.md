# Lunar Client

## Profile

```
cd ~/.lunarclient/settings/game
```

```
mkdir PVP
cd PVP
mkdir killsounds
```

```
curl -L https://api.github.com/repos/Kaiwen-W/mac_setup/contents/gaming/PVP?ref=main \
  | grep "download_url" \
  | cut -d '"' -f 4 \
  | xargs -n 1 curl -O
```

```
cd ../
code profile_manager.json
```

Append the following to the end of the profile_manager.json (within the square [] brackets)

```
{"name":"PVP","displayName":"PVP","default":false,"active":false,"iconName":"","server":""}
```

# Settings -> Options...

- FOV -> 100
- Music & Sounds...
  - Music -> Off
  - Weather -> 50%
  - Hostile Creatures -> 50%
  - Rest -> Default (100%)
- Video Settings

  - GUI Scale -> Large
  - Render Distance -> 16 Far
  - Max Framerate -> 120 fps
  - Dynamic FOV -> Off

- Controls

  - Pick Block -> LCONTROL
  - Hotbar
    - 6 -> X
    - 7 -> C
    - 8 -> Button 3 (front side mouse button)
    - 9 -> F
  - Toggle Perspective -> LMENU (caps lock remap)
  - Sprint -> R

- Chat Settings
  - Width -> 211px
  - Scale -> 75%

## Shaders to Download

Sildurs

- https://sildurs-shaders.github.io/downloads/
