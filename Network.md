`SMTP` -> Port 25 
`FTP` -> Port 21
`SSH` -> Port 22
`Telnet` -> Port 23
`(UDP/TCP)-DNS` -> 53
`HTTP` -> Port 80
`POP3` -> Port 110
`NetBios` -> Port 139
`IMAP` -> Port 143
`(UDP)-SNP` -> Port 161
`HTTPS` -> Port 443
`SMB, Microsoft-DS` -> Port 445
`RSH` -> Port 514
`VMware` -> Port 902
`MSSQL` -> Port 1433
`Oracle` -> Port 1521
`MySQL` -> Port 3306
`RDP` -> 3389
`VNC` -> Port 5900
`Proxy, Application Server` -> 8080, 8081
`iPhone sync` -> 62078


Microsoft Windows Browser Protocol -> Port 136

First three digit pairs in mac address tells us about the manufacturer of the device.

The Stream is a collection of packets that form a network conversation from the beginning to the end, just like a story.

8.8.8.8 IP address of Google DNS.

# TCP Dump:
TCP is a packet analyzing tool.

**Options:**
1. `-D` *List of Network Interfaces*
2. `-i` *To specify interface to listen*
3. `-n` *Don't convert address to names*
4. `-v` `-vv` `-vvv` *Verbosity Levels*
5. `-w` *Write raw packets to the file*
6. `-r` *Reads packets from a file*
7. `-A` *Prints each packet as an ASCII only headers*
8. `-X` *Print in ASCII and Hex form*
9. `-x` *Prints in Hex form only*

**Filtering**
1. `ip`, `arp`,`udp`,`tcp`,`icmp`...
2. `host`,`net`
3. `port`,`portrange`
4. `src`,`dst`
5. `and`, `or`

# HPING:
Dos with HPING:
```bash
hping3 --flood  -S -V --rand-source "Target Domain here"
```

# Nmap:
1. Host Detection
2. Port Scanning
3. Service and Version Detection
4. Operating System Detection
5. Firewall Detection
6. Vulnerability Assessment
7. Bruteforce Attack
8. Exploitation

## Arguments:
1. `-s` Scan Type
2. `-n` Don't convert to domain names
3. `-Pn` to avoid host discovery
4. `--reason` it states the reason why port is marked as open,closed or filtered.

## Ping Scan:
Our first goal is to reduce IP ranges to active or interested hosts.
`-sn | -sP` *No port Scan*

```bash
#Returns Host Up from 0 to 255
nmap -sn 192.168.43.0/24 
#shows only IP Address with Some Nmap text
nmap -sn 192.168.43.0/24 | grep "Nmap scan" 
# avoid domain names
nmap -sn 192.168.43.0/24 -n | grep "Nmap scan" 
#Below Command will return only IP Address
nmap -sn 192.168.43.0/24 -n| grep "Nmap scan" | cut -d" " -f5
```



## SYN Scan:
Default and Most Popular Type of Port Scan.
`-sS` *Half Open Scanning*

```bash
sudo nmap -sS 192.168.43.0/24 --top-ports 50
```

*Open* means 
* Port is accessible 
* A service is listening the port.
*Closed* means 
* Port is accessible
* Nothing is filtering the port
* No service is listening to the port
* Host sends back a RST flag
*Filtered* means
* No answer
* Filtered by a security system
* Port might be open or close

```bash
sudo nmap -sS 192.168.43.0/24 -p22,80,100-200

sudo nmap -sS -sU 192.168.43.145 -pT:80,43,U:53,139-150

sudo nmap -sS -sU 192.168.43.206 -p1-65535 
```

Port Ranges From `1 to 65535`
IP Ranges From `0 to 255`

## TCP Scan:
`-sT` indicates that the scan type is TCP.

Send `SYN` Packet
Receive `SYN,ACK` Packet (*If Port is Open/Listening*) else `ICMP` unreachable error is received
And we send `RST` packet to interrupt the three-way handshake in normal condition an `ACK` packet is sent to perform a three way handshake

```bash
nmap -sT -n -Pn "Ip Address" --top-ports 100
```

In this type of scan the three way handshake is completed and the destination keeps a record of it which indicates that this is not a much of a stealthy scan.

## UDP Scan:
`-sU` indicates that the scan type is UDP.

Important UDP Ports are:
1. `DNS` -> Port 53
2. `TFTP` -> Port 69
3. `DHCP` -> Port 67-68 
4. `NTP` -> Port 123
5. `SNMP` -> Port 161-162

Send empty `UDP` packets in general. Should run with version detection option for more accurate results 

```bash
sudo nmap -n -Pn -sU 172.20.10.1 --top-ports 10 --reason -sV
```

```bash
netstat -tnlp
service ssh stop #Stop ssh service
nano /etc/ssh/sshd_config #edit ssh config file
```





