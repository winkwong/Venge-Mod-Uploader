<div align="center">
  <img src="icons/icon128.png" alt="Logo" width="128" height="128" />

  # Venge Mod Uploader
  
  **Upload, manage, and apply browser-safe Venge.io mod files at runtime.**

  [![Manifest V3](https://img.shields.io/badge/Manifest-V3-brightgreen.svg)](https://developer.chrome.com/docs/extensions/mv3/)
  [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

</div>

---

A browser extension that allows you to easily load [Venge.io](https://venge.io/) mod files directly in your browser without external clients.

## ✨ Features

- **📂 Easy Uploads**: Upload mod files or folders directly from the extension popup.
- **🔘 Easy Mod Toggling**: Enable or disable loaded mods instantly with a single click from the extension popup.
- **💾 Local Storage**: Stores uploaded mods securely in extension storage.
- **⚡ Page-World Runtime**: Injects a custom runtime on `venge.io` to handle modding logic seamlessly.
- **🔄 Asset Remapping**: Automatically remaps matching Venge asset URLs to your uploaded mod assets.
- **🛠️ Userscript Patch Behavior**: Natively applies known userscripts such as:
  - `charfix`
  - `hide_hands`
  - `weapon_vol`

## 🚀 Installation

This extension supports all **Chromium-based browsers** (Google Chrome, Microsoft Edge, Brave, Opera, Vivaldi). 

Currently, it can be installed manually via Developer Mode:

1. Download the latest `venge-mod-uploader.zip` file from the **[Releases](../../releases/latest)** page and extract it.
2. Open your browser and navigate to its extensions page:
   - Chrome/Vivaldi/Opera: `chrome://extensions/`
   - Edge: `edge://extensions/`
   - Brave: `brave://extensions/`
3. Enable **Developer mode** (usually a toggle in the top right corner).
4. Click **Load unpacked** in the top left.
5. Select the extracted extension folder.

## 🕹️ Usage

1. Open [Venge.io](https://venge.io/) in your browser.
2. Click on the **Venge Mod Uploader** extension icon to open the popup.
3. Upload a mod file set or a full mod folder.
4. Ensure the mod is toggled to **enabled** in the popup.
5. Play! *(Note: Reload the Venge tab if needed after making major mod changes.)*

## 🐛 Debugging

The runtime exposes simple indicators so you can confirm that it is active and functioning correctly.

Check the console for:
- `document.documentElement.dataset.vengeModUploader`
- `window.__vengeModUploaderStatus`

If the mod is successfully active, your browser console will display:
```text
[Venge Mod Runtime] Active
```

### Advanced Logging
To enable extra runtime logging for troubleshooting, run the following in your console:
```javascript
localStorage.__vengeModDebug = "1"
```
Then, reload the page.

## 📝 Notes

- **File Paths**: Asset overrides work best when uploaded files preserve their original `assets/<id>/<version>/<name>` paths.
- **Performance**: Audio overrides are loaded in a deferred phase to reduce startup cost and prevent lag.
- **Stability**: If Venge.io changes its internal hooks, the runtime is designed to fail gracefully and log warnings without breaking the game.

## 🤝 Credits

- Created by **yolk!, ain**
