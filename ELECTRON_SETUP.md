# Desktop App Setup Guide

## ✅ Installation Complete!

Electron dependencies have been installed. You can now run this as a desktop application.

---

## 🚀 Running as Desktop App

### Development Mode (with hot reload):
```bash
npm run electron-dev
```
This will:
1. Start the Next.js dev server
2. Wait for it to be ready
3. Open the Electron desktop window

### Production Build:

#### For Windows (.exe):
```bash
npm run electron-build-win
```
Output: `dist/CPU Scheduling Visualizer Setup.exe`

#### For macOS (.dmg):
```bash
npm run electron-build-mac
```
Output: `dist/CPU Scheduling Visualizer.dmg`

#### For Linux (.AppImage, .deb):
```bash
npm run electron-build-linux
```
Output: `dist/CPU Scheduling Visualizer.AppImage` and `.deb`

---

## 📦 What Gets Created

After building, you'll find in the `dist/` folder:
- **Windows**: Installer executable (NSIS setup)
- **macOS**: DMG disk image
- **Linux**: AppImage (portable) and DEB package

---

## 🎯 Quick Commands

| Command | Description |
|---------|-------------|
| `npm run dev` | Web version (browser) |
| `npm run electron-dev` | Desktop app (development) |
| `npm run electron-build-win` | Build Windows installer |
| `npm run export` | Build static Next.js files |

---

## 📋 Requirements

- **Node.js** 20.x or higher
- **Windows**: Windows 7 or later
- **macOS**: macOS 10.13 or later
- **Linux**: Most modern distributions

---

## 🛠️ Troubleshooting

### Issue: "Cannot find module 'electron'"
**Solution**: Run `npm install` again

### Issue: Build fails on Windows
**Solution**: Install Windows Build Tools:
```bash
npm install --global windows-build-tools
```

### Issue: Build fails on macOS
**Solution**: Install Xcode Command Line Tools:
```bash
xcode-select --install
```

---

## 🌟 Features in Desktop App

✅ Offline functionality
✅ Native window controls
✅ System tray integration (optional)
✅ Auto-updates (configurable)
✅ Better performance than browser
✅ No need for internet after installation

---

## 📂 Project Structure

```
CPU-Scheduling-Visualizer/
├── electron/
│   ├── main.js       # Main Electron process
│   └── preload.js    # Preload script
├── out/              # Built Next.js files (after export)
├── dist/             # Built Electron apps (after build)
└── package.json      # Updated with Electron scripts
```

---

## 🎉 Ready to Go!

Try it now:
```bash
npm run electron-dev
```

This will open your CPU Scheduling Visualizer in a native desktop window!
