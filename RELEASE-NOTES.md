# CapSwap release notes

[한국어](RELEASE-NOTES.ko.md)

## 0.8.1

- **Favorites at a click.** A star button next to the template browser's search box shows only your favorites; click it again to see everything. It stays in step with the Favorites filter, and the browser remembers it the next time it opens.

## 0.8.0 (2026-10-10)

- **Templates with several text styles now work.** Templates made in Premiere whose text mixes styles used to stop with "several style runs are not supported". The first time a layout appears, CapSwap asks once whether its styled text is a speaker label (`Name | `, `Janeㅣ`) and remembers the answer for every template shaped the same way. Label layouts keep the label and put each caption in the body style; others put the whole caption in the body style. Premiere's older built-in templates are covered too.
- **Label templates swap into each other.** A caption made with a speaker-label template swaps to another with the body kept and the label converted (`John | body` → `Janeㅣbody`), or to a plain template with the body only, without asking.
- **Steadier template browser.** The browser keeps its size when a search finds nothing, so the buttons no longer jump, and cards no longer shift when a scrollbar appears. Scrollbars are thin and match the panel.
- **Reset saved choices.** The new ⚙ button next to the language menu resets what CapSwap remembered per template (it asks again next time) or all settings. The previous settings are kept as `settings.backup.json`.

## 0.7.4 — First public alpha (2026-10-08)

**Keep the words and timing, swap the caption design.** CapSwap is a Windows panel for Premiere Pro that turns captions and graphic captions into the Motion Graphics template (MOGRT) of your choice. This is the first public alpha.

### Features

- **Generate graphic captions from captions in one batch**: reads the text and start and end times straight from the sequence's caption track and places them with the MOGRT you choose. No SRT export or time offset needed. If there are several caption tracks (for example one per language) you pick one, and you can also generate from an SRT file.
- **Swap the template of selected captions**: changes the graphic captions you select on the timeline to another MOGRT, keeping the current text, start and end time, video track and disabled state.
- **Swap with the last template now**: applies the last successful swap template again with one click.
- **Template browser**: browse local MOGRT folders with thumbnails, with search, folder registration, favorites and recent choices.
- **English and Korean UI**: follows Premiere's language automatically (unsupported languages use English), and you can switch it in the panel. The installer speaks the Windows display language.

### Safety

- Existing captions are removed only after the new captions' text and length are verified. If preparation fails or you cancel, your originals are unchanged.
- Before generating, and before swapping 6 or more captions, the sequence is backed up to the project's `CapSwap Backup` bin (the 3 most recent are kept). Swaps of 5 or fewer skip the backup for speed.
- Temporary files and derived template assets that are no longer used are cleaned up automatically when a job ends.
- Your project file and original MOGRTs are never modified directly. CapSwap makes no internet connections and sends nothing anywhere; the Ko-fi link in the panel only opens your browser when you click it.

### Requirements

- Windows, Adobe Premiere Pro 26.5 or later. Verified on Premiere 26.5.2.
- On Premiere versions not yet verified, the panel shows a warning and asks once before the first job on that version.
- macOS is not supported.

### Install

1. Extract `CapSwap-0.7.4-windows.zip` and close Premiere Pro.
2. Double-click `Install-CapSwap.cmd`. No administrator rights are needed.
3. In Premiere Pro, open **Window → Extensions → CapSwap**.

The package is signed; the installer checks its SHA-256 and signature file before installing. To remove CapSwap, run `Install-CapSwap.cmd uninstall`.

### Support

CapSwap is free. If it saves you time, you can support it at [ko-fi.com/vex26](https://ko-fi.com/vex26). Use is free for personal and commercial work; redistribution is not allowed. See [LICENSE](LICENSE).

### Known limitations

- Effects, position keyframes, highlight colors and several style runs of existing captions are not carried over to the new template. Check layout and motion length when the number of characters changes.
- Caption fonts, colors and positions are not imported; the design comes from the template you choose.
- MOGRTs made in After Effects, and 23.976 fps and 29.97 fps drop-frame sequences, are not fully verified yet.
- Templates with audio, captions with changed speed and captions with linked clips are not supported.
- There is no single-step undo for a whole job. Use the backup sequence or Premiere's undo.
- Reading caption text relies on Premiere's internal file format. Check the results after Premiere updates.
- Premiere does not support panel shortcuts, so every feature runs from the panel buttons.
