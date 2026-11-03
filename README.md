# PDF

A quiet PDF reader and annotator: highlights and notes saved into the PDF, page rail, Find, a command
palette, and themes. Free to download. The application's source code is not public; this repository
holds release documentation, checksums and third-party notices, and its
[Releases](https://github.com/dmmeteo/pdf/releases) page carries the downloads.

Website: https://bullshitai.dev/pdf/

<a href="https://slint.dev" aria-label="Made with Slint"><img src="assets/made-with-slint.png" alt="Made with Slint" width="160"></a>

The interface is built with [Slint](https://slint.dev) 1.18.1 under the Slint Royalty-free License 2.0.
This badge on the public download page is the attribution that license asks for.

## Downloads (v0.1.0)

| Platform | File | Requirements | Tested |
|---|---|---|---|
| macOS | `PDF-0.1.0-macos-arm64.zip` | Apple silicon (arm64), macOS 27.0.1 or later | accepted on a Mac |
| Linux | `PDF-0.1.0-linux-x86_64.tar.gz` | x86_64, glibc 2.36 or later, X11 or Wayland | started and rendered a PDF in a Debian 12 container |
| Windows | not yet available | 64-bit Windows | a build exists and rendered a PDF under Wine 11, but it is not offered until the notices for its bundled MinGW libraries are complete |

Files appear on the Releases page when v0.1.0 is published. Verify each download against
[SHA256SUMS](SHA256SUMS): `shasum -a 256 <file>` (macOS) or `sha256sum <file>` (Linux).

## Install

- **macOS:** extract the zip and move PDF.app to Applications. This release is not notarized by Apple;
  see [first launch on macOS](docs/first-launch-macos.md) for the one-time Open Anyway step.
  It does not need a terminal command and does not turn off Gatekeeper.
- **Linux:** extract the archive and run `PDF-x86_64.AppDir/AppRun` (it sets up the bundled libraries).

## What is inside

Each archive bundles PDFium for rendering and Tesseract with English and Ukrainian models for OCR.
Third-party licenses ship inside every archive: `THIRD-PARTY-NOTICES/` (macOS) and
`usr/Resources/licenses/` (Linux). See [docs/notices.md](docs/notices.md).

## Security and privacy

Documents are opened and annotated locally. Report a security problem privately through
[GitHub security advisories](https://github.com/dmmeteo/pdf/security/advisories/new) for this repository.

## Support

Issues: https://github.com/dmmeteo/pdf/issues · Coffee: https://buymeacoffee.com/dimaforcepush
