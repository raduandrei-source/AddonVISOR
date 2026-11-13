# Fixing add-ons that fail

When an add-on fails in the sandbox test, press **Fix** next to it. AddonVisor never edits the original:
it makes a **patched copy** in `%LOCALAPPDATA%\AddonVisor\patched\` (Linux: `~/.local/share/AddonVisor/patched/`) and applies your patches there.

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

### Any AI chat: Generate AI prompt

You do not need the built-in assistant, and you do not have to write the request yourself. Press
**Generate AI prompt** (in the results window or the AI panel). AddonVisor writes a detailed request in
English with everything an AI needs:

- the Blender **and** Python versions on both sides (where the add-on worked, and the target), your system;
- the add-on type (legacy add-on or extension) and its file list;
- the full error, and the failing file (whole, or the part around the failing line);
- exact rules for the patch format, so the answer can be applied automatically.

Choose how to ask:

| Ask for | What you get |
|---|---|
| **Minimal fix** | the cause, the smallest patch, what to check afterwards |
| **Works in old + new** | one patch that keeps working in the older Blender too |
| **Explain only** | no code: what broke, how big the fix is, your options |
| **Full port review** | everything in the shown code that breaks in the target, not only the first error |
| **Diff only (small / local AI)** | only diff blocks in a strict format — best for small local models |

Edit the text if you like, press **Copy prompt**, paste it into ChatGPT, Claude, Gemini, Copilot or any other
AI, copy its whole answer and paste it into **Fix → Apply pasted text → Retest in sandbox**.

If the AI's patch does not apply (*"hunk N does not match"*), send that message back to the same chat and ask
it to copy the context lines exactly from the code it was given. If the next error appears after the first fix,
choose **Full port review**.

**Copy report for AI chat** copies only the short error report, if you prefer to write your own question.

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
send them the AI report from `%LOCALAPPDATA%\AddonVisor\logs\` (Linux: `~/.local/share/AddonVisor/logs/`).

## Example

`patches/BlenderGIS_2.2.10_python313_imghdr.diff` in this repository fixes BlenderGIS 2.2.10 on
Blender 5.3 (Python 3.13 removed the `imghdr` module).
