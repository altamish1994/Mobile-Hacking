
Good Article on Android App Patching Process: [**https://koz.io/using-frida-on-android-without-root/**](https://koz.io/using-frida-on-android-without-root/)

Frida Gadget Documentation: [https://frida.re/docs/gadget/](https://frida.re/docs/gadget/) & Frida Releases: [https://github.com/frida/frida/releases](https://github.com/frida/frida/releases)

Process to Follow:

- Decompile Source Code: apktool d -r <target.apk>
- Download frida-gadget for your CPU Architecture
![[Pasted image 20230824034731.png]]

You need to get the frida gadget from the github page of frida in the releases
![[Pasted image 20230824035031.png]]


- Unzip File, and rename file to frida-gadget.so
- Inject Frida-gadget into Android App under: /lib/<CPUArch-For-Your-Device>
- Save As: libfrida-gadget.so
- Add reference to frida-gadget to SMALI code, in a known exported activity or otherwise accessible Activity (usually MainActivity.smali, or OnboardingActivity.smali): 
const-string v0, "frida-gadget" 
invoke-static {v0}, Ljava/lang/System;->loadLibrary(Ljava/lang/String;)V
- Recompile Application: apktool b <target.apk> -o <output_file.apk> (in this case target.apk points to the folder you decompiled in step #1)
    - Sign with your key, and zipalign the app


**Apk Signing**

sign the apk via following commands

# if you dont have a keystore already, here's how to create one
$ keytool -genkey -v -keystore custom.keystore -alias mykeyaliasname -keyalg RSA -keysize 2048 -validity 10000

# sign the APK
$ jarsigner -sigalg SHA1withRSA -digestalg SHA1 -keystore mycustom.keystore -storepass mystorepass repackaged.apk mykeyaliasname

# verify the signature you just created
$ jarsigner -verify repackaged.apk

# zipalign the APK
$ zipalign 4 repackaged.apk repackaged-final.apk


Now transfer the apk to the emulator
If you see a blank white screen on the command line enter

objection explore

android sslpinning disable (to disable ssl pinning in android)


------------

Frida CodeShare URL: [https://codeshare.frida.re/](https://codeshare.frida.re/)

To start application and disable root detection

objection explore --startup-script sslpinninguniversal.js

objection explore -s "android root disable"

-------------------
