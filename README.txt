
## INSTALLATION ##

This code comes ready to use as a bash shell script.

## REQUIREMENTS ##

This tool assumes you have mdk3 installed. You will need to have
a wireless network interface, in monitor mode, named "mon0" which can be done
with the following commands:

#This will create a virtual interface called mon0.
1.) iw wlan0 interface add mon0 type monitor

#This will bring the mon0 interface up.
2.) ifconfig mon0 up

When you are done with the tool, the interface can be disabled
with the following commands:

#This will delete the virtual interface mon0.
1.) iw mon0 del

## USAGE ##

This tool assumes you have a basic knowledge on how to gather wireless information
about access points and stations including, but not limited to:

1.) BSSID (mac address)
2.) SSID (client/Access point name)
3.) Channel (Channel required for the specific mdk3 attacks that desire it)

By default, the script runs the basic configuration for each mdk3 attack. These can be 
changed at anytime by modifying the bash file auto-mdk3_v02.sh.

There is no error checks provided in this script so if you mess up you will have re-run the script.

## CONTACT ME ##

If you have any questions contact me at my email, facebook, or linkdin accounts.

Email:            yokai.linux.tutorials@outlook.com
facebook:         www.facebook.com/yokai.innorruk
Linkdin:          www.linkdin/in/nathaniel-spinks


