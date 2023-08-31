
**A nice tool for dealing with Split APKs:** [https://github.com/NickstaDB/patch-apk](https://github.com/NickstaDB/patch-apk)

**How to Deal with Split APKs manually:**

- Step 1: Pull all APKs and base apk off the device
- pm list packages | grep <myApp>
- pm path <myAppPath>
- (exit adb shell)

  

- Step 2: Inject base.apk with objection and sign all the split apks
- adb pull (base.apk, split_config.en.apk, etc.)
- objection patchapk -s <base.apk> --use-aapt2
- (after the application is signed and patched, you must sign all of the split config.apks)
- objection signapk split_config.en.apk, etc

  

- Step 3: Install all apks to the device using install-multiple
- After you have signed all split configs and patched base apk you use adb to install multiple APKs:
    - adb install-multiple base.objection.apk split_config.en.objection.apk, etc.