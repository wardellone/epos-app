# FAQ: Epos 1

**How do I buy?** Pay €25 via Revolut at https://revolut.me/wardell, or by
Czech bank transfer (QR Platba, 600 CZK; QR sent on request). Then email
federico.neffa@gmail.com with the email address of your Google account (any
Gmail address is one). You get access to a private Google Drive folder with
the installer and its updates. No GitHub or Microsoft account needed.

**Why pay when Handy is free?** Handy is a good project. Epos focuses on
simple local dictation, personal vocabulary/corrections and accessible Settings;
the €25 supports development. No claim of being more accurate or faster.

**Microphone and shortcuts?** Choose input in General and check its level.
Native 48 kHz capture is filtered and resampled. A missing saved input falls
back to Windows default with a notice. Hold Caps Lock to dictate; it does not
toggle capitals while Epos runs, except in windows running as administrator,
where it works normally and Epos turns it off when you leave them. Change it in
Settings (restart required).
Choose the language in Settings, opened from the tray. A shortcut for the
language picker can be set there; there is none by default. Type the keys
joined by +, for example ctrl+shift+f11; it works as soon as you Save.

**Clipboard and recipient?** Epos restores supported prior clipboard content
after every sent paste, even when the editor cannot expose the exact insertion.
A newer user copy always wins. If clipboard content cannot be preserved safely,
Epos leaves it unchanged and uses direct text input in the original focused
field. Epos remembers the window where dictation started: if it changes before
delivery, the text is not inserted and a notice appears; for 2 minutes you can
still copy it with Copy last dictation in the tray menu. Changes of tab or field
inside the same window are not detected, so keep the intended field focused
until the text appears, and always check the recipient and transcript.
In some editors (VS Code, for example) Epos cannot confirm the paste: your
earlier clipboard then returns a few seconds after the text appears, and a new
press in those seconds is ignored. Wait about 5 seconds before pasting something
you copied earlier or dictating again. Epos then says "Dictation may be
incomplete": check the field, and if the text is missing, use Copy last
dictation. If you click a button, list or menu
instead of a text field, Epos refuses with "Click the text field where you want
to dictate, then hold the key again." and keeps the text in Copy last dictation.
If it cannot give your previous clipboard back, the notice says so ("Epos
couldn't restore your previous clipboard" or "clipboard recovery failed"): copy
important text again.

**How long can I dictate, and what about Bluetooth headsets?** One hold can last
up to 10 minutes: the pill shows "1 min left" from minute 9, and at 10 minutes
Epos stops and inserts what it heard (press again to continue). If the PC
locks or goes to sleep while you hold the key, that recording is discarded.
Epos keeps the microphone open while it runs, so the first word of a sentence is
never cut off. Windows therefore shows the microphone as in use, and a Bluetooth
headset stays in its phone-quality headset mode while Epos is open. For good
audio, choose the laptop's microphone or a USB one in Settings > General >
Microphone: with "Windows default", Epos follows the headset as soon as Windows
makes it the default. You can also quit Epos from the tray when you want music
or calls in good quality.

**Languages and hardware?** Epos uses Whisper models and lets you choose the
dictation language in Settings. Quality varies with language, accent, microphone
and model, so try it with your own voice during the refund period. Settings is in
English. Auto uses small on CPU, large-v3-turbo on NVIDIA with a working CUDA
runtime.
Latency varies by PC. Optional NVIDIA DLLs go in
`%APPDATA%\EPOS\runtime\cuda12-cudnn9\bin`; they are not shipped.

**Data and uninstall?** Settings/vocabulary are in `%APPDATA%\EPOS\config.json`,
corrections in `corrections.txt`, logs in `.tmp`, models in the Hugging Face cache.
New logs exclude text unless explicitly enabled. Info clears current/legacy logs.
Installing an update over Epos retains the profile. Uninstalling keeps your data
and the models.

**How do I remove everything?** Uninstall Epos from Windows Settings, then delete
the folder `%APPDATA%\EPOS` (your settings, vocabulary, corrections and logs) and
in `%USERPROFILE%\.cache\huggingface\hub` the folders
`models--Systran--faster-whisper-*` (one for each model Epos used) and, if you chose
Turbo, `models--mobiuslabsgmbh--faster-whisper-large-v3-turbo` or
`models--deepdml--faster-whisper-large-v3-turbo-ct2` (0.5 to 3 GB each). Other
programs can share that cache, so leave anything else in it alone.

**Updates, licence and refunds?** €25 once; perpetual licence for version 1
with all its updates. One user, multiple own PCs, professional use allowed. No
activation or renewal. Version 1 keeps working after a version 2, which version
1 owners get at 50% off. Epos checks for a newer version once at startup and
on request; the new installer is in the same Google Drive folder. Refund on request
within 14 days of payment: email federico.neffa@gmail.com.

**Windows warnings and hash?** SHA256 confirms identical files, not publisher
identity. SmartScreen may warn about the unsigned file's reputation; the
More info → Run anyway option may be available. Smart App Control can block
it completely. Do not disable protections as an ordinary installation step.
Investigate actual Defender detections separately.

## Known problems, one line each

- **Epos closes right after starting, or says the dictation key protection could
  not start.** Security software may have blocked `epos_key_guard.dll` in the
  Epos folder (the file is unsigned). Allow the Epos folder in it and start Epos
  again; do not switch protection off.
- **Caps Lock seems stuck on.** Epos turns it off when it starts, after you
  unlock Windows and when you leave an administrator window. If the keyboard light
  still disagrees, quit Epos from the tray and start it again.
- **Nothing is typed in Task Manager, an administrator terminal or an installer.**
  Windows keeps programs run as administrator out of reach. Caps Lock works
  normally there; dictate into a normal window.
- **PowerToys Keyboard Manager, AutoHotkey or a screen reader that uses Caps
  Lock.** Whichever program installs its keyboard hook last wins. In Settings set
  the dictation key to Scroll Lock or Pause and restart Epos.
- **"Scratch that" is typed as said.** Spoken edit commands were removed in 1.0.1,
  because natural pauses rarely made them work and they could delete text by
  mistake. Fix text with your keyboard.
- **"Comma" or "period" is typed as a word.** Epos has no spoken punctuation:
  commas, periods and question marks come from your pauses and intonation, and
  the names of symbols stay words, since they are ordinary words too.
- **The first download says it is offline or keeps failing at work.** A firewall
  or proxy that inspects secure connections blocks the download from
  huggingface.co, and Epos does not use the Windows certificate store. Download
  on another network, or copy the `models--Systran--faster-whisper-small` (or,
  with NVIDIA, `models--mobiuslabsgmbh--faster-whisper-large-v3-turbo`) folder
  from another PC's `%USERPROFILE%\.cache\huggingface\hub` into
  the same place on this one; Epos then starts without downloading.
- **The text did not appear.** If you changed window while Epos was transcribing,
  open the tray menu and choose Copy last dictation within 2 minutes, then paste.
- **Something else is wrong.** In Settings, open Info and choose Copy support
  info, then paste it into your email. It holds the version, the Windows build,
  the processor, memory, Smart App Control state, the model loaded, the
  microphone and status codes, plus counts for the current session (dictations,
  nothing inserted and why, delivery results per program, transcription speed,
  speech at the start and end of holds, missing audio), never dictated text,
  vocabulary or corrections. Before you send it, delete any personal name from
  the Microphone line.
