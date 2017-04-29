# ripgrep-ubuntu
Ubuntu build script for [ripgrep](https://github.com/BurntSushi/ripgrep)

## Build dependencies
- cargo (>= 0.13.0)
- debhelper
- devscrips
- quilt

Build works on current Ubuntu 17.04

## Build steps
- install build dependencies
- download [source](https://github.com/BurntSushi/ripgrep/archive/0.5.1.tar.gz) as `ripgrep_0.5.1.orig.tar.gz`
- extract source in `ripgrep-0.5.1/.`
- download [buildscipt](https://launchpad.net/~x4121/+archive/ubuntu/ripgrep/+files/ripgrep_0.5.1-3.debian.tar.xz)
- extract buildscript in `ripgrep-0.5.1/debian/.`
- cd to `ripgrep-0.5.1/debian`
- run `debuild`

## Update build dependencies
- install [cargo-vendor](https://github.com/alexcrichton/cargo-vendor)
- cd to `ripgrep-0.5.1`
- run `cargo vendor debian/vendor`
- cd to `ripgrep-0.5.1/debian`
- run `rm vendor.tar.gz; tar czf vendor.tar.gz; rm -rf vendor`

## [Pre-build](https://launchpad.net/~x4121/+archive/ubuntu/ripgrep)
```
sudo add-apt-repository ppa:x4121/ripgrep
sudo apt-get update
sudo apt-get install ripgrep
```

Pre-build should work on Debian as well
