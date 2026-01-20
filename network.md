# Network

## Nmap

### Install

    sudo apt install nmap

### Scan

Scan all up host in a network

    nmap -sn -n 192.168.1.0/24

- `-sn`: No post scan, it only checks if host is up
- `-n`: No DNS name resolution

Scan a specific range of port

    nmap -p 80-1024 192.168.1.150

Scan specific ports

    nmap -p 22,80,443 192.168.1.150

## SS

`ss` stands for Socket Statistic. It is the up-to-date command to investigate on socket on a Linux machine. It replaces `netstat`. `ss` can be installed with `sudo apt install iproute2`.