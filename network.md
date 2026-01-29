# Network

## Nmap

### Install

```bash
sudo apt install nmap
```

### Scan

Scan all up host in a network

```bash
nmap -sn -n 192.168.1.0/24
```

- `-sn`: No post scan, it only checks if host is up
- `-n`: No DNS name resolution

Scan a specific range of port

```bash
nmap -p 80-1024 192.168.1.150
```

Scan specific ports

```bash
nmap -p 22,80,443 192.168.1.150
```

## SS

`ss` stands for Socket Statistic. It is the up-to-date command to investigate on socket on a Linux machine. It replaces `netstat`. `ss` can be installed with `sudo apt install iproute2`.

### Common usage

To list all TCP and UDP sockets listening on the machine and their associated process:

```bash
sudo ss -tunlp
```

- `-t`: TCP
- `-u`: UDP
- `-n`: No name resolution (80 instead of http)
- `-l`: Listening sockets only (no established connection)
- `-p`: Display with process is listening on that port (require `sudo`)

## nmcli

`nmcli` is the tool of **NetworkManager** to manage networking on a client Linux machine. On server, it's `Netplan` that is used to manage networking. While `ip` command is used to debug or to set temporary interface, `nmcli` allow creating persistent interfaces.

### Wi-Fi

Check Wi-Fi access points available

```bash
nmcli dev wifi
```

### General
Show interfaces (virtual and physical)
```bash
nmcli device
```

Show connections
```bash
nmcli con show
```

Up or down a connection
```bash
sudo nmcli con up "MY-CON"
```