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
toggle capitals while Epos runs. Change it in Settings (restart required).
Choose the language in Settings, opened from the tray. A shortcut for the
language picker can be set there; there is none by default. Type the keys
joined by +, for example ctrl+shift+f11; it works as soon as you Save.

**Clipboard and recipient?** Epos restores supported prior clipboard content
after every sent paste, even when the editor cannot expose the exact insertion.
A newer user copy always wins. If clipboard content cannot be preserved safely,
Epos leaves it unchanged and uses direct text input in the original focused
field. Epos remembers the window where dictation started: if it changes before
delivery, the text is not inserted and a notice appears. Changes of tab or field
inside the same window are not detected, so keep the intended field focused
until the text appears, and always check the recipient and transcript.

**Languages and hardware?** Epos uses Whisper models and lets you choose the
dictation language in Settings. Quality varies with language, accent, microphone
and model, so try it with your own voice during the refund period. Settings is in
English. Auto uses small on CPU, medium on NVIDIA with a working CUDA runtime.
Latency varies by PC. Optional NVIDIA DLLs go in
`%APPDATA%\EPOS\runtime\cuda12-cudnn9\bin`; they are not shipped.

**Data and uninstall?** Settings/vocabulary are in `%APPDATA%\EPOS\config.json`,
corrections in `corrections.txt`, logs in `.tmp`, models in the Hugging Face cache.
New logs exclude text unless explicitly enabled. Info clears current/legacy logs.
Uninstall keeps data and models by default; shared model caches require separate
careful cleanup. Installing an update over Epos retains the profile.

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
