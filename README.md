# WebView Launcher v1.4 New Update

An Android app for storing and running HTML projects (web games/apps) directly on your device. Simply add a `.zip` file (containing html/css/js) or a single `.html` file, then launch it from the list in a full-screen WebView.

| | |
|---|---|
| **Latest version** | 1.4 (versionCode 14) |
| **Package** | `com.webviewlauncher.app` |
| **Minimum Android** | 5.0 Lollipop (API 21) |
| **Target SDK** | 34 |
| **APK size** | ~7.5 MB |

---

## What's New in v1.4

The changes below are compared to **v1.0**.

### New features

- **Splash screen**: an opening screen with a logo when the app starts (`SplashActivity`), replacing the direct launch into the main screen.
- **New app icon**: the launcher icon is now an *adaptive icon* (supports round/square shapes depending on the device launcher, Android 8.0+).
- **Optional name**: the name field can be left empty. The app generates an **automatic name** from the selected file and shows a hint (`Auto name: ...`). In v1.0 the name was required.
- **Automatic icon from inside the ZIP**: if a `.zip` project contains `icon.png` or `icon.jpg`, that image is used as the item's icon. If none is found, the app generates an automatic icon. A manual icon (optional) can still be chosen.
- **"Choose action" dialog**: a per-item action menu with clearer **Info** and **Delete** buttons.
- **"File Information" dialog**: shows item details:
  - Display Name
  - Original File Name
  - File Type
  - File Size
  - Original File Location
  - Date Added
- **Updated project importer**: a new `ProjectImporter` component and supporting utilities (`IconUtils`, `NameFormatter`) to process files, determine names, and prepare icons.

### UI changes

- The main screen now shows **a single list of HTML projects** (no tabs), making it simpler.
- Themes, buttons, and dialogs were refreshed (new dialog background, flat button style, dedicated delete and info button styles, new info and trash icons).
- The game screen (`WebGameActivity`) uses an adjusted theme and still supports automatic screen rotation.

### Removed

- **The PDF / Document feature was removed.** The *Documents* tab, the *Add PDF* page, and the PDF viewer (page navigation, image zoom) are no longer in v1.4. The app now focuses on HTML projects.
- The tab/pager components (`TabLayout`, `ViewPager`) were replaced with a single fragment container.

---

## Comparison: v1.0 vs v1.4

| Aspect | v1.0 | v1.4 |
|---|---|---|
| Version / versionCode | 1.0 / 1 | 1.4 / 14 |
| First screen | Main screen directly | Splash screen, then main screen |
| Main screen structure | Tabs: HTML and PDF | Single HTML list |
| PDF support | Yes (add and view PDFs) | **Removed** |
| Add HTML project (`.zip` / `.html`) | Yes | Yes |
| Name field | Required | Optional (auto name) |
| Item icon | Manual pick or automatic | Manual pick, automatic from `icon.png`/`icon.jpg` in the ZIP, or auto-generated icon |
| Item actions | Delete confirmation | "Choose action" dialog: Info and Delete |
| File details | None | File Information dialog |
| App icon | Standard icon | New adaptive icon |
| Min SDK / Target SDK | 21 / 34 | 21 / 34 |
| APK size | ~7.4 MB | ~7.5 MB |

---

## Key Features

- Run web projects (HTML/CSS/JS) offline through WebView.
- Supports full-project `.zip` files as well as single `.html` files.
- Custom or automatic icon and name.
- Screen rotation support while running a project.
- Detailed information for every added file.

---

## How to Use

1. Open the app and wait for the splash screen to finish.
2. Tap the **add** button on the main screen.
3. Choose an HTML file (`.zip` or `.html`).
4. *(Optional)* Enter a name. If left empty, a name is generated automatically.
5. *(Optional)* Choose an icon image. If skipped, the app uses `icon.png` / `icon.jpg` from inside the ZIP if present, or an auto-generated icon.
6. Save, then tap an item in the list to run it.
7. To view details or delete an item, open the **Choose action** menu on that item.

### Tips for `.zip` projects

- Make sure the ZIP contains at least one `.html` file. Otherwise the app shows the message *"No .html file found in this project"*.
- Put `icon.png` or `icon.jpg` inside the ZIP if you want it used as the icon automatically.

---

## Installation

1. Download the APK file `Apk_v1_4_WebViewLauncher.apk`.
2. Allow installation from unknown sources on your device.
3. Open the APK file and follow the installation steps.

> **Upgrade note:** v1.4 no longer includes the PDF feature. PDF items created in v1.0 will not appear in this version.

---

## Technical Information

- **Package:** `com.webviewlauncher.app`
- **Main activities:** `SplashActivity` (launcher), `MainActivity`, `AddGameActivity`, `WebGameActivity`
- **App-specific permissions:** the manifest requests no additional storage or internet permissions
- **UI libraries:** AndroidX and Material Components

---
