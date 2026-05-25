# Settings changed with TinkerTool

Finder

- Finder options
  - Show hidden and system files -> On
  - Disable sound effects -> On
  - Automatically adapt to file name widths in column mode -> On
- Animation effects
  - Animate opening info panels and Desktop icons -> Off
  - Animate selecting info panel categories -> Off
- Restricted Finder
  - Burn disc -> On

Dock

- Dock Options
  - Disable animation when hiding or showing Dock -> On

Desktop

- When applications crash
  - Don't display anything -> On

#### Remember to press reload finder and reload dock after setting these settings.

# Settings changed within MacOS

## Finder

Finder Settings (`cmd + ,`)

- General
  - Show these items on the desktop -> All Off
  - New Finder windows show -> downloads
- Tags -> select all tags and delete them
- Sidebar
  - Show these items in the sidebar
    - Recents -> Off
    - Shared -> Off
  - Favourites
    - AirDrop -> Off
    - Home directory -> On
  - iCloud
    - iCloud Drive -> Off
    - Shared -> Off
  - Locations
    - K's MacBook Pro -> On
  - Tags
    - Recent Tags -> Off
- Advanced
  - Show all filename extensions -> On
  - Show warning before changing an extension -> Off
  - Remove items from the Bin after 30 days -> On
  - When performing a search -> Search the Current Folder

View

- as List -> On
- Sort By
  - Snap to Grid -> On
- Show Path Bar -> On
- Show Status Bar -> On
- Customise Toolbar... -> Turn off "Edit Tags"

Go to home directory -> Add a new folder called "Developer" -> Add to Favourites by dragging it over and add it between Applications and Desktop

## System Settings

Menu Bar
- Automatically hide and show the menu bar -> Never

- Menu Bar Controls
  - Spotlight
    - Don't Show in Menu Bar -> On
  - Battery
    - Show in Menu Bar -> Off

- Control Centre Modules
  - Focus -> Show When Active
  - Display -> Don't Show in Menu Bar
  - Sound -> Always Show in Menu Bar
  - Now Playing -> Don't Show in Menu Bar


Desktop & Dock

- Dock

  - Position on screen -> Left
  - Minimise windows using -> Scale Effect
  - Double-click a window's title bar to -> Minimise
  - Minimise windows into application icon -> On
  - Automatically hide and show the Dock -> On
  - Animate opening applications -> Off

- Widgets

  - Default web browser -> Arc

- Windows

  - Hold `opt` key while dragging windows to tile -> On
  - Tiled windows have margins -> Off

- Mission Control

  - Group windows by application -> On

- Hot Corners...
  - Bottom right -> - (i.e. nothing)

Spotlight -> Search Privacy...

- Add following folders:
  - Developer
  - Music

Sound

- Play sound on startup -> Off
- Play user interface sound effects -> Off

Keyboard

- Keyboard Shortcuts

  - Mission Control
    - Show Desktop -> F4 (remember to change setting in Function Keys parct of Karabiner-Elements)
  - Spotlight
    - Show Spotlight search -> Off
  - Services
    - Convert text to simplified Chinese -> Off

- Text Input -> Input Sources -> Edit...
  - Correct spelling automatically -> Off
  - Capitalise words automatically -> Off
  - Show inline predictive text -> Off
  - Add full stop with double-space -> Off

Mouse

- Natural Scrolling -> Off

Trackpad

- Point & Click
  - Tap to click -> On
- Scroll & Zoom
  - Natural scrolling -> Off

# Settings changed in the Terminal

To change the size of the dock:

```
defaults write com.apple.dock "tilesize" -int "54" && killall Dock
```

To disable windows management animation:

```
defaults write -g NSWindowResizeTime -float 0.003
killall Finder
```
