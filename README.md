<h1>Praktikum Modul 5 Jaringan Komputer</h1>
<h3>Kelompok I07</h3>

| NAME                          | NRP       |
|-------------------------------|-----------|
|Pascal Roger Junior Tauran     |5025211072 |
|Mochammad Naufal Ihza Syahzada |5025211260 |

## Tapologi

![group](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/7a0ff416-ed10-4dad-841a-a61aac985882)

## Route

| Nama Subnet |	Rute                    | Jumlah IP | Netmask |
|-------------|-------------------------|-----------|---------|
| A1	      | Fern-Revolte            | 2	    | /30     |
| A2	      | Fern-Richter	        | 2	    | /30     |
| A3	      | Himmel-SchwerMountain	| 66	    | /25     |
| A4	      | Himmel-LaubHills	| 256	    | /23     |
| A5	      | Frieren-Himmel	        | 2	    | /30     |
| A6	      | Frieren-Stark	        | 2	    | /30     |
| A7	      | Aura-Frieren	        | 2	    | /30     |
| A8	      | Aura-Heiter	        | 2	    | /30     |
| A9	      | Heiter-TurkRegion       | 1023	    | /21     |
| A10	      | Heiter-Sein-GrobeForest | 514	    | /22     |
|             | Total                   | 1871      | /20     |

## Tree

![tree](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/ee2f00aa-f391-4e87-aece-81e211ed6dd9)

## Pembagian IP

| Name |Hosts Needed|Hosts Available|Unused Hosts|Network Addresses|Slash|Mask           |Usable Range               |Broadcast   |
|:-----|:-----------|:--------------|:-----------|:----------------|:----|:--------------|:--------------------------|:-----------|
| A9   |1023        |2046           |1023        |10.62.0.0        |/21  |255.255.248.0  |10.62.0.1 - 10.62.7.254    |10.62.7.255 |
| A10  |514         |1022           |508         |10.62.8.0        |/22  |255.255.252.0  |10.62.8.1 - 10.62.11.254   |10.62.11.255|
| A4   |256         |510            |254         |10.62.12.0       |/23  |255.255.254.0  |10.62.12.1 - 10.62.13.254  |10.62.13.255|
| A3   |66          |126            |60          |10.62.14.0       |/25  |255.255.255.128|10.62.14.1 - 10.62.14.126  |10.62.14.127|
| A1   |2           |2              |0           |10.62.14.128     |/30  |255.255.255.252|10.62.14.129 - 10.62.14.130|10.62.14.131|
| A2   |2           |2              |0           |10.62.14.132     |/30  |255.255.255.252|10.62.14.133 - 10.62.14.134|10.62.14.135|
| A5   |2           |2              |0           |10.62.14.136     |/30  |255.255.255.252|10.62.14.137 - 10.62.14.138|10.62.14.139|
| A6   |2           |2              |0           |10.62.14.140     |/30  |255.255.255.252|10.62.14.141 - 10.62.14.142|10.62.14.143|
| A7   |2           |2              |0           |10.62.14.144     |/30  |255.255.255.252|10.62.14.145 - 10.62.14.146|10.62.14.147|
| A8   |2           |2              |0           |10.62.14.148     |/30  |255.255.255.252|10.62.14.149 - 10.62.14.150|10.62.14.151|

## Subnetting

- AURA
```
auto eth0
iface eth0 inet dhcp

#A8
auto eth1
iface eth1 inet static
address 10.62.14.149
netmask 255.255.255.252

#A7
auto eth2
iface eth2 inet static
address 10.62.14.145
netmask 255.255.255.252
```

- Heiter
```
#A8
auto eth0
iface eth0 inet static
address 10.62.14.150
netmask 255.255.255.252
gateway 10.62.14.149

#A9
auto eth1
iface eth1 inet static
address 10.62.0.1
netmask 255.255.248.0

#A10
auto eth2
iface eth2 inet static
address 10.62.8.1
netmask 255.255.252.0
```

- Frieren
```
#A7
auto eth0
iface eth0 inet static
address 10.62.14.146
netmask 255.255.255.252
gateway 10.62.14.145

#A6
auto eth1
iface eth1 inet static
address 10.62.14.141
netmask 255.255.255.252

#A5
auto eth2
iface eth2 inet static
address 10.62.14.137
netmask 255.255.255.252
```

- Himmel
```
#A5
auto eth0
iface eth0 inet static
address 10.62.14.138
netmask 255.255.255.252
gateway 10.62.14.137

#A4
auto eth1
iface eth1 inet static
address 10.62.12.1
netmask 255.255.254.0

#A3
auto eth2
iface eth2 inet static
address 10.62.14.1
netmask 255.255.255.128
```

- Fern
```
#A3
auto eth0
iface eth0 inet static
address 10.62.14.2
netmask 255.255.255.128
gateway 10.62.14.1

#A2
auto eth1
iface eth1 inet static
address 10.62.14.133
netmask 255.255.255.252

#A1
auto eth2
iface eth2 inet static
address 10.62.14.129
netmask 255.255.255.252
```

- Revolte
```
#A1
auto eth0
iface eth0 inet static
address 10.62.14.130
netmask 255.255.255.252
gateway 10.62.14.129
```

- Richter
```
#A2
auto eth0
iface eth0 inet static
address 10.62.14.134
netmask 255.255.255.252
gateway 10.62.14.133
```

- Stark
```
#A6
auto eth0
iface eth0 inet static
address 10.62.14.142
netmask 255.255.255.252
gateway 10.62.14.141
```

- Sein
```
#A10
auto eth0
iface eth0 inet static
address 10.62.8.2
netmask 255.255.252.0
gateway 10.62.8.1
```

- Client (SchwerMountain, LaubHills, TurkRegion, GrobeForest)
```
auto eth0
iface eth0 inet dhcp
```

## Routing

- Aura
```
#Heiter (A9, A10)
up route add -net 10.62.0.0 netmask 255.255.248.0 gw 10.62.14.150
up route add -net 10.62.8.0 netmask 255.255.252.0 gw 10.62.14.150

#Frieren (A1, A2, A3, A4, A5, A6)
up route add -net 10.62.14.128 netmask 255.255.255.252 gw 10.62.14.146
up route add -net 10.62.14.132 netmask 255.255.255.252 gw 10.62.14.146
up route add -net 10.62.14.0 netmask 255.255.255.128 gw 10.62.14.146
up route add -net 10.62.12.0 netmask 255.255.254.0 gw 10.62.14.146
up route add -net 10.62.14.136 netmask 255.255.255.252 gw 10.62.14.146
up route add -net 10.62.14.140 netmask 255.255.255.252 gw 10.62.14.146
```

- Heiter
```
#A8
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.62.14.149
```

- Frieren
```
#A1, A2, A3, A4, A5
up route add -net 10.62.14.128 netmask 255.255.255.252 gw 10.62.14.138
up route add -net 10.62.14.132 netmask 255.255.255.252 gw 10.62.14.138
up route add -net 10.62.14.0 netmask 255.255.255.128 gw 10.62.14.138
up route add -net 10.62.12.0 netmask 255.255.254.0 gw 10.62.14.138
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.62.14.145
```

- Himmel
```
#A1, A2, A5
up route add -net 10.62.14.128 netmask 255.255.255.128 gw 10.62.14.2
up route add -net 10.62.14.132 netmask 255.255.255.252 gw 10.62.14.2
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.62.14.137
```

- Fern
```
#A1
up route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.62.14.1
```

## DNS Configuration

Run this line to node `Aura` web console :
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.62.0.0/16
```

Add this line to every node in `.bashrc` : 
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
```

Add this following line on DNS Server `Richter` :
```
apt update
apt install netcat -y
apt install bind9 -y

echo '
options {
  directory "/var/cache/bind";
  forwarders {
    192.168.122.1;
  };
  allow-query {any;};
  auth-nxdomain no;
  listen-on-v6 {any;};
}' > /etc/bind/named.conf.options 

service bind9 restart 
```

Add this following line on DHCP Server `Revolte` :
```
apt update
apt install netcat -y
apt install isc-dhcp-server -y

echo 'INTERFACESv4="eth0"' > /etc/default/isc-dhcp-server

echo '
option domain-name "example.org";
option domain-name-servers ns1.example.org, ns2.example.org;

default-lease-time 600;
max-lease-time 7200;

ddns-update-style none;

# A10
subnet 10.62.8.0 netmask 255.255.252.0 {
  range 10.21.8.3 10.21.10.5;
  option routers 10.62.8.1;
  option broadcast-address 10.62.11.255; 
  option domain-name-servers 10.62.14.134;
  default-lease-time 720;
  max-lease-time 7200;
}

# A9
subnet 10.62.0.0 netmask 255.255.248.0 {
  range 10.62.0.2 10.62.4.4;
  option routers 10.62.0.1;
  option broadcast-address 10.62.7.255;
  option domain-name-servers 10.62.14.134;
  default-lease-time 720;
  max-lease-time 7200;
}

# A4
subnet 10.62.12.0 netmask 255.255.254.0 {
  range 10.62.12.2 10.62.13.1;
  option routers 10.62.12.1;
  option broadcast-address 10.62.13.255;
  option domain-name-servers 10.62.14.134;
  default-lease-time 720;
  max-lease-time 7200;
}

# A3
subnet 10.62.14.0 netmask 255.255.255.128 {
  range 10.21.14.3 10.21.14.66;
  option routers 10.21.14.1
  option broadcast-address 10.62.14.127;
  option domain-name-servers 10.62.14.134;
  default-lease-time 720;
  max-lease-time 7200;
}

# A8
subnet 10.62.14.148 netmask 255.255.255.252 {
	option routers 10.21.14.150;
}

# A7
subnet 10.62.14.144 netmask 255.255.255.252 {
	option routers 10.21.14.145;
}

# A6
subnet 10.62.14.140 netmask 255.255.255.252 {}

# A5
subnet 10.62.14.136 netmask 255.255.255.252 {
	option routers 10.21.14.137;
}

# A2
subnet 10.62.14.132 netmask 255.255.255.252 {}

# A1
subnet 10.62.14.128 netmask 255.255.255.252 {
	option routers 10.21.14.129;
}
' > /etc/dhcp/dhcpd.conf

service isc-dhcp-server start
```

Add this following line on DHCP Relay `Heiter` & `Himmel` :

Note: Uncomment `net.ipv4.ip_forward=1` di `nano /etc/sysctl.conf`

```
apt update
apt install netcat -y
apt install isc-dhcp-relay -y

echo '
SERVERS="10.62.14.130"
INTERFACES="eth0 eth1 eth2 eth3"
OPTIONS=""
' > /etc/default/isc-dhcp-relay

service isc-dhcp-relay restart
```

Web Server `Sein` , `Stark` :
```
apt update
apt install netcat -y
apt install apache2 -y
service apache2 start

echo '
Listen 80
Listen 443

<IfModule ssl_module>
        Listen 443
</IfModule>

<IfModule mod_gnutls.c>
        Listen 443
</IfModule>' > /etc/apache2/ports.conf
```

Add this following line on Client `SchwerMountain` , `LaubHills` , `TurkRegion` & `GrobeForest` :
```
apt update
apt install netcat -y
apt install lynx -y
```

# Problems

# Number 1

```
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.
```

- Code to put in node Aura `script.sh` :
```
ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```

- Result from `ping google.com` : Client, Aura, and Router
![Screenshot 2023-12-20 114850](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/9f7ba0ed-bcfa-44f2-ba18-856f8f8c596e)
![Screenshot 2023-12-20 114914](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/e7b05d9c-195f-4035-ba00-f735dd2e66f6)
![Screenshot 2023-12-20 114947](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/1df2fb28-d402-47a0-8bb0-714e6bf10476)


# Number 2
```
Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.
```

- Add this code to TurkRegion `script.sh` :

![Screenshot 2023-12-20 115448](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/23c56857-8673-476f-93a7-e3d3d3377839)

- Result:

First we run `nc -l -p 8080` on TurkRegion,

![Screenshot 2023-12-20 115339](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/20fd8622-241d-4cf8-9360-52d478b7c8fb)

Then we run `nc 10.62.0.4 8080` on other client, for instance GrobeForest 

![Screenshot 2023-12-20 115347](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/ec33e598-1e20-46df-9e82-db5b2a2a4952)
