# Getting started

## Requirements

- Windows 10 or 11, 64-bit
- Microsoft Edge WebView2 Runtime (built into Windows 11; on Windows 10 it is usually already installed —
  if the window stays blank, install it from Microsoft's WebView2 page)
- One or more Blender versions installed. AddonVisor has been tested with Blender **4.1 – 5.3**;
  older 2.8x–4.0 releases should work but are not tested.
- Internet only for the optional parts: extensions.blender.org downloads and the AI assistant.

## Install

**Installer:** run `AddonVisor-Setup-<version>.exe`. It adds AddonVisor to the Start menu and to
*Settings → Apps*, from where you can uninstall it.

**Portable:** unzip `AddonVisor-<version>-portable.zip` anywhere and run `AddonVisor.exe`.

> **Windows SmartScreen** may say *"Windows protected your PC"* the first time, because the app is new and
> not yet code-signed. Click **More info → Run anyway**. You only need to do this once.

## First start

1. AddonVisor scans your computer by itself: Program Files, Steam, the Windows registry and portable
   Blender folders. This takes a few seconds — every Blender version is started invisibly in the background
   to read its add-ons.
2. You see the **matrix**: one row per add-on (A → Z), one column per Blender version.
3. The newest Blender is selected as the **target** column.

| Symbol | Meaning |
|---|---|
| ✓ | enabled and working in that version |
| ○ | installed, but switched off |
| ✕ | enabled, but fails to load (hover to see the error) |
| ! | GPU add-on: can't be tested in the background, retested with a small window |
| + | queued: will be installed in the target version |

## Language

Use the language button in the top-right corner. Available: English (default), Français, Español,
Deutsch, Русский, 简体中文, 日本語, Português (Brasil), Română. Your choice is remembered.

## Where AddonVisor keeps its files

Everything lives in `%LOCALAPPDATA%\AddonVisor\`:

| Folder | What's inside |
|---|---|
| `backups\` | a backup taken before every real install (used by **Undo**) |
| `logs\` | `run_*.log` and `ai_report_*.md` for every test |
| `patched\` | your fixed copies of add-ons (see [Fixing add-ons](fixing-addons.md)) |
| `settings.json`, `keys.json` | preferences; AI keys encrypted for your Windows user |

Next: [Migrating add-ons](migrating.md)
