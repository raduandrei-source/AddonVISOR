# Changelog

## 1.0.0 — Blender extension edition
- The same AddonVisor as a Blender extension (Blender 4.2+, Windows / Linux / macOS): **Open AddonVisor** in the
  N panel opens the page in your web browser (local only, 127.0.0.1, private link).
- Install straight into the Blender you are in: tested in a separate Blender first; only what passes is turned on
  in your session, and Blender saves its own preferences. Undo works the same way.
- Warns when the target Blender is open (it would overwrite the preferences when it quits). Desktop app too.
- AI providers are called over plain HTTPS (no extra packages).

## 1.0.0 — first release
- Scans every Blender on your PC and shows all your add-ons in one matrix (A → Z).
- Always the newest copy of each add-on; newer compatible versions are downloaded from extensions.blender.org.
- Sandbox test before anything changes; install only what works, with a backup and Undo.
- Fix on a copy with patches from any AI; patch list with removal one by one.
- Optional AI assistant (Gemini or Claude) with encrypted keys.
- Generate AI prompt: a detailed English request for any AI chat (versions, system, error, failing code, patch format), with five ways of asking.
- 9 languages, installer and portable version, online help.
- Linux version: an AppImage for Ubuntu 22.04+, Debian 12+, Fedora 36+ and Linux Mint 21+.
