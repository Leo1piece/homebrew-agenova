# Agenova Homebrew tap

Public macOS, Linux and Windows preview distribution of the [Agenova CLI](https://github.com/wunderforge/agenova).

```bash
brew install Leo1piece/agenova/agenova
agenova login --server https://app.agenova.app
agenova work list
```

Sign in using your own Google account. An administrator must approve your project
access before you can submit Work. No AWS keys, kubeconfig or cluster permissions
are needed for member commands.

```bash
agenova run -f work.yaml
agenova work show <request-ref>
agenova logout
```

[New member guide and example](https://github.com/wunderforge/agenova/blob/3921df511f3d5d0d7425eaf0163997ee4d378450/docs/cli-installation.md).

## Updates

```bash
brew update
brew upgrade Leo1piece/agenova/agenova
```

This is a preview from Agenova PR #216, not a stable release. The formula pins an
immutable source archive and SHA-256 checksum. Homebrew installs the Go build
dependency and compiles the native CLI locally with native OS credential storage.
No prebuilt bottles or Developer ID notarization are claimed. Apple Silicon is locally verified. Windows x64 and Linux x64 have native CI
credential/build checks; WSL2 requires a separate real-user acceptance run.
Intel macOS and Windows ARM64 are not yet verified.

macOS may ask for Keychain permission. Choose Always Allow only for the Agenova
executable you installed. Upgrades or a locked keychain may require consent again.
This repository contains no tokens, passwords or cloud credentials.

## Linux / WSL2

The same brew command works with Linux Homebrew. You need a D-Bus session and an
unlocked GNOME login keyring (Secret Service); tokens never fall back to plaintext.
On WSL2, `wslview` from wslu opens the Windows browser, otherwise xdg-open is used.
The browser must reach the CLI callback at 127.0.0.1:38123.
Alternatively run the Windows agenova.exe from WSL interoperability, using Windows
Credential Manager and Windows file paths. Linux and Windows keep separate logins.

## Windows

Download the x64 ZIP and matching SHA256 from [Releases](https://github.com/Leo1piece/homebrew-agenova/releases).
Verify the hash with Get-FileHash, extract agenova.exe and put its directory on your
user PATH. Or download, review and run install-windows.ps1 from the release; it
checks the ZIP hash and installs to LocalAppData/Agenova/bin without admin rights.
Use Windows PowerShell. Do not change execution policy if your organization blocks
scripts; use the ZIP instead. Credentials use Windows Credential Manager.
