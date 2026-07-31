# IDEAI — downloads

Binaries only. This repo exists so IDEAI's in-app updater and the installer can
fetch releases without a GitHub login; the source lives in a private repo and is
mirrored here as build artifacts by CI on every tag.

## Install (Apple Silicon)

```sh
curl -fsSL https://github.com/ClarkeFL/IDEAI-releases/releases/latest/download/install.sh | sh
```

No Gatekeeper prompt: `curl` doesn't set the `com.apple.quarantine` flag that
invokes it. The app updates itself from here after that.

### DMG instead

Grab `IDEAI_x.y.z_aarch64.dmg` from [Releases](../../releases/latest), drag
`IDEAI.app` to `/Applications`, then **first launch only**: right-click →
**Open** → confirm. The app is signed with a self-signed certificate rather than
a paid Apple Developer ID, so Gatekeeper asks once and then remembers.

## What's in a release

| asset | what it's for |
| --- | --- |
| `IDEAI_aarch64.app.tar.gz` + `.sig` | the updater feed and `install.sh` |
| `IDEAI_x.y.z_aarch64.dmg` | manual browser download |
| `latest.json` | updater manifest (`plugins.updater.endpoints`) |
| `install.sh` | the installer the command above pipes to `sh` |
