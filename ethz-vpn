#!/bin/bash

connect () {
        TOKEN=$(sudo cat /secrets/ethzvpntoken.secret) 
        #place your OTP password seccret here, or choose another location. Make sure sour permissions are "chmod og-rwx ./*.secret", and user:group is root:root
        
        sudo cat /secrets/ethzvpnpass.secret | sudo openconnect -b -u kuerzel@student-net.ethz.ch -g student-net --useragent=AnyConnect --passwd-on-stdin --token-mode=totp --token-secret=sha1:base32:$TOKEN sslvpn.ethz.ch
        #Same goes here for the password secret file. If you don't want the OTP secret, you can remove the --token- arguments and Variable. You will be prompted for a password, wich is the OTP token.
        
        TOKEN="" #Clears variable for additional security.
}

disconnect () {
        sudo killall -v -SIGINT openconnect #add -i option to ask for confirmation, usefull if running multible openconnect.
}

case "$1" in 
        'connect')
                connect
        ;;
        c)
                connect
        ;;
        'disconnect')
                disconnect
                ;;
        d)
                disconnect
                ;;
        dc)
                disconnect
                ;;
        *)
                echo -e 'Usage: ethz-vpn [Option] \n [Option]: \n       connect, c:             Connect VPN \n disconnect, d, dc:      Disconnect VPN'
esac
