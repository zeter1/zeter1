**Язык / Language:** [Русский](SUPPORT.md) · **English**

# Support and bug reports

The main repositories use structured GitHub Issue Forms for bug reports. They are designed to collect the information needed to reproduce and diagnose a problem from the beginning.

## Before opening an issue

1. Confirm that the problem still reproduces on the current project revision.
2. Read the project's README and relevant documentation.
3. If the application creates diagnostic files, preserve the latest failing session before repeated runs or cleanup.
4. Remove personal information, secrets, and any data that should not be public from logs and attachments.

## A useful bug report

A strong report usually includes:

- application version or revision;
- Windows version;
- exact reproduction steps;
- actual result;
- expected result;
- settings that affect the scenario;
- a small relevant diagnostic excerpt;
- whether the problem reproduces consistently.

Instead of:

> the application does not work

a more useful report would be:

> Windows 11 24H2, revision X. With NVENC and system audio selected, recording starts but FFmpeg exits after 8–10 seconds. CPU encoding works with the same settings. A relevant diagnostic-log excerpt is attached.

## What should not be published

Do not publish unless explicitly necessary and reviewed first:

- passwords;
- API keys;
- OAuth tokens;
- cookies;
- private URLs;
- real crash dumps without inspecting them first;
- personal documents, audio, or video;
- an entire application user-data directory;
- logs containing private conversations or dictated text.

## Project-specific diagnostics

### Screen Recorder Pro

Useful details include capture/encoding settings, audio devices, FFmpeg context, timing information, and GPU/monitor information.

### BSOD Investigator

A safe diagnostic summary, CDB/WinDbg version, and symbol-related messages are useful. A crash dump should not be uploaded automatically to a public issue.

### VoiceFlow

Include the Whisper model, CPU/CUDA mode, compute type, microphone, and the subsystem where the problem occurs: hotkey, capture, inference, or text insertion.

### Video Translator Pro

Identify the pipeline stage: Whisper, translation, Edge TTS/gTTS, Pause Sync, FFmpeg, final validation, or recovery.

### ZeTer OS

Specify desktop/web mode and the affected module. Do not attach application state or backups containing personal data.

### Vacancy Parser Pro

Include the vacancy source, search parameters, and a safe summary of the diagnostic session.

### Universal Video Downloader

Include the site, video/MP3 mode, requested quality, yt-dlp version, and the relevant FFmpeg/yt-dlp message. Do not publish cookies or private URLs.

### Text to MP3 for Windows

Include the SAPI voice, reading/MP3 scenario, audio device, and a safe diagnostic excerpt.

### Windows PC Locker

Include sleep-prevention settings, timer configuration, and the lock/unlock sequence. Use the built-in `--self-test` for a safe baseline check.

## Security reports

For potential vulnerabilities where public disclosure could create additional risk, follow the corresponding repository's `SECURITY.md` instructions and use a private contact path first.
