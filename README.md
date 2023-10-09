# sep/08/2023 10:29:49 by RouterOS 6.49.8
# software id = IKZF-7MUV
#
# model = RB450Gx4
# serial number = HD5085X8RFP
/interface ethernet
set [ find default-name=ether1 ] comment=Main name=ether1-INDOCYBER
set [ find default-name=ether2 ] comment=Backup disabled=yes name=\
    ether2-COMNET
set [ find default-name=ether3 ] comment=Backup name=ether3-BIZNET
set [ find default-name=ether4 ] comment=Client
set [ find default-name=ether5 ] comment=Backup name=ether5-COMNET
/interface pptp-client
add comment="Dial Palembang" connect-to=103.31.133.189 disabled=no name=\
    pptp-out1 password=indocyberbekasi user=indocyberbekasi
/interface list
add name=WAN
add name=LAN
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip firewall layer7-protocol
add name=Youtube regexp="^.+(youtube.com|googlevideo.com|ytimg.com|youtu.be|yt\
    3.ggpht.com|youtubei.googleapis.com).*\$"
/ip pool
add name=dhcp_pool0 ranges=192.11.0.10-192.11.0.254
add name=dhcp_pool1 ranges=192.11.0.10-192.11.0.254
add name=dhcp_pool2 ranges=192.12.0.12-192.12.0.254
/ip dhcp-server
add address-pool=dhcp_pool1 disabled=no interface=ether4 name=dhcp1
/queue simple
add name=TOTAL_SPEED target=192.11.0.0/24
add name="0.Trafic Internet Rumah" parent=TOTAL_SPEED target=192.11.0.0/24
add max-limit=10M/10M name=Rb931 parent="0.Trafic Internet Rumah" target=\
    192.11.0.12/32
add max-limit=30M/30M name="Neng Mulyanih" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.72/32
add max-limit=20M/20M name="Tante Lucki" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.31/32
add max-limit=30M/30M name="Sita Nurul" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.80/32
add max-limit=7M/7M name="Saudaranya Arema" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.101/32
add max-limit=10M/10M name="Warung Mena" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.11/32
add max-limit=7M/7M name="Teh Rena" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.35/32
add max-limit=5M/5M name=Nita parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.63/32
add max-limit=5M/5M name=Fathan parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.48/32
add max-limit=5M/5M name="Imron Kober" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.76/32
add max-limit=2M/2M name=Rayyan parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.77/32
add max-limit=4M/4M name="Dina Yohana" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.38/32
add max-limit=2M/2M name="Bu Ferdi" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.19/32
add max-limit=2M/2M name="Mang Engkos 2" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.32/32
add max-limit=2M/2M name="Om Puput" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.10/32
add max-limit=2M/2M name=Piyan parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.28/32
add max-limit=2M/2M name="Sunarya/Pak Narya" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.17/32
add max-limit=2M/2M name="Rustandi Belakang Garda" parent=\
    "0.Trafic Internet Rumah" queue=default/default target=192.11.0.84/32
add disabled=yes max-limit=45M/45M name=Epon parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.222/32
add max-limit=2M/2M name=Jamilah parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.68/32
add max-limit=2M/2M name=Mala parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.42/32
add max-limit=2M/2M name=Anggi/Karni parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.13/32
add max-limit=2M/2M name="Bu Neneng/Pak Hj Wahyu" parent=\
    "0.Trafic Internet Rumah" queue=default/default target=192.11.0.51/32
add max-limit=2M/2M name=Supriyatin parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.53/32
add max-limit=2M/2M name="Teh Neneng Kontrakan 2 Samping Alika" parent=\
    "0.Trafic Internet Rumah" queue=default/default target=192.11.0.74/32
add max-limit=2M/2M name="Bu Teti" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.14/32
add max-limit=2M/2M name="Ibu Firda" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.54/32
add max-limit=2M/2M name="Dede Permana" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.47/32
add max-limit=2M/2M name="Didu Mena" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.52/32
add max-limit=2M/2M name=Yaya parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.20/32
add max-limit=2M/2M name="Warung Bubble Khanza" parent=\
    "0.Trafic Internet Rumah" queue=default/default target=192.11.0.55/32
add max-limit=3M/3M name="Warung Alika" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.15/32
add max-limit=2M/2M name="Wahyu Sodara Mena" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.34/32
add max-limit=2M/2M name="Wa Lili" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.18/32
add max-limit=2M/2M name="Teh Nunung" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.16/32
add max-limit=2M/2M name="Teh Nindi" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.61/32
add max-limit=2M/2M name=Dimas parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.41/32
add max-limit=4M/4M name=Fallah/Nurdin parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.37/32
add max-limit=5M/5M name="Mang Engkos 1" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.21/32
add max-limit=5M/5M name="Pak RW" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.100/32
add max-limit=5M/5M name="Saudara Teh Dewi" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.71/32
add max-limit=5M/5M name=Sumi parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.81/32
add max-limit=5M/5M name=Tanamal parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.62/32
add max-limit=5M/5M name="Teh Ai" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.64/32
add max-limit=5M/5M name="Teh Darti" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.60/32
add max-limit=5M/5M name="Teh Dewi" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.67/32
add max-limit=5M/5M name="Teh Dyen" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.33/32
add max-limit=5M/5M name=Wiyatni parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.24/32
add max-limit=5M/5M name="Kontrakan Belakang Garda" parent=\
    "0.Trafic Internet Rumah" queue=default/default target=192.11.0.73/32
add max-limit=5M/5M name="Mamah Yogi" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.29/32
add max-limit=5M/5M name="Lilis Arema" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.82/32
add max-limit=5M/5M name="Siti Aisyah Kober" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.89/32
add max-limit=5M/5M name=Nining parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.79/32
add max-limit=5M/5M name=Nona parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.78/32
add max-limit=5M/5M name="Ibu Helmi" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.30/32
add max-limit=2M/2M name=Candra parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.56/32
add max-limit=5M/5M name="David JNE" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.65/32
add max-limit=5M/5M name=Aji parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.25/32
add max-limit=5M/5M name="Bu Tini" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.44/32
add max-limit=10M/10M name="Sari Rahayu" parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.75/32
add max-limit=10M/10M name=Nana/Sopian parent="0.Trafic Internet Rumah" \
    queue=default/default target=192.11.0.22/32
add max-limit=10M/10M name="Ibu Ade" parent="0.Trafic Internet Rumah" queue=\
    default/default target=192.11.0.26/32
/system logging action
set 0 memory-lines=1
set 1 disk-lines-per-file=100
/ip firewall connection tracking
set enabled=yes generic-timeout=5m icmp-timeout=5s tcp-close-timeout=1s \
    tcp-close-wait-timeout=5s tcp-fin-wait-timeout=5s tcp-last-ack-timeout=1s \
    tcp-syn-received-timeout=1s tcp-syn-sent-timeout=1s \
    tcp-time-wait-timeout=1s udp-stream-timeout=1m udp-timeout=1s
/interface l2tp-server server
set enabled=yes
/interface list member
add interface=ether1-INDOCYBER list=WAN
add interface=ether2-COMNET list=WAN
add interface=ether3-BIZNET list=WAN
add list=LAN
/interface pptp-server server
set enabled=yes
/ip address
add address=103.31.132.90/29 interface=ether1-INDOCYBER network=103.31.132.88
add address=192.168.18.36/24 interface=ether3-BIZNET network=192.168.18.0
add address=192.11.0.1/24 interface=ether4 network=192.11.0.0
add address=192.12.0.1/24 interface=ether5-COMNET network=192.12.0.0
add address=192.168.100.36/24 interface=ether5-COMNET network=192.168.100.0
/ip dhcp-server network
add address=192.11.0.0/24 gateway=192.11.0.1
add address=192.12.0.0/24 gateway=192.12.0.1
/ip dns
set allow-remote-requests=yes servers="8.8.8.8,8.8.4.4,1.1.1.1,103.31.132.132,\
    103.31.134.134,192.168.18.1,192.168.100.1"
/ip firewall address-list
add address=103.31.132.88/29 list=Lokal
add address=192.168.100.0/24 list=Lokal
add address=192.168.18.0/24 list=Lokal
add address=192.11.0.0/24 list=Lokal
/ip firewall filter
add action=drop chain=forward comment=DIMAS disabled=yes in-interface-list=\
    all src-address=192.11.0.41
/ip firewall mangle
add action=accept chain=prerouting dst-address-list=Lokal
add action=accept chain=output dst-address-list=Lokal
add action=mark-connection chain=prerouting comment=In-Public in-interface=\
    ether1-INDOCYBER new-connection-mark=ISP1 passthrough=yes
add action=mark-connection chain=prerouting in-interface=ether3-BIZNET \
    new-connection-mark=ISP3 passthrough=yes
add action=mark-connection chain=prerouting in-interface=ether5-COMNET \
    new-connection-mark=ISP2 passthrough=yes
add action=mark-routing chain=output comment=Out-ISP connection-mark=ISP1 \
    new-routing-mark=Route1 passthrough=yes
add action=mark-routing chain=output connection-mark=ISP2 new-routing-mark=\
    Route2 passthrough=yes
add action=mark-routing chain=output connection-mark=ISP3 new-routing-mark=\
    Route3 passthrough=yes
add action=mark-routing chain=prerouting comment=SpeedTest dst-address-list=\
    SpeedTest new-routing-mark=Route1 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment=Medsos dst-address-list=\
    Medsos new-routing-mark=Route2 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment=Game dst-address-list=\
    Game-List new-routing-mark=Route2 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment=Youtube dst-address-list=\
    Youtube new-routing-mark=Route2 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment=Tiktok dst-address-list=\
    Tiktok new-routing-mark=Route3 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment=Wa dst-address-list=Wa \
    new-routing-mark=Route3 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment=Market dst-address-list=\
    Market-List new-routing-mark=Route3 passthrough=no src-address-list=Lokal
add action=mark-routing chain=prerouting comment="Port Wa" dst-address-list=\
    Wa-List new-routing-mark=Route3 passthrough=no src-address-list=Lokal
add action=add-dst-to-address-list address-list=YT address-list-timeout=\
    none-dynamic chain=prerouting comment=Layer7YT disabled=yes \
    dst-address-list=!Lokal layer7-protocol=Youtube src-address-list=Lokal
add action=mark-connection chain=prerouting disabled=yes dst-address-list=YT \
    new-connection-mark=C-YT passthrough=yes src-address-list=Lokal
add action=mark-connection chain=prerouting disabled=yes dst-address-list=YT \
    dst-port=443 new-connection-mark=C-YT passthrough=yes protocol=udp \
    src-address-list=Lokal
add action=mark-packet chain=prerouting connection-mark=ISP3 disabled=yes \
    dst-address-list=!Lokal new-packet-mark=P-ISP3 passthrough=yes \
    src-address-list=Lokal
add action=mark-routing chain=prerouting disabled=yes in-interface=*6 \
    new-routing-mark=Route2 packet-mark=P-ISP3 passthrough=no
/ip firewall nat
add action=masquerade chain=srcnat comment=INDOCYBER out-interface=\
    ether1-INDOCYBER
add action=masquerade chain=srcnat comment=COMNET out-interface=ether5-COMNET
add action=masquerade chain=srcnat comment=BIZNET out-interface=ether3-BIZNET
add action=masquerade chain=srcnat comment=VPN
add action=dst-nat chain=dstnat comment=Client1 dst-address=103.31.132.90 \
    dst-port=2001 protocol=tcp to-addresses=9.9.9.9 to-ports=2001
add action=dst-nat chain=dstnat comment=HIOSO dst-address=103.31.132.90 \
    dst-port=2023 protocol=tcp to-addresses=9.9.9.9 to-ports=2023
add action=dst-nat chain=dstnat comment="Mikrotik RB750Gr3 Rumah Pak Taufik" \
    dst-address=103.31.132.90 dst-port=1001 protocol=tcp to-addresses=9.9.9.9 \
    to-ports=8191
add action=dst-nat chain=dstnat comment="Mikrotik RB951 Rumah Nanda" \
    dst-address=103.31.132.90 dst-port=1003 protocol=tcp to-addresses=\
    192.168.30.1 to-ports=8291
add action=dst-nat chain=dstnat comment=Mikrotik dst-address=103.31.132.90 \
    dst-port=1002 protocol=tcp to-addresses=192.168.2.1 to-ports=8291
/ip firewall raw
add action=accept chain=prerouting comment=DDoS disabled=yes limit=\
    400,5:packet protocol=tcp tcp-flags=syn
add action=drop chain=prerouting disabled=yes protocol=tcp tcp-flags=syn
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting comment=SpeedTest content=\
    speedtest.net dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedtest- \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedest. \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedof.me \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=openspeedtest.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedtest.cbn.id \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedcheck.org \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedtestcustom.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=speedtestcustom. \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=fast.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=nflxvideo.net \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=SpeedTest \
    address-list-timeout=1h chain=prerouting content=ooklaserver.net \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting comment=Medsos content=.facebook.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=.facebook.net dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=.fbcdn.net dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=.instagram.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=.cdninstagram.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=.twimg.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=twitter.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Medsos address-list-timeout=\
    1h chain=prerouting content=t.co dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.twitter.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.ttwstatic.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting comment=PortGame \
    dst-address-list=!Lokal dst-port=\
    5000-5221,5224-5227,5229-5241,5243-5287,5289-5509,5517,5520-5529 \
    protocol=tcp src-address-list=Lokal
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port=5551-5559,5601-5700,8443,9000-9010,9443,10003,30000-30300 \
    protocol=tcp src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port="2702,3702,4001-4009,5000-5221,5224-5241,5243-5287,5289-5509,5517\
    ,5520-5529" protocol=udp src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port=\
    5551-5559,5601-5700,8001,8130,8443,9000-9010,9120,9992,10003,30000-30300 \
    protocol=udp src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port=\
    6006,6008,6674,7006-7008,7889,8001-8012,9006,9137,10000-10012,11000-11019 \
    protocol=tcp src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port=6006,6008,6674,7006-7008,7889,8008,8001-8012,8130,8443,9008,9120 \
    protocol=udp src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port=12006,12008,13006,15006,20561,39003,39006,39698,39779,39800 \
    protocol=tcp src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Game-List \
    address-list-timeout=4h chain=prerouting dst-address-list=!Lokal \
    dst-port=10000-10015,10100,11000-11019,12008,13008 protocol=udp \
    src-address-list=Lokal src-port=""
add action=add-dst-to-address-list address-list=Youtube address-list-timeout=\
    1h chain=prerouting comment=Youtube content=.youtube.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Youtube address-list-timeout=\
    1h chain=prerouting content=.ytimg.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Youtube address-list-timeout=\
    1h chain=prerouting content=youtu.be dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Youtube address-list-timeout=\
    1h chain=prerouting content=.googlevideo.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Youtube address-list-timeout=\
    1h chain=prerouting content=youtubei.googleapis.com dst-address-list=\
    !Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Youtube address-list-timeout=\
    1h chain=prerouting content=yt3.ggpht.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting comment=Tiktok content=.tiktokcdn-us.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.tiktokcdn.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.tiktokcdn-in.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.tiktokv.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.life360.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.amemv.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.tiktok.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.myqcloud.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=bytedance.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.ibytedtos.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.ibyteimg.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Tiktok address-list-timeout=\
    1h chain=prerouting content=.ttlivecdn.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Wa address-list-timeout=1h \
    chain=prerouting comment=Wa content=.whatsapp.com dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Wa address-list-timeout=1h \
    chain=prerouting content=.whatsapp.net dst-address-list=!Lokal \
    src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting comment=Market content=\
    shopee.co.id dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.shopee.co.id \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.shopee.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.lazada.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.slatic.net \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.shopee.sg \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.lazada.co.id \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.lazada. \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.aliyuncs.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.alibaba-inc.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=bukalapak.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.tokopedia.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.tokopedia.net \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.bukalapak.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=.shopeemobile.com \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Market-List \
    address-list-timeout=1h chain=prerouting content=shopee.io \
    dst-address-list=!Lokal src-address-list=Lokal
add action=add-dst-to-address-list address-list=Wa-List address-list-timeout=\
    1h chain=prerouting comment=Port-Wa dst-address-list=!Lokal dst-port=\
    3478,4244,5222,5223,5228,5288,5242,5349,34784,45395,50318,59234 protocol=\
    udp src-address-list=Lokal
add action=add-dst-to-address-list address-list=Wa-List address-list-timeout=\
    1h chain=prerouting dst-address-list=!Lokal dst-port=\
    3478,4244,5222,5223,5228,5288,5242,5349,34784,45395,50318,59234 protocol=\
    tcp src-address-list=Lokal
add action=add-dst-to-address-list address-list=Browsing \
    address-list-timeout=4h chain=prerouting comment=Browsing disabled=yes \
    dst-address-list=!Lokal dst-port=81,8000-8081,21,22,23,81,88,5050,843,182 \
    protocol=tcp src-address-list=Lokal
add action=add-dst-to-address-list address-list=Browsing \
    address-list-timeout=4h chain=prerouting disabled=yes dst-address-list=\
    !Lokal dst-port=81,8000-8081,21,22,23,81,88,5050,843,182 protocol=udp \
    src-address-list=Lokal
/ip route
add check-gateway=ping comment=Rec1 distance=1 gateway=8.8.8.8 routing-mark=\
    Route1 target-scope=30
add comment="ISP1 ke ISP 2" distance=2 gateway=192.168.100.1 routing-mark=\
    Route1
add comment="ISP1 ke ISP3" distance=3 gateway=192.168.18.1 routing-mark=\
    Route1
add check-gateway=ping comment=Rec2 distance=1 gateway=8.8.4.4 routing-mark=\
    Route2 target-scope=30
add comment="ISP2 ke ISP1" distance=2 gateway=103.31.132.89 routing-mark=\
    Route2
add comment="ISP2 ke ISP3" distance=3 gateway=192.168.18.1 routing-mark=\
    Route2
add check-gateway=ping comment=Rec3 distance=1 gateway=1.1.1.1 routing-mark=\
    Route3 target-scope=30
add comment="ISP3 ke ISP1" distance=2 gateway=103.31.132.89 routing-mark=\
    Route3
add comment="ISP3 ke ISP2" distance=3 gateway=192.168.100.1 routing-mark=\
    Route3
add check-gateway=ping comment="Koneksi Utama" distance=1 gateway=8.8.8.8 \
    target-scope=30
add comment="Koneksi Kedua" distance=2 gateway=192.168.100.1
add comment="Koneksi Ketiga" distance=3 gateway=192.168.18.1
add comment=DNS3 distance=1 dst-address=1.1.1.1/32 gateway=192.168.18.1
add comment=DNS2 distance=1 dst-address=8.8.4.4/32 gateway=192.168.100.1
add comment=DNS1 distance=1 dst-address=8.8.8.8/32 gateway=103.31.132.89
add comment="Vpn Nassa" distance=1 dst-address=10.101.104.0/24 gateway=\
    192.168.30.1
add comment="Vpn Raudah" distance=1 dst-address=10.101.105.0/24 gateway=\
    *F13C43
add comment=RAUDAH disabled=yes distance=1 dst-address=10.101.105.0/28 \
    gateway=*F0BA31
add comment=Rotte distance=1 dst-address=10.101.106.0/24 gateway=pptp-out1
add comment="VPN Daru-Daru" distance=1 dst-address=10.101.108.0/24 gateway=\
    192.168.11.2
add comment=Rawalumbu distance=1 dst-address=192.168.31.0/24 gateway=*F0A809
add comment="VPN Nanda" distance=1 dst-address=192.168.88.0/24 gateway=\
    *F07786
/ip service
set ftp disabled=yes
set www disabled=yes
set ssh disabled=yes
set winbox port=8191
/ppp secret
add local-address=192.168.1.2 name=nanda123 password=nanda123 profile=\
    default-encryption remote-address=192.168.2.1
add local-address=192.168.20.1 name=nassa123 password=nassa123 profile=\
    default-encryption remote-address=192.168.30.1
add local-address=192.168.101.1 name=nassavalley1 password=nassavalley1 \
    profile=default-encryption remote-address=192.168.101.2
add local-address=1.1.1.1 name=oasependopo password=oasependopo profile=\
    default-encryption remote-address=1.1.1.2
add local-address=192.168.77.1 name=raudah1 password=raudah1 profile=\
    default-encryption remote-address=192.168.77.2
add local-address=192.168.44.1 name=rotte13 password=rotte13 profile=\
    default-encryption remote-address=192.168.44.2
add local-address=7.7.7.1 name=rotte14 password=rotte14 profile=\
    default-encryption remote-address=7.7.7.2
add local-address=192.168.10.1 name=cobagratis password=cobagratis profile=\
    default-encryption remote-address=192.168.10.2
add local-address=192.168.102.1 name=rotte45 password=rotte45 profile=\
    default-encryption remote-address=192.168.102.2
add local-address=192.168.12.2 name=nandarumah password=nandarumah profile=\
    default-encryption remote-address=192.168.12.1
add local-address=192.168.11.1 name=rotte75 password=rotte75 profile=\
    default-encryption remote-address=192.168.11.2
add local-address=9.9.9.8 name=rb7502 password=rb7502 profile=\
    default-encryption remote-address=9.9.9.9
add local-address=192.168.103.1 name=rotte10 password=rotte10 profile=\
    default-encryption remote-address=192.168.103.2
add local-address=192.168.13.1 name=nurulfajri password=nurulfajri profile=\
    default-encryption remote-address=192.168.13.2
add local-address=192.168.14.1 name=happybear password=happybear profile=\
    default-encryption remote-address=192.168.14.2
add local-address=192.168.15.1 name=rawalumbu password=rawalumbu profile=\
    default-encryption remote-address=192.168.15.2
add local-address=4.4.4.4 name=nandarumah2 password=nandarumah2 profile=\
    default-encryption remote-address=5.5.5.5
/system clock
set time-zone-name=Asia/Jakarta
/system identity
set name=RouterOS
/system scheduler
add interval=2d name=Reboot-Otomatis on-event="/system reboot" policy=\
    ftp,reboot,read,write,policy,test,password,sniff,sensitive,romon \
    start-date=apr/11/2023 start-time=03:50:00
/tool netwatch
add down-script=":local CHID \"5994955961\";\r\
    \n:local BotID \"6063755341:AAG8dqkis45GGj2feYzDvsrKKcHrxXBCSu8\";\r\
    \n:local HostStatus \"Down\";\r\
    \n\r\
    \n:local message \"Ping \$host \$HostStatus\";\r\
    \n\r\
    \n/tool fetch url=\"https://api.telegram.org/bot\$BotID/sendmessage\\\?cha\
    t_id=\$CHID&text=\$message\";" host=192.168.12.2 interval=5s up-script=":l\
    ocal CHID \"5994955961\";\r\
    \n:local BotID \"6063755341:AAG8dqkis45GGj2feYzDvsrKKcHrxXBCSu8\";\r\
    \n:local HostStatus \"Up\";\r\
    \n\r\
    \n:local message \"Ping \$host \$HostStatus\";\r\
    \n\r\
    \n/tool fetch url=\"https://api.telegram.org/bot\$BotID/sendmessage\\\?cha\
    t_id=\$CHID&text=\$message\";"
