# Cordova app troubleshooting guide

LICENSE: CC0 (public domain) ref: http://creativecommons.org/publicdomain/zero/1.0/

Inspiration:
- [jessemonroy650 / top-phonegap-mistakes](https://github.com/jessemonroy650/top-phonegap-mistakes)
- [litehelpers / Cordova-sqlite-storage / issues](https://github.com/litehelpers/Cordova-sqlite-storage/issues)

## Purpose

TBD

## General

- Check [brodybits / Cordova-quick-start-checklist](https://github.com/brodybits/Cordova-quick-start-checklist)
- In case of problems start with a fresh, clean project, follow [brodybits / Cordova-quick-start-checklist](https://github.com/brodybits/Cordova-quick-start-checklist), and try one thing at a time to isolate and pinpoint the exact issue and cause

## General pitfalls

- Whitelist (see below)
- Attempting to use any Cordova or Cordova plugin functionality before receiving `deviceready` event
- In case of ngCordova/Ionic, possible controller/factory/service/??? callbacks before `deviceready` event
- TBD ...

## Whitelist/security pitfalls

- intent whitelist: blocked intent such as external URL intent *may* cause certain Cordova plugin(s) to misbehave (see [litehelpers / Cordova-sqlite-storage#396](https://github.com/litehelpers/Cordova-sqlite-storage/issues/396))
- navigation & network request whitelist
- Content Security Policy in index file
- In case of multi-page apps, each navigation HTML page *MUST* have the correct Content Security Policy config

## ngCordova/Ionic-specific pitfalls

- possible controller/factory/service/??? callbacks before `deviceready` event
- as discussed in [litehelpers / Cordova-sqlite-storage#355](https://github.com/litehelpers/Cordova-sqlite-storage/issues/355) and https://forum.ionicframework.com/t/keyboard-error-and-cordova-plugins/39851, it may be necessary to add ionic-plugin-keyboard for certain plugins such as [litehelpers / Cordova-sqlite-storage](https://github.com/litehelpers/Cordova-sqlite-storage) to work

## SQLite-specific pitfall(s)

TBD (already documented in [litehelpers / Cordova-sqlite-storage](https://github.com/litehelpers/Cordova-sqlite-storage))
