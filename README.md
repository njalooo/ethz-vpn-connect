# ethz-vpn-connect
A customizable script for Linux to connect to the ETHZ vpn using openconnect

# Install
Install the openconnect package using your packet manager like apt or pacman

Then place the `ethz-vpn` shell script file in your `/bin/` Directory

Put your password in the file `/secrets/ethzvpnpass.secret`

Put your OTP Token (2FA) in the file `/secrets/ethzvpntoken.secret`

Alternatively choose any location and edit the shell script.

Make sure the filepermissions for the secret files are `chmod og-rwx /secrets/*.secret`, and that the files are owned by `chown root:root /secrets/*.secret`

Edit the `ethz-vpn` shell script, and change your username on line 7 to match your ETH-Kürzel

Make sure the filepermissions for the `ethz-vpn` shell script are `chmod a+x /bin/ethz-vpn`, and that the files are owned by `chown root:root /bin/ethz-vpn`

Restart your shell to load the new command using `exec bash`

# Usage
ethz-vpn [Option]
  Whereby [Option]:
    connect,c           to Connect
    disconnect, dc, d   to Disconnect

# Contribute
If you'd like to contribute, you could add an bash completion script (https://iridakos.com/programming/2018/03/01/bash-programmable-completion-tutorial).
