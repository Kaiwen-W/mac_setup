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
