# Open SSTP Client for Android <img src="https://github.com/kittoku/Open-SSTP-Client/raw/main/images/icon.png" height="40">
This is an open-sourced Secure Socket Tunneling Protocol (MS-SSTP) client for Android, developed for accessing to 
[VPN Azure Cloud](https://www.vpnazure.net/) (or [SoftEther VPN Server](https://www.softether.org/)). 
So no test with other servers is done. Its behavior may be still unstable.

## Installation
* You need to [allow unknown sources](https://developer.android.com/studio/publish/#unknown-sources) 
* Download .apk file [here](https://github.com/kittoku/Open-SSTP-Client/releases/download/v1.1.0/osc-1.1.0.apk) and install it

## Usage
Fill `Host`, `Username` and `Password` fields and turn the switch on. If a key icon gets to show on 
the right side of the status bar, establishing a VPN connection has been succeeded. To disconnect 
the connection, turn the switch off in the home tab or push `DISCONNECT` in the notification.  
<br>
<img src="https://github.com/kittoku/Open-SSTP-Client/raw/main/images/example_home.jpg" width=25%>
<img src="https://github.com/kittoku/Open-SSTP-Client/raw/main/images/example_setting.jpg" width=25%>

## Setting tab
You can configure some settings in the setting tab. You need to **push** SAVE button to apply the settings 
**before** connecting. Some settings to be noted are written below:

### Enabled Network Control Protocols
You can choose what network protocol PPP layer tries enabling. Remember, IPv6 option just gives the device 
a link local address, never guarantees that you can communicate perfectly with IPv6 protocol.

### Trusted Certificates
If you choose a certain directory, the client uses ONLY certificates in the directory, but the default 
certificate store. I made this option for debugging. 

## Notice
* `Host` field can also contain IP address, but cannot include a port number. You can configure it in
the setting tab.

* Your device needs to install a self-signed certificate and
 enable `Disable Hostname Verifier` option to access to a server using it
 
* A server must enable DHCP
 
* Only **PAP** and **MS-CHAPv2** authentication protocols can be enabled. No EAP. 
 
## Debugging
It is almost impossible that I can debug a problem caused in any environments but my own. In a networking
app, there are many possible reasons to cause the problem and I cannot identify the real one unless the 
problem can be reproduced in my environment.

So it is strongly encouraged that you should debug by yourself. With `Decryptable Mode`, this client tries 
to use `TLS_RSA_WITH_AES_128_CBC_SHA` or `TLS_RSA_WITH_AES_256_CBC_SHA` as a cipher suite so that you 
can decrypt and investigate packets with software like WireShark. I think there can be a similar app for 
Android. In my experience, Specifying TLS version explicitly is necessary to decrypt. Don't forget the
great software, Android Studio and its emulator (v^ー°)

I don't have Windows Server OS. So I don't officially support accessing to it, but there is a
 successful case. See [this issue](https://github.com/kittoku/Open-SSTP-Client/issues/8#issuecomment-590241322).

## License
Licensed under MIT. Be sure you use this software at your own risk. 
