**Kinescope — Downloads**

Installers for **Kinescope**, a desktop IPTV player for macOS and Windows.
This repo hosts builds only — there is no source code here.

**Which file to download**

Go to [**Releases**](../../releases/latest) and grab the file for your machine:

| Platform | File |
|---|---|
| Apple Silicon (M1/M2/M3/M4) | `Kinescope-x.y.z-arm64.dmg` |
| Intel Mac | `Kinescope-x.y.z.dmg` |
| Windows | `Kinescope Setup x.y.z.exe` |

**Installing on macOS**

1. Open the `.dmg` and drag **Kinescope** into **Applications**.
2. Launch it from Applications (not from the mounted disk image).

**"Apple could not verify this app is free of malware"**

This build is not signed with a paid Apple Developer ID, so Gatekeeper shows
a warning the first time you open it. This is expected — here's how to get
past it:

1. Click **Done** on the warning dialog.
2. Open **System Settings → Privacy & Security**, scroll to the bottom, and
   click **Open Anyway** next to the mention of Kinescope.
3. Launch the app again and click **Open Anyway** on the second prompt.
   macOS remembers this choice permanently after that.

If the app is blocked outright or quits immediately on launch, clear the
quarantine flag and re-sign it locally from Terminal:

```bash
xattr -cr "/Applications/Kinescope.app"
codesign --force --deep --sign - "/Applications/Kinescope.app"
```

**Installing on Windows**

1. Run `Kinescope Setup x.y.z.exe`.
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

**Updating from Relay IPTV / Signal IPTV**

Kinescope is the same app, renamed and re-themed. Your saved settings,
favorites, history, and cached channel lists carry over automatically on
first launch. One exception: if you had a saved login protected by your
device's Keychain, macOS ties that encryption to the app's identity, so
you'll need to re-enter that login once after updating — everything else
survives the update.

**Updates**

New versions are published here as new Releases. This app does not
auto-update from this repo — check back here (or watch this repo's
Releases) for new versions.
