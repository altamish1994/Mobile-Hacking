
How to start ADB with port open on host machine:

- **adb -a nodaemon server**

(if you receive an error that the port is already in use, kill the adb process - this will vary per your Operating System)

- **taskkill /f /t /im adb.exe**
- **then run: adb -a nodaemon server**

From the networked machine, or VM run the following command to connect to the emulator via the newly opened port:

**adb -H <host_machine_IP> -P 5037 shell**