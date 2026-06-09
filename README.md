# Scriptura Live — Updates mirror

This repository **does not contain Scriptura Live source code**.

Its only purpose is to host the public `latest.json` manifest and signed installers that the Scriptura Live desktop app's auto-updater polls. The actual Scriptura Live source lives in a separate, private repository.

The "Source code (zip/tar.gz)" links GitHub auto-generates on each release contain only this README — there is no source code to expose here.

## Why a separate repo

Tauri's updater plugin fetches the update manifest via anonymous HTTP. Anonymous requests cannot read assets from a private repo, so the manifest and signed installers must be hosted publicly. Keeping them in a dedicated mirror repo means the source code stays private while the auto-updater works.

## Verifying a release

Every installer is signed with a minisign keypair. The matching public key is baked into every installed copy of Scriptura Live, so a tampered installer will be rejected before it runs. The `.sig` file on each release is the detached signature.
