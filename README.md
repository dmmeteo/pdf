# PDF

A quiet PDF reader and annotator: highlights and notes saved into the PDF, page rail, Find, a command
palette, and themes. Free to download. The application's source code is not public; this repository
holds release documentation, checksums and third-party notices. The links below always download the latest
version; earlier versions stay on the [Releases](https://github.com/dmmeteo/pdf/releases) page.

Website: https://bullshitai.dev/pdf/

<a href="https://slint.dev" aria-label="Made with Slint"><img src="assets/made-with-slint.png" alt="Made with Slint" width="160"></a>

The interface is built with [Slint](https://slint.dev) 1.18.1 under the Slint Royalty-free License 2.0.
This badge on the public download page is the attribution that license asks for.

## Downloads (latest version)

| Platform | Download | Requirements |
|---|---|---|
| macOS | [Apple silicon disk image](https://artifacts.dmmeteo.dev/pdf/latest/macos-arm64) | Apple silicon (arm64), macOS 27.0.1 or later |
| Linux | [x86_64 AppImage](https://artifacts.dmmeteo.dev/pdf/latest/linux-x86_64) | x86_64, glibc 2.36 or later, the host's desktop, fonts and graphics libraries |
| Linux | [arm64 AppImage](https://artifacts.dmmeteo.dev/pdf/latest/linux-arm64) | arm64, glibc 2.36 or later, the host's desktop, fonts and graphics libraries |
| Debian 12 | [amd64 package](https://artifacts.dmmeteo.dev/pdf/latest/debian12-amd64) | Debian 12 (bookworm) only, x86_64; not other Debian or Ubuntu releases |
| Debian 12 | [arm64 package](https://artifacts.dmmeteo.dev/pdf/latest/debian12-arm64) | Debian 12 (bookworm) only, arm64; not other Debian or Ubuntu releases |

Checksums for the latest version: [SHA256SUMS](https://artifacts.dmmeteo.dev/pdf/latest/sha256sums). Verify a file with `shasum -a 256 <file>`
(macOS) or `sha256sum <file>` (Linux).

On Linux, the app was checked on X11; Wayland is not verified.

**Updates.** PDF 1.0.1 and later have built-in updates on macOS and in the Linux AppImage. A Debian 12
installation updates through apt with the newer package and does not replace itself with an AppImage.
The macOS and Linux 1.0.0 downloads have no built-in updater: install the latest version above once by hand
to join the 1.0.1+ update channel.

## Windows (v1.0.0)

| Platform | File | Requirements | Tested |
|---|---|---|---|
| Windows | `PDF-1.0.0-windows-x86_64.zip` | 64-bit Windows (x86_64) | started and rendered a PDF under Wine 11 on Linux; not yet tested on a Windows PC |

Download from the [v1.0.0 release](https://github.com/dmmeteo/pdf/releases/tag/v1.0.0) and verify it against
[SHA256SUMS](SHA256SUMS) with `Get-FileHash <file>` (Windows PowerShell).

## Release history

v1.0.0 also shipped these macOS and Linux downloads, now superseded by the latest version above:

| Platform | File | Requirements | Tested |
|---|---|---|---|
| macOS | [`PDF-1.0.0-macos-arm64.dmg`](https://github.com/dmmeteo/pdf/releases/download/v1.0.0/PDF-1.0.0-macos-arm64.dmg) (disk image) | Apple silicon (arm64), macOS 27.0.1 or later | built natively from the 1.0.0 source; opened a PDF and quit normally on a Mac |
| Linux | `PDF-1.0.0-linux-x86_64.tar.gz` | x86_64, glibc 2.36 or later | started and rendered a PDF in a Debian 12 container |

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
- **Linux AppImage:** save it as `~/Applications/PDF.AppImage` so it can update itself, then make it executable
  and add it to the app menu (this step needs Python 3):

  ```sh
  chmod +x ~/Applications/PDF.AppImage
  ~/Applications/PDF.AppImage --install-desktop
  ```
- **Debian 12:** `sudo apt install ./PDF-<version>-debian12-amd64.deb` (or the arm64 file). apt installs its
  dependencies, including zenity and the X11 keyboard bridge `libxkbcommon-x11-0`. Install a newer package the
  same way to update.
- **Linux 1.0.0 archive (history):** extract the archive and run `PDF-x86_64.AppDir/AppRun` (it sets up the
  bundled libraries).
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
