# Duck OS App Store

Put each app in its own folder under `assets/appstore/`, then register it in `apps.json`.

## Folder layout

```text
assets/
└── appstore/
    ├── apps.json
    └── weather/
        ├── app.json
        └── index.html
```

## Register an app

Add an entry to `apps.json`:

```json
{
  "apps": [
    {
      "id": "weather",
      "name": "Weather",
      "description": "A simple weather app.",
      "icon": "🌦️",
      "category": "Utilities",
      "entry": "assets/appstore/weather/index.html"
    }
  ]
}
```

The `name` is the name shown on the App Store card and in the app window. The `entry` is the app's HTML file path from the repository root. Each app can keep its own CSS, JavaScript, and images in its folder.

The App Store reads `apps.json`, displays registered apps, and opens an app in a window when selected. Use GitHub Pages or another web server to run Duck OS; browser security usually blocks loading the catalogue from a page opened directly as a `file://` URL.

Apps run inside a sandboxed iframe. They should not expect access to Duck OS's private browser storage.
