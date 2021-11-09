---
id: AuDqSlWn0PlsSo8JdLgrR
title: Software
desc: ''
updated: 1636428260839
created: 1636427887650
---

Some documentation for quick fixes regarding software.

## R

Compilation (and installation) of some packages requires the avialability of C++ compilers.

Windows - Rtools

MacOS - Xcode build tools

Linux - gcc

## Citrix

In most of the occasions we might need set a link to Firefox's keystore to Citrix & below command will help to set the link to Firefox's keystore to Citrix

```
sudo ln -s /usr/share/ca-certificates/mozilla/* /opt/Citrix/ICAClient/keystore/cacerts
```

## EViews

Citrix tries to mount local drives as "network" drives in the remote session. If this does not work, try adjusting the permissions setting in the relevant Citrix app.

Linking with Google Drive is possible, but reportedly very finicky.

## AWS

See [[Software.AWS]]

## MONARCH/HPC

See [[Software.HPC]]

## Git

See [[Software.Git]]