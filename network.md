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

## Journalctl

A CLI tool to manage logs.

To see all logs
```bash
journalctl
```

To see only 20 last logs
```bash
journalctl -n 20
```

To follow logs output
```bash
journalctl -f
```

To see kernel logs only
```bash
journalctl -k
```

To see specific process logs (example for ssh service)
```bash
journalctl -u ssh.service
```

To filter by time:
```bash
journalctl --since "2023-10-27 10:00:00" --until "2023-10-27 11:00:00"
```

To filter by log level:
```bash
journalctl -p 1 -b
```
- `-b`: To see error only until last reboot
- `-p 1`: To see log level 1 and above

There are 8 log levels, from the most critical to the most informative

| Log level | Name |
| --- | --- |
| 0 | `emerg` |
| 1 | `alert` |
| 2 | `crit` |
| 3 | `err` |
| 4 | `warning` |
| 5 | `notice` |
| 6 | `info` |
| 7 | `debug` |






