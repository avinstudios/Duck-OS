# Duck OS 🦆

Duck OS is a browser-based desktop environment with a Windows 10-inspired interface, a Start menu, taskbar, startup screen, File Explorer, and an App Store for add-on apps.

## Features

- Windows-inspired desktop, wallpaper, Start menu, taskbar, clock, and startup animation
- App windows with minimize, maximize, close, and drag controls
- File Explorer with browser-local folders and editable text files
- App Store that loads apps from `assets/appstore/apps.json`
- Notepad, Calculator, web browser launcher, and personalization settings
- Preferences, installed-app list, notes, and workspace saved in browser local storage
- Custom icon and favicon at `assets/icon/iconandfavicon.png`

## Run Duck OS

Open `index.html` through a local web server or GitHub Pages. The App Store loads its catalogue with `fetch()`, so it needs an HTTP(S) origin; opening the HTML directly as a `file://` URL may prevent the catalogue from loading.

## Add apps to the App Store

Create a folder for each app inside `assets/appstore/`. Each app folder should contain its HTML entry point and an `app.json` metadata file. Then register the app in `assets/appstore/apps.json` (the catalogue file).

Example layout:

```text
assets/
├── icon/
│   └── iconandfavicon.png
└── appstore/
    ├── apps.json
    └── weather/
        ├── app.json
        └── index.html
```

Example `assets/appstore/apps.json`:

```json
{
  "apps": [
    {
      "id": "weather",
      "name": "Duck Weather",
      "icon": "🌦️",
      "description": "A simple weather app for Duck OS.",
      "category": "Utilities",
      "entry": "assets/appstore/weather/index.html"
    }
  ]
}
```

The App Store reads each catalogue entry's `id`, `name`, `icon`, `description`, `category`, and `entry`. The `entry` must be a path inside `assets/appstore/`. The optional per-app `app.json` can hold the same metadata for your own organization; the current catalogue uses `apps.json` as its index because static GitHub Pages sites cannot automatically list directory contents.

Apps launch in a sandboxed iframe inside a Duck OS window. Apps are static web files; the Store's installed state is saved in the current browser.

## Custom files

Files and folders created in File Explorer are stored in the browser's local storage. They are not the actual files on your device and are not committed to GitHub.

## Icon credit

The Duck OS icon and favicon at `assets/icon/iconandfavicon.png` were provided by **DuckDNS**. Credit and thanks to DuckDNS for the artwork.

## Inspiration

Duck OS is inspired by web-based desktop interfaces, including [VUS by Cra-Z-Gaming](https://github.com/Cra-Z-Gaming/VUS).
