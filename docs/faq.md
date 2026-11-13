# FAQ

**Is this a Blender add-on?**
No. AddonVisor is a separate app for Windows and Linux. It runs outside Blender, so it can see and compare
*all* your Blender versions at once — including ones you have never opened.

**Can it break my Blender setup?**
Everything is tested first in a sandbox copy. A real install happens only after you confirm,
with a backup first, and **Undo** puts everything back. Your older Blender versions are only read from.

**Does it fix add-ons automatically?**
It finds what breaks and why. It then uses a newer compatible version from extensions.blender.org when
there is one; otherwise you can apply a patch (from the built-in AI or any other AI) to a copy and retest.
Some add-ons need their author to update them — AddonVisor tells you which and gives you a report to send.

**Does it work with add-ons bought on Superhive / Gumroad?**
Yes — it copies whatever is installed on your computer. It never shares your add-ons with anyone.

**Do I need the AI?**
No. It is optional; without it nothing leaves your computer.

**Mac / Linux?**
Linux: yes — an AppImage for 64-bit PCs (Ubuntu 22.04 or newer and similar distributions).
Mac: not for now.

**Which Blender versions?**
Tested with 4.1 – 5.3. Older 2.8x–4.0 should work but are untested.

**Is the source code included?**
Yes. AddonVisor is licensed under the GNU GPL v3; the source is in the download.
