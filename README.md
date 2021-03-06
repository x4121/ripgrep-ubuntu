# ripgrep-ubuntu
Ubuntu build script for [ripgrep](https://github.com/BurntSushi/ripgrep)

## Disclaimer
This repositories and the resulting packages sole purpose is to bridge the time
until ripgrep is available in official Ubuntu sources.
If you only want to install ripgrep manually, you are most likely better off to
download the provided `.deb` from the [ripgrep releases](https://github.com/BurntSushi/ripgrep/releases).

## Build dependencies
- cargo (>= 0.13.0)
- debhelper (>= 9)
- quilt
- libxslt1-dev
- asciidoc
- docbook-xsl
- xsltproc
- libxml2-utils

Build works on Ubuntu >= 16.04

## Build steps
- install build dependencies
- download [source](https://github.com/BurntSushi/ripgrep/archive/0.9.0.tar.gz) as `ripgrep_0.9.0.orig.tar.gz`
- extract source in `ripgrep-0.9.0/.`
- download [buildscipt](https://launchpad.net/~x4121/+archive/ubuntu/ripgrep/+files/ripgrep_0.9.0-3.debian.tar.xz)
- extract buildscript in `ripgrep-0.9.0/debian/.`
- cd to `ripgrep-0.9.0/debian`
- run `debuild`

## Update build dependencies
- install [cargo-vendor](https://github.com/alexcrichton/cargo-vendor)
- cd to `ripgrep-0.9.0`
- run `cargo vendor debian/vendor`
- cd to `ripgrep-0.9.0/debian`
- run `rm vendor.tar.gz; tar czf vendor.tar.gz vendor; rm -rf vendor`

## [Pre-build](https://launchpad.net/~x4121/+archive/ubuntu/ripgrep)
```
sudo add-apt-repository ppa:x4121/ripgrep
sudo apt-get update
sudo apt-get install ripgrep
```

Pre-build should work on Debian as well
