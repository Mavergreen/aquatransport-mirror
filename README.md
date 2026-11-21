# aquatransport-mirror

A byte-exact copy of every [Aqua Transport](https://github.com/Wowfunhappy/AquaTransport)
download seen at <https://mavericksforever.com/downloads/AquaTransport.dmg>.

Upstream serves one URL and overwrites it with each release, so a build pinned to an older
version can't fetch it any more. [packer-plugin-macosx](https://github.com/Mavergreen/packer-plugin-macosx)'s
`aquatransport-observer.yml` looks at that URL each day and files each new download here before
anything pins it.

## Releases

- One release per download, tagged `<version>-<first 12 hex digits of its SHA-256>`, such as
  `2026.11.17-933d5d34d302`. If upstream replaces a version's bytes without changing the version,
  the new bytes get their own release beside the old.
- `AquaTransport.dmg`: the download, unchanged.
- `AquaTransport-source-<commit>.tar.gz`: GitHub's tarball of
  [Wowfunhappy/AquaTransport](https://github.com/Wowfunhappy/AquaTransport) at that commit.
- The notes give the full SHA-256, the date first seen, and the source commit.

Nothing here is ever deleted or replaced. Check what you fetch against the SHA-256 you pinned.

## Licenses

Aqua Transport is under the MIT license in [LICENSE](LICENSE). The DMG also bundles OWL
([Open Wireless Link](https://github.com/seemoo-lab/owl)), which is under the GNU GPL, version 3.
Its source, with its license text, is in each release's source tarball under `deps/owl/`,
alongside the build scripts and the libev and OpenSSL sources the build uses.

Upstream tags no builds, and the binaries say nothing of the commit they came from. So each
source tarball is upstream's `main` at the moment the download was first seen: the best match
available, not a proven build commit. If you need the exact source of a binary here, ask the
author at <https://github.com/Wowfunhappy/AquaTransport/issues>.
