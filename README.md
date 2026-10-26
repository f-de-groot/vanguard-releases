<img src="icon.png" width="96" alt="" align="left">

# Vanguard

A local development environment for Windows 11, in one desktop app.

<br clear="left">


- Park a folder and every project inside it is served at `https://<name>.test`,
  with a certificate your browser trusts.
- Install PHP versions side by side, 7.0 through 8.5, and pick one per site.
- Manage Node versions the same way. `php` and `node` end up on your PATH.
- Catch outgoing mail locally and read it in the app.
- Run MySQL or MariaDB as a service, and work in them with Keep, the built-in
  database client.
- Start Redis, Meilisearch, RustFS (S3-compatible storage) and Laravel Reverb
  with one click, each with a ready-to-paste `.env` block.

## Keep and production databases

- Saved connections and their passwords are encrypted. With a password set
  (Keep's settings), Keep asks for it when it opens and again after Windows
  locks or sleeps. It only works for your Windows account, so a copy of
  Keep's file is no use elsewhere. Save the recovery key it shows: without
  it, a lost password means starting again.
- On any server that is not on your machine, a DROP or TRUNCATE first shows
  a warning and then asks for that database's password.

## Terms

This app is an internal tool, not open-source software and not a product. It is intended for
the copyright holder and the people working with him, who may install and use it for their own
work. Making the installers reachable here does not license anyone else to use, redistribute,
mirror or repackage them.

The app is provided **as is**, with no warranty and no support commitment.

Copyright (c) 2026 F. de Groot. All rights reserved. The libraries the app bundles carry their
own licences, listed in the application's `NOTICE.md`.

## Install

Download `Vanguard_x.y.z_x64-setup.exe` from the release marked **Latest** under
[Releases](https://github.com/f-de-groot/vanguard-releases/releases) and run it.
A new version appears here once Microsoft has confirmed that Windows Defender
should not flag it, which usually takes a day or two after it is built.

The installer is not signed, so SmartScreen warns once: More info, then Run
anyway. Everything Vanguard downloads lives in `%USERPROFILE%\.vanguard\`.

Not being signed has a second consequence: Windows Defender and Malwarebytes
occasionally judge the install on behaviour alone and quarantine it, Defender
usually as `Trojan:Win32/Bearfoos.A!ml`. Vanguard edits the Windows hosts file and puts its own `php` and `node` on your
PATH, which is what it is for, and a scanner with no signature to go on cannot
tell that apart from something unwelcome. Every release is reported to
Microsoft as a false positive before Vanguard offers it as an update, but
Defender can still change its mind later. If it happens to you:

- **Windows Defender:** in Windows Security, go to Virus & threat protection,
  Protection history, open the Vanguard detection and choose Actions, Restore.
  That brings back Vanguard, its shortcuts and its uninstall entry. Installing
  again instead does not help: Defender takes the same file again.
- **Malwarebytes:** restore it under Detection History, Quarantine, and add
  `C:\Program Files\Vanguard` under Allow List.

Then, in Vanguard 0.19.3 or later, go to Settings, Windows Defender and choose
**Add exception**. It
excludes `C:\Program Files\Vanguard` and nothing else (only administrators can
change that folder), so later updates and scans leave Vanguard alone. Windows
asks for permission once, and uninstalling Vanguard removes the exception.

## Issues

This repository hosts the releases only.
[Bug reports and requests](https://github.com/f-de-groot/vanguard-releases/issues)
are welcome.
