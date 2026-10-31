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
- Filler words no longer leave stray commas or periods.
- The final page of the installer shows the correct settings folder.
- The Ready indicator always appears on the laptop's own screen, even when
  docked with other displays.
- Settings: aligned navigation icons, a compact status chip, a status line
  that no longer repeats itself and a tidier Info page.

Going back to 1.0.0: 1.0.0 does not start without a quit shortcut. Before
installing it again, open Settings in 1.0.1, set a quit shortcut (for
example ctrl+shift+f12) and Save.

## 1.0.0

- Visible startup, model download with progress and a repeatable Retry.
- Selectable microphone, audio level and capture at the native sample rate.
- In-memory audio; transcript text excluded from standard logs; log rotation
  and cleanup.
- Welcome screen and protection against delivery to a changed window.
- Startup notice when a newer version is available; no activation or
  subscription.
