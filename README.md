<p align="center">
  <img src="https://img.shields.io/badge/macOS-10.15%2B-378ADD?style=flat-square" alt="macOS 10.15+" />
  <img src="https://img.shields.io/badge/Apple%20Silicon%20%2B%20Intel-universal-378ADD?style=flat-square" alt="Universal" />
  <img src="https://img.shields.io/badge/version-0.1.0%20early%20preview-B9D6F3?style=flat-square&labelColor=555" alt="Version 0.1.0" />
</p>

# Brindel

**Your clipboard, quietly remembered.**

Brindel is a small clipboard history for macOS. It keeps your last five copies, text and images, one keystroke away, and pastes the one you choose straight into the app you are using.

**[Download for macOS](https://github.com/dubey5/Brindel/releases/download/v0.1.0/Brindel_0.1.0_universal.dmg)** · [Website](https://dubey5.github.io/Brindel/) · [All releases](https://github.com/dubey5/Brindel/releases)

> **Early preview.** Brindel is shared with a small group of testers and is not yet notarised by Apple, so macOS asks you to confirm the first launch. Installation steps are below.

---

## Features

- **Your last five.** The picker shows your five most recent copies, newest first. Copy the same thing again and it moves to the top instead of repeating.
- **Text and images.** Copy a paragraph or a screenshot. Both appear in the list, and images get a small thumbnail.
- **Pin one item.** Keep something you paste often at the top until you unpin it.
- **Instant paste.** Press `Ctrl` `Cmd` `V` to paste your pinned item, or your latest copy, without opening anything.
- **Opens at your cursor.** The picker appears where you are working. Click anywhere else or press `Esc` and it closes without pasting.
- **Lives in the menu bar.** No Dock icon. Optional launch at login from the menu bar icon.
- **Six accent colours.** Choose a colour from the small dots at the bottom of the picker. Your choice is remembered.
- **Stays on your Mac.** Your history is stored locally. There is no account, and Brindel does not send your clipboard anywhere.

## Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| `Cmd` `Shift` `V` | Open the picker at your cursor |
| `Ctrl` `Cmd` `V` | Paste the pinned item, or the latest copy, instantly |
| `↑` `↓` | Move through the list |
| `Enter` | Paste the selected item |
| `1` – `5` | Paste that row directly |
| `P` | Pin or unpin the selected item |
| `Esc` | Close without pasting |

You can also click a row to paste it, and click the star on a row to pin it.

## Requirements

- macOS 10.15 Catalina or later
- Apple Silicon or Intel Mac (one universal download)

## Install

No Terminal is needed.

1. **Download** `Brindel_0.1.0_universal.dmg` from the [latest release](https://github.com/dubey5/Brindel/releases/latest) and double-click it.
2. **Drag Brindel** onto the Applications folder in the window that appears.
3. **Open Brindel** from Applications. macOS says it cannot verify the app. Choose **Done**.
4. **Approve the first launch.** Open **System Settings → Privacy & Security**, scroll to the Security section, choose **Open Anyway** beside Brindel, and confirm.
5. **Allow two permissions.** Choose **Get started** on the welcome card. macOS asks to let Brindel control System Events, then for Accessibility. Allow both.
6. **Restart Brindel once.** Choose **Quit Brindel** from its menu bar icon, then open it again. Press `Cmd` `Shift` `V` to try it.

### Why the permissions?

| Permission | Why Brindel needs it |
| --- | --- |
| **Accessibility** | To paste for you. After you pick an item, Brindel sends a Command+V key press to the app you were using. macOS only allows this when Accessibility is switched on. |
| **Automation (System Events)** | To ask which app is in front when you open the picker, so the paste lands where you were working. Nothing else is read. |

## Troubleshooting

**Pasting does not work.**
Open **System Settings → Privacy & Security → Accessibility** and check that Brindel is on. If it is on but still fails, select Brindel, press the minus (−) button to remove it, then quit and reopen Brindel and allow it again. This is most common right after installing an update.

**The picker does not open.**
Check that Brindel is running (look for its icon in the menu bar). If another app uses `Cmd` `Shift` `V`, quit that app or change its shortcut.

**Something else is wrong.**
Open an issue on this repository and include the output of this command in Terminal:

```bash
tail -n 10 ~/Library/Logs/Brindel.log
```

The log contains technical messages about Brindel only, never the contents of your clipboard.

## Updates during the preview

Brindel is signed ad-hoc while it is in early preview. Each new version may ask you to switch Accessibility on again (see the first troubleshooting item). This ends once Brindel is signed with an Apple Developer ID and notarised.

## Privacy

- Your clipboard history is stored on your Mac only.
- Brindel has no account and does not send your clipboard anywhere.
- To remove your data, quit Brindel and delete its data folder: `~/Library/Application Support/Brindel` (or `~/clipboard-history-manager` if it exists on your Mac).

## Platform support

| Platform | Status |
| --- | --- |
| macOS | Available (early preview) |
| Windows | Planned for later |
| iPhone | Not planned at this time |

## Built with

[Tauri](https://tauri.app) (Rust) with a plain HTML and JavaScript picker.

## Feedback

This is an early preview and feedback shapes what comes next. Please open an issue on this repository, or tell the person who shared Brindel with you what worked and what did not.
