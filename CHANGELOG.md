# Changelog

## 0.3.2 — 2026-11-12
- Patch list per add-on (▸): see every patch, remove them one by one, or reset all.
- Applying a patch that is already applied is now refused instead of being applied twice.
- Patches must match indentation (tabs vs 4 spaces still tolerated).
- Deleting a patched copy retries when Windows briefly locks a file, and reports it if it still can't.

## 0.3.0
- **Fix on a copy:** apply diffs, whole AI answers, `.py` files or `.zip` to a copy of a failing add-on and
  retest it in the sandbox.
- "Apply the AI's patches and retest" in one click.
- New logo and app icon.

## 0.2.0
- Direct AI assistant: Gemini (free key with Google sign-in) or Claude; keys encrypted with Windows DPAPI.
- Automatic retry and fallback to another Gemini model when one is busy; **Retry** button.
- Newer compatible versions are downloaded from extensions.blender.org.
- **Undo** for real installs.
- Drag across cells to tick several add-ons.
- Romanian UI; blue title bar and scrollbars.
- Single-file `AddonVisor.exe` — no Python needed.

## 0.1.0
- First version: scan all Blender versions, add-on matrix, sandbox test, install with backup,
  error log and AI-ready report, 8 UI languages.
