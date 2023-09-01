
(SSL Kill Switch Documentation: [https://github.com/nabla-c0d3/ssl-kill-switch2](https://github.com/nabla-c0d3/ssl-kill-switch2)
SSL Kill Switch for higher versions of iOS (as demonstrated in the video): [https://github.com/nabla-c0d3/ssl-kill-switch2/issues/98](https://github.com/nabla-c0d3/ssl-kill-switch2/issues/98))

Install substitute via Cydia
Install wget
Install OpenSSH

From you Macbook connect your device using

root@ip_addr
pass: alpine

wget [https://github.com/nabla-c0d3/ssl-kill-switch2/releases/download/0.14/com.nablac0d3.sslkillswitch2_0.14.deb](https://github.com/nabla-c0d3/ssl-kill-switch2/releases/download/0.14/com.nablac0d3.sslkillswitch2_0.14.deb)

iPhone:/tmp root# dpkg -i com.nablac0d3.sslkillswitch2_0.14.deb

If you get an error then fire the following command:

iPhone:/tmp root# apt --fix-broken install

iPhone:/tmp root# dpkg -i com.nablac0d3.sslkillswitch2_0.14.deb

Now respring your iDevice:

iPhone:~ root# killall -9 backboardd

and you are done.

Now open iOS settings app, scroll down and locate SSL Kill Switch 2. Open it and enable "Disable Certificate Validation"

Thats it.

--------

For iOS 15-16

Commands to Setup SSL Killswitch:

From the Jailbreak/Cydia Store install OpenSSH application.

ssh root@<IP_of_iPhone>

password is: alpine

from inside of the iPhone shell:

wget [https://github.com/nabla-c0d3/ssl-kill-switch2/releases/download/0.14/com.nablac0d3.sslkillswitch2_0.14.deb](https://github.com/nabla-c0d3/ssl-kill-switch2/releases/download/0.14/com.nablac0d3.sslkillswitch2_0.14.deb)

(if wget is not installed you can easily install it with: sudo apt-get install wget)

sudo dpkg -i <name_of_package_from_wget>

killall -HUP Springboard

  

SSL Killswitch Latest Version and Documentation: [https://github.com/nabla-c0d3/ssl-kill-switch2](https://github.com/nabla-c0d3/ssl-kill-switch2)

