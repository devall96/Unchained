**Unchained 0.1.2**: a small update for players on **Linux who use [RecompLauncher](https://recomplauncher.com/game/unchained)**. Your saves, settings and logs now live in the launcher's own data folder for the game, so a launcher update of Unchained can no longer replace them. Gameplay and the picture are the same as 0.1.1, and nothing changes on Windows or for the AppImage run by itself.

> **Bring your own copy.** No game files are included. You need your own *Whiplash* for the original Xbox (USA), as a disc image or its extracted files. The game's code is built on your PC from your copy the first time you start it.

## Downloads

| File | For |
| --- | --- |
| `Unchained-0.1.2-Windows-x64-Setup.exe` | Windows 10 / 11: the installer (for your user only, no admin) |
| `Unchained-0.1.2-Windows-x64.zip` | Windows: portable, extract and run |
| `Unchained-0.1.2-Linux-x86_64.AppImage` | Linux and Steam Deck: one file, everything inside |
| `SHA256SUMS.txt` | Checksums |

Unchained isn't code-signed yet, so Windows SmartScreen may warn on the first run (More info → Run anyway).

## What's new

- **Linux, RecompLauncher: your data in the launcher's data folder.** RecompLauncher unpacks the AppImage and replaces that folder on every update. 0.1.1 kept saves, settings, logs and the built game code inside it; 0.1.2 keeps them in the launcher's data folder for the game (`recompdata`) instead.
- **What you already have is carried over.** On the first start, your settings, saves (the console's hard disk), save backups, save profiles, logs, texture packs, colour LUTs and screenshots are copied there once. They're copied, never moved, so the old files stay where they were. A copy that was interrupted or ran out of disk space is thrown away and tried again on the next start, and until it has succeeded Unchained keeps using the old place.
- **The launcher's Saves, Logs and settings** point at the new place (`recomplauncher.json`), and still find the old one on an install that hasn't started 0.1.2 yet.

Thanks to **[@Xarishark](https://github.com/Xarishark)** for both pull requests ([Unchained#1](https://github.com/devall96/Unchained/pull/1), [XboxXBERecomp#1](https://github.com/devall96/XboxXBERecomp/pull/1)).

## How it was tested

On Ubuntu 26.04, started the way RecompLauncher starts it (the unpacked AppImage, with the launcher's data folder set): a fresh install, and a 0.1.1 install with saves, a save backup, a texture pack folder, a colour LUT and a screenshot updated to this build. The copied files matched the originals byte for byte and the game started on them. Not checked: the launcher's own Saves, Logs and settings buttons inside RecompLauncher, and loading the carried-over save in game. Please report anything odd.

## Known issues

The same as 0.1.1: some of the partner's spoken lines don't play yet, the lab's wall-lamp beams flicker at some distances, only the opening levels have been played through, and the frame cap stays at 60 by default.

*Unchained is a fan project, not affiliated with Crystal Dynamics, Eidos, Square Enix, Embracer Group or Microsoft. Made with AI: written by Claude (Anthropic) through Claude Code, directed and played by devall96.*
