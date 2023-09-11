README.md` ######################################################
# Vpn Game Script Generator By BuanaNETPBun.Github.io
# Date/Time: 11/9/2023 06.59.51
# Created By: BuanaNETPBun.Github.io - fb.me/buananet.pbun
# VPN Protocol -> PPTP
######################################################
/interface pptp-client
add connect-to="x.x.x.x" disabled=no name="VPN-GAME" user="******" password="******" comment="VPN-GAME"
/ip firewall nat
add chain=srcnat out-interface="VPN-GAME" action=masquerade comment="VPN-GAME"
/ip route
add gateway="VPN-GAME" routing-mark=vpn-routing-game comment="VPN-GAME"
/ip firewall address-list
add address=192.168.0.0/16 list=LOCAL-IP
add address=172.16.0.0/12 list=LOCAL-IP
add address=10.0.0.0/8 list=LOCAL-IP
/ip firewall mangle
add action=mark-routing chain=prerouting src-address-list=LOCAL-IP dst-address-list=List-IP-Games new-routing-mark=vpn-routing-game passthrough=no comment="VPN-GAME"
/ip firewall raw

Copy ScriptCopy-Paste to Terminal.
# This Script for remove all Script from this Generator:
