# Agenova Homebrew tap

Public macOS preview distribution of the [Agenova CLI](https://github.com/wunderforge/agenova).

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

[New member guide and example](https://github.com/wunderforge/agenova/blob/19f22c1/docs/member-quickstart.zh-CN.md).

## Updates

```bash
brew update
brew upgrade Leo1piece/agenova/agenova
```

This is a preview from Agenova PR #216, not a stable release. The formula pins an
immutable source archive and SHA-256 checksum. Homebrew installs the Go build
dependency and compiles the native CLI locally with macOS Keychain support.
No prebuilt bottles or Developer ID notarization are claimed. Apple Silicon is
locally verified; Intel installation is not yet verified.

macOS may ask for Keychain permission. Choose Always Allow only for the Agenova
executable you installed. Upgrades or a locked keychain may require consent again.
This repository contains no tokens, passwords or cloud credentials.

If you previously installed the local `agenova/preview` tap, switch with:

```bash
brew uninstall agenova/preview/agenova
brew untap agenova/preview
brew install Leo1piece/agenova/agenova
```

Uninstalling the executable does not intentionally remove application credentials
or saved server configuration. You may still need to sign in again.
