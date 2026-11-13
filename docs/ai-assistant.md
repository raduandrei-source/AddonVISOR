# AI assistant (optional)

The assistant reads the error report of a failed test and explains what broke and how to fix it,
usually with a ready-to-apply diff. It is **off unless you connect a provider**; AddonVisor works fully
without it.

## Connect

Choose a provider in the *AI assistant* card:

**Gemini — free key with your Google account**
1. Press **Continue with Google**. Google AI Studio opens in your browser.
2. Sign in, press **Create API key**, copy it.
3. Paste it into AddonVisor and press **Connect**.
The free tier has request limits per minute and per day — plenty for occasional analyses.

**Claude — paid API key**
1. Press **Get a Claude API key**. The Claude Console opens.
2. Add credit under *Billing*, then create a key under *API keys* (it is shown only once).
3. Paste it into AddonVisor and press **Connect**.
A Claude Pro/Max subscription does **not** include API usage; the API is billed per use
(a typical analysis costs a few cents).

Keys are stored **encrypted for your Windows user** (Windows DPAPI) in `%LOCALAPPDATA%\AddonVisor\keys.json`.
On Linux they go into the system keyring (GNOME Keyring / KWallet), or — if there is none — into a file
only your user can read.
**Disconnect** deletes the key.

## Use

- **Read the log automatically after each test** (on by default): when a test fails, the report is sent
  right away and the answer appears in the results window.
- Or press **Ask AI about these errors**.
- If the provider is busy, AddonVisor waits and tries another model by itself; if it still fails,
  press **↻ Retry**.

## What is sent

Only the report of the failed add-ons: the Python error and about 17 lines of code around the failing line.
Paths containing your Windows user name are replaced with `%USERPROFILE%` (Linux: `~`).
Nothing else from your computer is sent. With the assistant off, nothing is sent at all;
you can still press **Copy report for AI chat** and paste it anywhere yourself.

Models: Claude uses `claude-opus-5-5`; Gemini uses the newest Flash model your key can access.
