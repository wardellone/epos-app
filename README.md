# Epos: local dictation for Windows

Local dictation for Windows, tuned for Italian. **€25 once. No subscription
or cloud transcription. Perpetual licence for version 1, all its updates
included.**

Hold Caps Lock, speak and release. Epos transcribes on your PC and pastes
into the active window. Personal vocabulary and corrections help with
your terminology, while Italian scratch commands let you discard a
sentence before it is pasted.

If you are looking for Windows dictation software without a subscription,
Epos is a possible alternative to Wispr Flow, Superwhisper for Windows or
Dragon. It offers simple local dictation, without promising every feature
of those products or making unverified accuracy or speed comparisons.

## How to buy

1. Pay **€25** via Revolut at **https://revolut.me/wardell**. In Czechia you
   can also pay 600 CZK by bank transfer: ask for the QR Platba code by email.
2. Email **federico.neffa@gmail.com** with the email address to use for
   the download.
3. You receive access to a private OneDrive folder with the installer, its
   SHA256 hash and the installation guide. Every version 1 update appears in
   the same folder. No GitHub or Microsoft account is needed.

Refunds on request within 14 days of payment: write to the same address.
This repository contains the product page, terms, update manifest and free
third-party sources. The Epos source code and installer are not published here.

## Requirements and usage

The reference platform for testing is 64-bit Windows 11. You need a
microphone and an internet connection for the initial model download,
approximately 0.5 to 1.6 GB depending on the model. Dictation works offline
after the download. The complete app requires additional storage.
CPU transcription can take several seconds; it is not instantaneous.

Install Epos, wait for Ready and complete the welcome screen. Hold Caps Lock,
speak and release. Caps Lock does not toggle capital letters while Epos is
running. Change the hotkey in Settings, opened from the tray icon.

Epos restores supported prior clipboard content after every sent paste, even
when the target editor cannot expose the exact insertion. A newer user copy
always wins. Select the correct field before dictating and keep it focused until
the text appears. If the clipboard cannot be preserved safely, Epos leaves it
unchanged and uses direct text input in the original focused field.

Italian and English are the reference languages for validation. Other
languages have no specifically verified quality guarantee. Settings and the
welcome screen are in English.

## Privacy

Epos does not send audio or transcripts. Audio stays in memory and the
model runs on your PC. Model downloads from Hugging Face and the update check
on GitHub (once at startup and on request) send technical connection data,
such as your IP address, to those services. There is no telemetry.
Configuration and logs are stored in `%APPDATA%\EPOS`.

New logs exclude dictated text unless you explicitly enable diagnostic
text logging. Historical logs may contain it. During delivery, the transcript
briefly occupies the Windows clipboard; synchronisation by Windows or other
software depends on their settings.
See the [privacy notice](PRIVACY.md).

## Licence, updates and Windows

The personal licence covers one user on multiple PCs owned by that user,
including professional use. It is perpetual for version 1 and includes all
version 1 updates. Version 1 keeps working after a version 2 is released, and
version 1 owners get version 2 at 50% off. There is no activation.
See the [terms](TERMS.txt).

Epos checks this repository's `latest.json` once at startup and shows a
notice when a newer version is available. You can also check from the tray
or Info. Updates are not downloaded or installed automatically: get the new
installer from your OneDrive folder and install it over the current one.
Your settings are kept.

Version 1.0 is unsigned. SmartScreen may show a warning because the file has
not established a reputation. If Windows offers it, you can select
**More info → Run anyway** after checking the download's source. Smart App
Control can block execution without that option. Disabling protections is not
an ordinary installation requirement.

To check your download in PowerShell:

```powershell
Get-FileHash .\Epos-Setup-1.0.0.exe -Algorithm SHA256
```

Compare the result with the `sha256` value in [latest.json](latest.json).
A match confirms that the files are identical; it does not certify the
developer's identity or replace a digital signature.

## Third-party sources

Epos uses FFmpeg, PyAV and pystray under LGPL licences. Their corresponding
sources and build recipe are available free of charge in this repository's
[Releases](../../releases).

[FAQ](FAQ.md#english-faq) · [Changelog](CHANGELOG.md)
