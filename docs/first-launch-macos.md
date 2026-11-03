# Open PDF on macOS

PDF is free to download. This release is not notarized by Apple, so macOS may block the first launch with an unidentified-developer warning.

1. Extract the download and move **PDF.app** to **Applications**.
2. Try opening PDF once.
3. For that developer warning, open **System Settings → Privacy & Security**. Under Security, choose **Open Anyway** for PDF. Some macOS versions first show an **Open** button.
4. Confirm opening PDF and authenticate if macOS asks. Later launches open normally.

This creates an exception for PDF. It does not require a terminal command or disabling Gatekeeper. If macOS instead reports damage or malware, check the download and report the exact message.

Apple documents this process in [Open an app by overriding security settings](https://support.apple.com/en-lamr/guide/mac-help/mh40617/27/mac/27).
