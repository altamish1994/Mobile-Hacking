
pip3 install frida-tools

check installation via frida

pip install objection

To patch the apk 
objection patchapk --source appName.apk 

**If get the error  Can't Decode Resources**
objection patchapk --source appName.apk  --use-aapt2

If you want to specify the landing page e.g. app starts at Tutorial or SignUp Page instead of MainActivity

objection patchapk --source appName.apk  --use-aapt2 -t com.android.SignUpActivity

Make sure that the emulator is running ( preferably through command line)

Objection might not rebuild the application properly and might cause issues. In that case patch the application manually
