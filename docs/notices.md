# Third-party notices

Every release archive carries the full notices for what it bundles:

- **Slint 1.18.1** (UI toolkit): Slint Royalty-free License 2.0. Attribution under its section 2(b) is the
  official badge in this repository's README, which is the public download page.
- **PDFium** (bblanchon/pdfium-binaries, chromium/7881): BSD-style license, `LICENSE` shipped with the binary.
- **Tesseract** with Leptonica, and `tessdata_fast` English/Ukrainian models: Apache License 2.0.
- **Rust crates** compiled into the app: full license texts per crate and version.
- **Fonts and icons** in the interface: Fixel (SIL OFL 1.1), Phosphor icons (MIT).
- **Linux:** the Debian copyright file of each bundled shared library. Each bundled library is byte-identical
  to a named Debian 12 package (`licenses/debian/`).
- **Windows:** the Tesseract build's runtime DLLs come from MSYS2 MINGW64 packages. `licenses/TESSERACT-DLLS.txt`
  maps every DLL to an MSYS2 package version and its license, and `licenses/msys2/` holds the full license texts
  from that version's upstream source. The versions are the MSYS2 recipes current on the Tesseract build date
  (2024-06-06), and they agree with every version string the DLLs embed. MSYS2 no longer hosts those 2024
  binary packages, so the DLL bytes are not hash-proven against them, and DLLs without an embedded version
  rest on the build date alone.

## Corresponding source

The LGPL/GPL libraries bundled in the Linux and Windows archives have their complete corresponding source on
the [v1.0.0 release page](https://github.com/dmmeteo/pdf/releases/tag/v1.0.0), next to the downloads
(the v0.1.0 release page carries the same files under their 0.1.0 names):

- `PDF-1.0.0-linux-debian-sources.tar`: Debian source packages for glibc (libresolv), GnuTLS, Nettle, GMP,
  libunistring, libidn2, libtasn1, JBIG-KIT, librtmp, keyutils, acl and the GCC 12 runtime libraries.
- `PDF-1.0.0-windows-msys2-sources.tar`: the MSYS2 recipes, patches and upstream sources for GLib, cairo,
  Pango, FriBidi, libthai, libdatrie, libiconv, gettext (libintl), Graphite2, JBIG-KIT and the GCC 14 runtime
  libraries.

Each tar file has a `README.txt` that lists the versions and the SHA-256 of every file. The Linux libraries are
byte-identical to the named Debian packages. For Windows, every upstream file matched its MSYS2 recipe's checksum
except Pango's `720.patch`, which GitLab regenerates; its three commits are named instead. These files were
checked as present and matching. That is not a legal guarantee.

Questions about notices: open an issue.
