# Privacy

- **No accounts, no telemetry, no analytics.** AddonVisor does not report anything about you or your
  computer to anyone.
- **Network use, only when needed:**
  - `extensions.blender.org` — to see which extensions have compatible versions and, when you install one,
    to download it (through Blender itself).
  - The AI provider you connected (Anthropic or Google) — only if you turned the assistant on, and only the
    error report described in [AI assistant](ai-assistant.md#what-is-sent).
  - Your browser opens the AI key pages when you press those buttons.
- **API keys** are encrypted with Windows DPAPI for your Windows user and never leave your computer except
  to the provider they belong to.
- **Everything else stays local** in `%LOCALAPPDATA%\AddonVisor\`. Uninstalling the app leaves that folder
  so your backups survive; delete it by hand to remove everything.
