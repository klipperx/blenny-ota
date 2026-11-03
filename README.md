# blenny-ota

Signed firmware updates for [blenny](https://github.com/klipperx/blenny) badges.

Badges fetch `manifest.json` and `manifest.json.sig` from
`https://klipperx.github.io/blenny-ota/` when they join Wi-Fi, verify the ECDSA P-256
signature against the public key built into the firmware, and install the build for
their board only if the version is newer and the SHA-256 matches.

Generate releases with `tools/ota_release.py` in the blenny repo. Never commit the
signing key here.

`bad/` holds a deliberately tampered manifest used to test signature rejection.
