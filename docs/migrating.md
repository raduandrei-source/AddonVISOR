# Migrating add-ons to a new Blender

## 1. Choose the target version

Click a column header to make that Blender version the target. By default it is the newest one
you have installed — even if you have never opened it yet.

## 2. Tick what should go there

- **Click** an empty cell in the target column to queue that add-on (`+`). Click again to remove it.
- **Press and drag** down the column to tick several add-ons at once.
- Or use a **shortcut**:
  - **My X + Y setup → target** — everything enabled in your two most recent Blender versions.
  - **Everything that works → target** — every add-on you have used anywhere, except the ones known to fail.
  - **Clear** — empties the queue.
- Add-ons you installed but never enabled are hidden under *"Show N add-ons that were never enabled"*.

## 3. Which copy is used?

You don't pick a source version. For each add-on AddonVisor looks at **every copy on your computer**
and takes the newest one that declares support for the target Blender version
(`blender_version_min/max` in `blender_manifest.toml`, or `bl_info["blender"]`).

If **extensions.blender.org** has a newer version that supports the target — or your local copy is known
to fail — the row says *"↑ 1.2.3 on extensions.blender.org · will be used"* and that version is downloaded
instead (through Blender's own `blender -c extension install`).

If you fixed an add-on yourself, your **patched copy** is used (see [Fixing add-ons](fixing-addons.md)).

## 4. Install & test

Press **Install & test (N)**. Two things happen, in this order:

1. **Sandbox test.** The target's user folder is copied to a temporary folder, Blender is started pointing
   at that copy (`BLENDER_USER_RESOURCES`), the add-ons are copied in and enabled one by one.
   **Nothing in your real Blender folders changes.** GPU add-ons that refuse to load in the background are
   tested again with a small Blender window — you may see it flash for a few seconds.
2. **Results.** You see what works and what fails, with the exact error. Then:
   - **Install the N that work** — installs only those, for real.
   - **Fix** next to a failing add-on — see [Fixing add-ons](fixing-addons.md).
   - **Cancel** — nothing is installed.

## 5. Undo

Before a real install AddonVisor saves a backup of your preferences and of every file it replaces.

- In the results window: **↶ Undo**.
- Later: **↶ Undo last install** in the *Target version* card.

Undo removes what was added, puts back what was replaced and restores your preferences
(or removes them, if the version had no saved preferences before).

## Your other Blender versions

AddonVisor only ever **reads** from them. Copies are made from them, never moved.
