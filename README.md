# CapSwap

**Keep the words and timing, swap the caption design.**

CapSwap is a free panel for Adobe Premiere Pro on Windows. It turns your captions into the Motion Graphics template (MOGRT) of your choice, and swaps the template of graphic captions you already placed, without retyping text or re-timing anything. [한국어](README.ko.md)

<!-- Demo GIF goes here: captions → one click → graphic captions, then a template swap. -->

## Download

**[Download the latest release](../../releases/latest)** and get `CapSwap-<version>-windows.zip`.

Each release lists the SHA-256 of the signed `.zxp`. The installer checks it before installing.

CapSwap never checks for updates by itself (it makes no internet connections). To hear about new versions, click **Watch → Custom → Releases** at the top of this page, or follow [Ko-fi](https://ko-fi.com/vex26).

If Windows shows a security warning when you run the installer (for example "Windows protected your PC"), choose **More info → Run anyway**, or **Run**. Windows warns about scripts downloaded from the internet; the installer itself verifies the package before installing.

## What it does

- **Captions → graphic captions in one batch.** Reads the text and start and end times straight from your sequence's caption track and places them with your MOGRT. You don't need to export an SRT or fix time offsets. SRT files work too.
- **Swap the template of selected captions.** Select graphic captions on the timeline and pick another MOGRT. CapSwap keeps the current text, timing, video track and enabled state.
- **Swap with the last template now.** Applies the last successful swap template again with one click.
- **Template browser.** Lets you browse local MOGRTs by thumbnail, with search, folders, favorites and recent picks.
- **Speaker-label templates.** Templates with a styled speaker label (`Name | `, `Janeㅣ`) keep the label and put each caption in the body style. CapSwap asks once per template layout and remembers it; swapping between label templates converts the label and keeps the body.
- **English and Korean.** Follows Premiere's language automatically; you can switch it in the panel.

## Built to be safe

- Your original captions are removed only after the new ones are verified. If something fails or you cancel, your originals stay as they were.
- Before generating, or before swapping 6 or more captions, CapSwap backs up the sequence. The 3 most recent backups are kept in a `CapSwap Backup` bin in your project.
- Your project file and your MOGRT files are never modified directly.
- CapSwap makes no internet connections. The Ko-fi link in the panel only opens your browser when you click it.

## Requirements

- Windows 10 or 11, 64-bit (tested on Windows 11)
- Adobe Premiere Pro 26.5 or later (verified on 26.5.2). On a newer version that has not been verified yet, the panel asks once before working.
- macOS is not supported.

## Install

1. Extract `CapSwap-<version>-windows.zip` and close Premiere Pro.
2. Double-click **Install-CapSwap.cmd**. No administrator rights are needed.
3. In Premiere Pro, choose **Window → Extensions → CapSwap**.

To remove CapSwap, run `Install-CapSwap.cmd uninstall` from a command prompt. Your settings are kept.

The installer checks that Premiere is closed and verifies the package checksum and signature. It backs up any existing install before replacing it (keeping only the newest backup), and it does not touch the registry.

## Quick start

1. Open the sequence with your captions.
2. **Browse** to set the default MOGRT, and choose an empty video track.
3. Click **Generate with default template**. Then hide the original caption track.
4. To restyle later, select graphic captions and click **Choose another MOGRT and swap**.

## Known limitations

- Effects, position keyframes, highlight colors and multiple style runs of existing captions are not carried over. Check the layout when the text length changes.
- Caption fonts, colors and positions are not imported; the design comes from your template.
- After Effects MOGRTs, and 23.976 fps and 29.97 fps drop-frame sequences, are not fully verified yet.
- Templates with audio, speed-changed captions and linked clips are not supported.
- There is no single-step undo for a whole job. Use the backup sequence or Premiere's undo.

Full notes for each version: [RELEASE-NOTES.md](RELEASE-NOTES.md)

## Feedback

Found a bug or have an idea? [Open an issue](../../issues). Please include your Premiere Pro version, your Windows version and your CapSwap version.

## Support

CapSwap is free. If it saves you time, you can support it on **[Ko-fi](https://ko-fi.com/vex26)** ☕

## License

You can use CapSwap for free, for personal and commercial work. You may not redistribute it, sell it or distribute modified versions. See [LICENSE](LICENSE). Third-party components are listed in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

Adobe and Premiere Pro are trademarks of Adobe. CapSwap is an independent tool and is not made or endorsed by Adobe.

This repository hosts releases and documentation only.
