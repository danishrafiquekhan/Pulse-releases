**Pulse Downloads**

Installers for **Pulse**, a desktop IPTV player for macOS and Windows.
This repo hosts builds only. There is no source code here.

**Which file to download**

Go to [**Releases**](../../releases/latest) and grab the file for your machine:

| Platform | File |
|---|---|
| Apple Silicon (M1/M2/M3/M4) | `Pulse-x.y.z-arm64.dmg` |
| Intel Mac | `Pulse-x.y.z.dmg` |
| Windows | `Pulse Setup x.y.z.exe` |

**Installing on macOS**

1. Open the `.dmg` and drag **Pulse** into **Applications**.
2. Launch it from Applications (not from the mounted disk image).

**"Apple could not verify this app is free of malware"**

This build is not signed with a paid Apple Developer ID, so Gatekeeper shows
a warning the first time you open it. This is expected. Here is how to get
past it:

1. Click **Done** on the warning dialog.
2. Open **System Settings → Privacy & Security**, scroll to the bottom, and
   click **Open Anyway** next to the mention of Pulse.
3. Launch the app again and click **Open Anyway** on the second prompt.
   macOS remembers this choice permanently after that.

If the app is blocked outright or quits immediately on launch, clear the
quarantine flag and re-sign it locally from Terminal:

```bash
xattr -cr "/Applications/Pulse.app"
codesign --force --deep --sign - "/Applications/Pulse.app"
```

**Installing on Windows**

1. Run `Pulse Setup x.y.z.exe`.
2. Choose an install location (or accept the default) and finish the wizard.

**"Windows protected your PC" (SmartScreen)**

This build is not signed with a paid code-signing certificate, so
Windows SmartScreen flags it as unrecognized. To proceed:

1. On the blue SmartScreen dialog, click **More info**.
2. Click **Run anyway**.

If SmartScreen or your antivirus removed/quarantined the downloaded file
instead of just warning, restore it from quarantine in Windows Security
(**Windows Security → Virus & threat protection → Protection history**)
before trying the steps above.

**Updating from Kinescope, Relay IPTV, or Signal IPTV**

Pulse is the same app, renamed and re-themed. Your saved settings,
favorites, history, and cached channel lists carry over automatically on
first launch. One exception: if you had a saved login protected by your
device's Keychain, macOS ties that encryption to the app's identity, so
you will need to re-enter that login once after updating. Everything else
survives the update.

**Updates**

New versions are published here as new Releases. This app does not
auto-update from this repo. Check back here (or watch this repo's
Releases) for new versions.
