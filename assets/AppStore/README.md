# Duck OS App Store — App folder format

Each app lives in its own folder inside `assets/AppStore/`.

```text
assets/
└── AppStore/
    └── YourAppName/
        ├── Icon.png
        ├── index.html
        └── Appstore info.json
```

## 1. Icon.png

The app's icon image. PNG is recommended.

## 2. index.html

The app's HTML entry point. Put the app's CSS, JavaScript, and any additional assets in this app folder.

## 3. Appstore info.json

This file contains the details Duck OS displays in the App Store. Use this JSON format:

```json
{
  "name": "Your App Name",
  "description": "A short description of your app.",
  "category": "Utilities",
  "version": "1.0.0"
}
```

The app folder name is used as its unique ID. Keep the folder name unique.

## Important

GitHub Pages is a static host and does not provide a built-in way for a webpage to list every folder. The App Store must discover app folders through the GitHub Contents API or a generated catalogue. The current Duck OS App Store still reads the legacy `assets/appstore/apps.json` catalogue, so this folder format is documented here but is not automatically detected by the current store code yet.
