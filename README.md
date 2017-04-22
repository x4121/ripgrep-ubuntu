# ripgrep-ubuntu
Ubuntu build script for ripgrep (not working on Launchpad!)

## Build dependencies
- cargo
- debhelper
- devscrips
- quilt

## Build steps
- install build dependencies
- download [source](https://github.com/BurntSushi/ripgrep/archive/0.5.1.tar.gz) as `ripgrep_0.5.1.orig.tar.gz`
- extract source in `ripgrep-0.5.1/.`
- download [buildscipt](https://github.com/x4121/ripgrep-ubuntu/releases/download/v0.2/ripgrep_0.5.1-1.debian.tar.xz)
- extract buildscript in `ripgrep-0.5.1/debian/.`
- cd to `ripgrep-0.5.1/debian`
- run `debuild`

## Pre-build
[pre build for amd64](https://github.com/x4121/ripgrep-ubuntu/releases/download/v0.2/ripgrep_0.5.1-1_amd64.deb)
