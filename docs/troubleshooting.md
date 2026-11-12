# Troubleshooting

### A Blender version is missing from the matrix
AddonVisor looks in `Program Files\Blender Foundation`, Steam (`steamapps\common\Blender`), the Windows
registry, and portable installs. For a Blender elsewhere (e.g. `D:\Apps\blender-5.3`), add its folder to
`%LOCALAPPDATA%\AddonVisor\settings.json`:

```json
{ "extra_dirs": ["D:\\Apps\\blender-5.3"] }
```
then press **Rescan**. Microsoft Store installs are not supported (Windows locks that folder).

### A Blender window flashes during the test
That is the retest for GPU add-ons (they can't load without a window). It closes by itself.

### "Could not reach the AI: … high demand"
The provider is overloaded. AddonVisor already tried other models; press **↻ Retry** a bit later.

### "hunk N does not match the file"
The patch was written for different code than the add-on you have (another version, or the copy is already
patched). Open the patch list (**▸**), remove or reset patches, and try again — or ask the AI for a new
patch using the latest report.

### "this patch is already applied"
Nothing to do: that change is already in the patched copy.

### "could not delete … a file is in use"
Close Explorer windows or editors that show files inside `%LOCALAPPDATA%\AddonVisor\patched\`, then retry.

### The window is blank
Install or repair the **Microsoft Edge WebView2 Runtime**.

### SmartScreen / antivirus warning
The app is new and not code-signed yet. Choose **More info → Run anyway**. If your antivirus quarantines it,
restore it and add an exception — and please tell us, so we can report the false positive.

## Reporting a problem

Attach the newest `run_*.log` from `%LOCALAPPDATA%\AddonVisor\logs\` and say which Blender versions you
have. Open an issue on [GitHub](https://github.com/raduandrei-source/AddonVISOR/issues) or write to
**gmcis.cutvisor@gmail.com**.
