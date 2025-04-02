# ethz-vpn-connect
A customizable script for Linux to connect to the ETHZ vpn using openconnect

# Install
Install the openconnect package using your packet manager like apt or pacman

Then place the `ethz-vpn` shell script file in your `/bin/` Directory
To do this you can simply run: 
`sudo wget -O /bin/ethz-vpn https://raw.githubusercontent.com/njalooo/ethz-vpn-connect/refs/heads/main/ethz-vpn`

Restart your shell to load the new command, for example by using `exec bash`

run `ethz-vpn setup` to enter your credentials. By default they will be stored, encrypted with the password you chose, in the folder `~/.share/ethz-vpn-connect/`.
To change this location, edit the script, and change `DATADIR=~/.local/ethz-vpn-connect` to the location of your choice. 

Alternatively to providing the token secret, you can edit the Script: line 10: remove `--token-mode=totp --token-secret=sha1:base32:$TOKEN`, comment line 7,13,25,28,33. With this option you will be prompted for your OTP token each time you connect.

# Usage
ethz-vpn [Option]  
Whereby [Option]:  
- connect,c:           to Connect  
- disconnect, dc, d:   to Disconnect  
- setup:               to Setup Username and Secrets interactivly  

# Contribute
If you'd like to contribute, you could add an bash completion script (https://iridakos.com/programming/2018/03/01/bash-programmable-completion-tutorial).
