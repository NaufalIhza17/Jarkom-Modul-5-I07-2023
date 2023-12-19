<h1>Praktikum Modul 5 Jaringan Komputer</h1>
<h3>Kelompok I07</h3>

| NAME                          | NRP       |
|-------------------------------|-----------|
|Pascal Roger Junior Tauran     |5025211072 |
|Mochammad Naufal Ihza Syahzada |5025211260 |

## Tapologi

![group](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/7a0ff416-ed10-4dad-841a-a61aac985882)

## Route

| Nama Subnet |	Rute                    |	Jumlah IP |	Netmask |
|-------------|-------------------------|-----------|---------|
| A1	        | Fern-Revolte            |	2	        | /30     |
| A2	        | Fern-Richter	          | 2	        | /30     |
| A3	        | Himmel-SchwerMountain	  | 66	      | /25     |
| A4	        | Himmel-LaubHills	      | 256	      | /23     |
| A5	        | Frieren-Himmel	        | 2	        | /30     |
| A6	        | Frieren-Stark	          | 2	        | /30     |
| A7	        | Aura-Frieren	          | 2	        | /30     |
| A8	        | Aura-Heiter	            | 2	        | /30     |
| A9	        | Heiter-TurkRegion       | 1023	    | /21     |
| A10	        | Heiter-Sein-GrobeForest |	514	      | /22     |
|             | Total                   | 1871      | /20     |

## Tree

![tree](https://github.com/NaufalIhza17/Jarkom-Modul-5-I07-2023/assets/89951546/ee2f00aa-f391-4e87-aece-81e211ed6dd9)

## Pembagian IP

|Name |Hosts Needed|Hosts Available|Unused Hosts|Network Addresses|Slash|Mask           |Usable Range               |Broadcast   |
|:----|:-----------|:--------------|:-----------|:----------------|:----|:--------------|:--------------------------|:-----------|
|A9   |1023        |2046           |1023        |10.62.0.0        |/21  |255.255.248.0  |10.62.0.1 - 10.62.7.254    |10.62.7.255 |
|A10  |514         |1022           |508         |10.62.8.0        |/22  |255.255.252.0  |10.62.8.1 - 10.62.11.254   |10.62.11.255|
|A4   |256         |510            |254         |10.62.12.0       |/23  |255.255.254.0  |10.62.12.1 - 10.62.13.254  |10.62.13.255|
|A3   |66          |126            |60          |10.62.14.0       |/25  |255.255.255.128|10.62.14.1 - 10.62.14.126  |10.62.14.127|
|A1   |2           |2              |0           |10.62.14.128     |/30  |255.255.255.252|10.62.14.129 - 10.62.14.130|10.62.14.131|
|A2   |2           |2              |0           |10.62.14.132     |/30  |255.255.255.252|10.62.14.133 - 10.62.14.134|10.62.14.135|
|A5   |2           |2              |0           |10.62.14.136     |/30  |255.255.255.252|10.62.14.137 - 10.62.14.138|10.62.14.139|
|A6   |2           |2              |0           |10.62.14.140     |/30  |255.255.255.252|10.62.14.141 - 10.62.14.142|10.62.14.143|
|A7   |2           |2              |0           |10.62.14.144     |/30  |255.255.255.252|10.62.14.145 - 10.62.14.146|10.62.14.147|
|A8   |2           |2              |0           |10.62.14.148     |/30  |255.255.255.252|10.62.14.149 - 10.62.14.150|10.62.14.151|

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
auto lo
iface lo inet loopback

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
auto lo
iface lo inet loopback

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
auto lo
iface lo inet loopback

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
auto lo
iface lo inet loopback

#A3
auto eth0
iface eth0 inet static
address 10.62.14.126
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
address 10.62.11.254
netmask 255.255.252.0
gateway 10.62.8.1
```

- Client (SchwerMountain, LaubHills, TurkRegion, GrobeForest)
```
auto eth0
iface eth0 inet dhcp
```
