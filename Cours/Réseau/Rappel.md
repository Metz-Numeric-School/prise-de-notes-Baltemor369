# Les Matériels
## EndPoints
## Routeur
## Switch
## Câbles
## Server
# Le Réseau
## LAN
## MAN
## WAN

# Protocole

# Modèle OSI

7. Application :
6. Présentation :
5. Session : 
4. Transport : firewall ; PORT ; segment
3. Réseau : routeur ; Ipv4 IPv6 ; packet
2. Liaison : switch / HUB ; addresse MAC (48bits constructor, n°serie de l'interface) ; Trame (Frame)
1. Physique : cable (ethernet, coaxial), Fibre, wifi/bluetooth

# cisco config

## Routeur

renomer le routeur :
`host NAME`

* Penser à allumer les interfaces :
`int Gig0/0/0`
`no shut` 

* les sous interfaces :
`int G0/0/0.<1-4096>`
`encaps dot1Q <1-4096>`
`ip address IP MASK`

## switch

affiche la configuration
`show runnig-config`

affiche en bref les vlan config
`show vlan brief`

?
`switchport trunk allowed vlan all`

`ip routing`

sur l'interface physique
`no switchport` -> devient port routeur
ip add routeur (gateway)

### vlans

`vlan X` X étant le numéro de vlan
`name NAME` rename la vlan

### trunk

aller sur l'interface en question
`interface fa0/1`

mettre le mode trunk
`switchport mode trunk`

affiche les interfaces 
`show interface trunk`

### vtp

pour le transfert de vlan
Faire les Trunk avant

pour le server
`vtp domain nom_domain`
`vtp mode server`
`vtp password my_password`

pour les clients
`vtp domain nom_domain`
`vtp mode client`
`vtp password my_password`

voir table arp
``

table cam
enregistrer qui envoie le message entrant sur quel interface
pour savoir qui est où

# Autre

**
[répartition plage réseau](https://vlsmcalc.vercel.app/)
**

packet type :
arp
bgp
dhcp
dns
eigrp
hsrp
icmp
ospf
rip

4 bit : 16 combinaison
8 bit : 256 
16 : 65K
32 : 4m

port 20 = File Transfert Protocol
port 21 = contrôle FTP
port 22 = Secure Shell Hq
port 53 = DNS
port 80 = HTTP
port 443 = HTTPS
port 500 = SERVER

IEEE : orga des normes WIFI
ISP : internet service provider

Class A 0.0.0.0 -> 127.255.255.255
Class B 128.0.0.0 -> 191.255.255.255
Class C 192.0.0.0 -> 223.255.255.255
Class D Multicast 224.0.0.0 -> 239.255.255.255
Class E 

128 = 1000 0000 = /25
192 = 1100 0000 = /26
224 = 1110 0000 = /27
240 = 1111 0000 = /28
248 = 1111 1000 = /29
252 = 1111 1100 = /30
254 = 1111 1110 = /31
255 = 1111 1111 = /32

# Training

172.16.0.0/23
SALES 200 256
R&D 50 64
MGT 25 32
IT 10 16
PRINTERS 10 16
SERVERS 10 16

172.16.0.0 : network address
172.16.0.2 : gateaway

172.16.0.5 -> 172.16.0.255 : SALES (256)
172.16.1.0 -> 172.16.0.63 : R&D (64)
172.16.1.64 -> 172.16.1.95 : MGT (32)
172.16.1.96 -> 172.16.1.111 : IT (16)
172.16.1.112 -> 172.16.1.127 : PRINTERS (16)
172.16.1.128 -> 172.16.1.143 : SERVERS (16)


## config
un réseau avec switch uniquement
besoin de rien

un réseau avec un routeur
dans routeur :
`enable`
`configure terminal`
\# par interface par réseau
	`interface FastEthernet X/X`
	`ip address IP MASK ` # gateway des réseau
	`no shutdown`

un réseau switch avec vlan
dans switch
`enable`
`conf t`
`int faX/X`
`switchport mode access`
`switchport access vlan X`

ENTRE 2 SWITCH MODE TRUNK
`enable`
`conf t`
`int faX/X`
`sw mode trunk`
