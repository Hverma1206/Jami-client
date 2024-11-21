# Clarion Android

The Clarion client for Android

| App | CI
| :-: | :-: |
| [![Download on the Play Store](https://img.shields.io/badge/download-play%20store-blue.svg)](https://play.google.com/store/apps/details?id=com.clarion.app) [![Download on F-Droid](https://img.shields.io/badge/download-fdroid-blue.svg)](https://f-droid.org/repository/browse/?fdid=com.clarion.app) | [![Build Status](https://jenkins.clarion.net/buildStatus/icon?job=client-android)](https://jenkins.clarion.net/job/client-android/)

## Environment

### Submodule

Download the project including the daemon submodule with:

```sh
git clone --recursive https://review.clarion.net/clarion-client-android
```

Or to download the daemon submodule from the existing project directory:

```sh
git submodule update --init --recursive
```

### Dependencies

Make sure to have autotools, autopoint, swig, yasm, m4, ninja-build and cmake available on your system.

> [!WARNING]
>
> Clarion needs at least swig 4.2 to work. Else it will raise errors at compilation.
> See if the package is available with this version from your package manager, else you will need to install it [from sources](https://github.com/swig/swig).

## Build instructions

### With Android Studio:

* Add 'clarion-android' in Android Studio
* Click on build
* Enjoy!

### With the command line:

```sh
cd clarion-client-android/clarion-android
./gradlew assembleDebug
```

### Troubleshoot

Clarion Android doesn't use the system's `pkg-config`; it builds its own version with custom parameters to support cross-compilation. However, after cleaning the project, `pkg-config` may not be rebuilt, which could result in falling back to the system's version, leading to errors when trying to locate shared libraries.

```sh
cd clarion-client-android/daemon/extras/tools
./bootstrap && make
```

## Update translations

Update translations using the Transifex client (tx) :
```sh
./update-translations.sh
```

## Generate new release commit

Generate a new release commit updating the version code and version string:
```sh
./update_version.py --commit
```

## Report issues

Report issues on Gitlab:
https://git.clarion.net/savoirfairelinux/clarion-client-android

