# Changelog

## 1.0.1

- Starts without a network connection once the speech model has been
  downloaded. Model downloads send no usage telemetry, and a stalled or
  interrupted download ends with a Retry message.
- A damaged settings or corrections file no longer prevents startup: it is
  kept under a new name and Epos continues from the last backup or defaults.
- An invalid shortcut can no longer stop Epos from starting, and Settings
  checks the shortcuts before saving. There are no default global
  shortcuts any more, because Ctrl+Alt combinations clash with AltGr
  characters: quit from the tray icon and choose the language in Settings,
  or set your own shortcuts there. Settings shows how to type them
  (for example ctrl+shift+f12), and they work as soon as you Save.
- When Epos cannot start it explains why in a message window. Starting it
  again while it is running opens its Settings.
- Dictated text is kept out of the Windows clipboard history and the cloud
  clipboard while it is being inserted.
- Spoken edit commands such as "scratch that" have been removed: what you
  say is always typed as said, and no sentence is ever deleted by a phrase
  that happened to match a command.
- Punctuation names such as "comma" or "period" are typed as words instead of
  becoming symbols, so sentences that use them as ordinary words stay intact.
  Commas, periods and question marks come from your pauses and intonation.
- Filler words no longer leave stray commas or periods.
- The final page of the installer shows the correct settings folder.
- The Ready indicator always appears on the laptop's own screen, even when
  docked with other displays.
- Settings: aligned navigation icons, a compact status chip, a status line
  that no longer repeats itself and a tidier Info page.
- Caps Lock: if it is on when Epos starts, after you unlock Windows or when you
  leave a window run as administrator, Epos turns it off. Unplugging or
  reconnecting a keyboard no longer closes Epos, and Epos recovers if Windows
  removes its keyboard hook; if Caps Lock gets through meanwhile, Epos turns it
  off again. In windows run as administrator Caps Lock works
  normally and Epos says it cannot dictate there.
- A recording is discarded if the PC locks or goes to sleep during the hold,
  and one hold now ends by itself after 10 minutes (a warning shows at 9).
- Nothing is recorded for Epos's own windows or when no window is in front, and
  Epos waits for Shift, Ctrl, Alt and Windows to be released before pasting.
  A dictation that could not be inserted can be copied for 2 minutes with
  Copy last dictation in the tray menu. Insertion into Notepad and other plain
  edit controls is exact when Epos cannot use the clipboard.
- Microphones connected after Epos started, and a new Windows default, are
  picked up without restarting. Microphones with several channels work. The
  last syllable before you let go of the key is kept. A silent or blocked
  microphone is reported, with a button to Windows privacy settings, and a
  recording with no speech says so.
- Notices no longer take the keyboard focus and appear in the bottom-right
  corner of the main screen. The recording pill no longer reacts to clicks.
  Check updates shows its result in a notice.
- First start: the welcome explains the one-time model download, the Ready
  state and where the tray icon is. Closing it with the X counts as seen.
- Settings: the language cards say what they do, Precision follows the device,
  Advanced values are limited to sensible ranges and can be reset, and a saved
  language or sound choice is not undone by Save. If CUDA fails, Epos runs the
  small model on the CPU and says so. The default style prompt is no longer
  tied to one language, and short phrases are less likely to be recognised in
  the wrong language.
- Support: logs carry the date and time and can no longer fail on a full disk,
  failures are logged by type and code, and Info has Copy support info (version,
  Windows build, microphone, status; never dictated text, vocabulary or
  corrections).
- Installer: upgrades replace the program folder cleanly, the message about a
  running Epos says to quit it from the tray icon, Start with Windows is only
  offered for a per-user install, Windows 10 or later (64-bit) is required, and
  the final message says where settings and models stay.

Going back to 1.0.0: after a Save with 1.0.1 or later, the saved settings have
no quit shortcut and 1.0.0 does not start without one. Before installing 1.0.0
again, open Settings, set a quit shortcut (for example ctrl+shift+f12) and
Save. If 1.0.0 already refuses to start, add a quit shortcut to
`%APPDATA%\EPOS\config.json` by hand.

## 1.0.0

- Visible startup, model download with progress and a repeatable Retry.
- Selectable microphone, audio level and capture at the native sample rate.
- In-memory audio; transcript text excluded from standard logs; log rotation
  and cleanup.
- Welcome screen and protection against delivery to a changed window.
- Startup notice when a newer version is available; no activation or
  subscription.
