# Fixing add-ons that fail

When an add-on fails in the sandbox test, press **Fix** next to it. AddonVisor never edits the original:
it makes a **patched copy** in `%LOCALAPPDATA%\AddonVisor\patched\` and applies your patches there.

## What you can give it

| Input | How it is applied |
|---|---|
| A unified diff (`.diff`, `.patch`) | Matched by the surrounding code; line numbers are ignored, so AI-written diffs work |
| A whole AI chat answer (`.md`, or pasted text) | Every ```` ```diff ```` block in it is extracted and applied |
| A whole `.py` file | Replaces the file with the same name inside the add-on |
| A `.zip` of the fixed add-on | Replaces the whole copy |

Drop the file on the box, click it to choose a file, or paste text into the field and press
**Apply pasted text**. Patches from **any AI** work: Claude, ChatGPT, Gemini, Copilot…

Then press **↻ Retest in sandbox**. If it now works, install it as usual — the patched copy is used.

### One click with the built-in AI

If the [AI assistant](ai-assistant.md) answered with a diff, press
**Apply the AI's patches and retest**.

## Safety rules

- **All or nothing.** If one part of a patch doesn't match the file, nothing is written and you are told
  exactly which file and which line.
- **No double patches.** Applying a patch that is already in the copy is refused
  (*"this patch is already applied — nothing changed"*).
- **Indentation matters.** In Python indentation changes the meaning, so a patch must match it
  (tabs vs 4 spaces is tolerated).

## The patch list

Rows with patches show **▸**. Click it to see every patch: number, file name, which files it changed and when.

- **✕ Remove** undoes one patch: the copy is rebuilt from the original add-on and the other patches are
  applied again, in order. If a later patch depends on the one you remove, nothing changes and you are
  told which one to remove first.
- **↺ Reset all patches** (or the small ↺ next to the row's note) deletes the patched copy;
  the original add-on is used again.

## Commercial add-ons

A patch stays on your computer. For paid add-ons, an update from the author is usually the safer route —
send them the AI report from `%LOCALAPPDATA%\AddonVisor\logs\`.

## Example

`patches/BlenderGIS_2.2.10_python313_imghdr.diff` in this repository fixes BlenderGIS 2.2.10 on
Blender 5.3 (Python 3.13 removed the `imghdr` module).
