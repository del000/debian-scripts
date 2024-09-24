# Wireguard

Sometimes, wireguard clients may loose connexion to their server and have difficulty to connect back.

Wireguard watchdog script is in charge of checking latest wireguard handshake.
Usually, wireguard issues an handshake every 2 minutes maximum.
If handshake has not been issued for more than 4 minutes, it means that connexion is having trouble.
Client wireguard service needs to be restarted.

To install this wireguard watchdog client, run following commands as root :
    wget -O /usr/local/bin/wireguard-watchdog https://raw.githubusercontent.com/NicolasBernaerts/debian-scripts/master/wireguard/wireguard-watchdog
    chmod +x /usr/local/bin/wireguard-watchdog

Then add this line to root crontab :
    * * * * * /usr/local/bin/wireguard-watchdog