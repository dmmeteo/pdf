# PDF

A quiet PDF reader and annotator: highlights and notes saved into the PDF, page rail, Find, a command
palette, and themes. Free to download. The application's source code is not public; this repository
holds release documentation, checksums and third-party notices, and its
[Releases](https://github.com/dmmeteo/pdf/releases) page carries the downloads.

Website: https://bullshitai.dev/pdf/

<a href="https://slint.dev" aria-label="Made with Slint"><img src="assets/made-with-slint.png" alt="Made with Slint" width="160"></a>

The interface is built with [Slint](https://slint.dev) 1.18.1 under the Slint Royalty-free License 2.0.
This badge on the public download page is the attribution that license asks for.

## Downloads (v1.0.0)

| Platform | File | Requirements | Tested |
|---|---|---|---|
| macOS | [`PDF-1.0.0-macos-arm64.dmg`](https://github.com/dmmeteo/pdf/releases/download/v1.0.0/PDF-1.0.0-macos-arm64.dmg) (disk image) | Apple silicon (arm64), macOS 27.0.1 or later | built natively from the 1.0.0 source; opened a PDF and quit normally on a Mac |
| Linux | `PDF-1.0.0-linux-x86_64.tar.gz` | x86_64, glibc 2.36 or later, X11 or Wayland | started and rendered a PDF in a Debian 12 container |
| Windows | `PDF-1.0.0-windows-x86_64.zip` | 64-bit Windows (x86_64) | started and rendered a PDF under Wine 11 on Linux; not yet tested on a Windows PC |

Download from the [v1.0.0 release](https://github.com/dmmeteo/pdf/releases/tag/v1.0.0). Verify each file against
[SHA256SUMS](SHA256SUMS): `shasum -a 256 <file>` (macOS), `sha256sum <file>` (Linux) or
`Get-FileHash <file>` (Windows PowerShell).

**About the version number.** The first release is version 1.0.0. It was first published as v0.1.0.
The Linux and Windows 1.0.0 archives contain the same tested executables as their v0.1.0 archives; only the
archive name and the version named in the notices changed, so they were not tested again. The macOS app
records its version inside the executable, so macOS 1.0.0 is a new native build from the 1.0.0 source, shipped
as a disk image. The [v0.1.0 release](https://github.com/dmmeteo/pdf/releases/tag/v0.1.0), including the
earlier macOS zip, stays available.

## Install

- **macOS:** open the disk image and drag PDF.app onto the Applications folder. PDF.app has an ad hoc
  signature only: it is not signed with an Apple Developer ID and not notarized by Apple. See
  [first launch on macOS](docs/first-launch-macos.md) for the one-time Open Anyway step.
  It does not need a terminal command and does not turn off Gatekeeper.
- **Linux:** extract the archive and run `PDF-x86_64.AppDir/AppRun` (it sets up the bundled libraries).
- **Windows:** extract the whole zip, keep its folders together, and run `bin\pdf-notes.exe`. The app is not
  code-signed, so Windows SmartScreen may show "Windows protected your PC" the first time; choose
  More info, then Run anyway.

## What is inside

Each archive bundles PDFium for rendering and Tesseract with English and Ukrainian models for OCR.
Third-party licenses ship inside every archive: `THIRD-PARTY-NOTICES/` (macOS, in the disk image),
`usr/Resources/licenses/` (Linux) and `licenses/` (Windows). See [docs/notices.md](docs/notices.md).

The Linux and Windows archives bundle some LGPL/GPL libraries. Their corresponding source is published on the
same release page: `PDF-1.0.0-linux-debian-sources.tar` and `PDF-1.0.0-windows-msys2-sources.tar`.
[docs/notices.md](docs/notices.md) explains how each library's version was identified and where that is
inferred rather than hash-proven.

## Security and privacy

Documents are opened and annotated locally. Report a security problem privately through
[GitHub security advisories](https://github.com/dmmeteo/pdf/security/advisories/new) for this repository.

## Support

Issues: https://github.com/dmmeteo/pdf/issues · Coffee: https://buymeacoffee.com/dimaforcepush
