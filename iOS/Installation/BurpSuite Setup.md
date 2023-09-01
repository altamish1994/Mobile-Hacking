
Set a port in the proxy tab and bind to all interfaces

![[Pasted image 20230824023900.png]]

Go to the wifi in your iphone and set up a manual proxy with your ip address and port

![[Pasted image 20230831104834.png]]

On your iphone browser go to http://burp:port and download the CA certificate

![[Pasted image 20230831104932.png]]

Now go to Settings-> Genreal -> profile
Install the Port Swigger Certificate

![[Pasted image 20230831105049.png]]

Now go to Settings -> General -> About -> Certificate Trust Settings and enable Port Swigger CA

![[Pasted image 20230831105216.png]]


You will be able to intercept https traffic now :)


--------

For iOS 15-16

Instructions for Burp Suite with SSL Killswitch:

In Burp Suite, enable proxy listener on All Interfaces

Set Proxy on iPhone to IP Address of your Burp Suite Box (local network)

Install the Burp Suite Certificate by navigating to http://burp:8080 in Safari

Trust the certificate in "Certificate Trust Settings" as well as "VPN and Device Management"

Ensure SSL Killswitch is enabled in Setting of Jailbroken device, and have fun intercepting!