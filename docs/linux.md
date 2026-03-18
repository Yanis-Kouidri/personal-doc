# Linux

## Change hostname

Change permanently with

```bash
sudo hostnamectl set-hostname linuxconfig
```

Check

```bash
hostnamectl
```

Reboot is required to show it in the prompt

## Message Of The Day (MOTD)

### Add a new message

```bash
sudo vi /etc/update-motd.d/99-custom
```

Write something like that:

```bash
#!/bin/bash
echo """
SOME TEXT or ASCII Art
"""
```

Change permissions

```bash
sudo chmod 755 /etc/update-motd.d/99-custom
```

Logout login to check

## APT packet research

When you want to execute a command, but you don't remind the name of the packet who contain this command you can try:

### Simply run the command

On Ubuntu, it will help you with the package to install:

```bash
$ traceroute
Command 'traceroute' not found, but can be installed with:
sudo apt install inetutils-traceroute  # version 2:2.6-1ubuntu3, or
sudo apt install traceroute            # version 1:2.1.6-1
```

### Search using apt-file

Install apt-file

```bash
sudo apt install apt-file
```

Update list

```bash
sudo apt-file update
```

If you know exactly the path you can try:  
Example for the `dig` command

```bash
apt-file find /usr/bin/dig -F
```

`-F` will search for this exact pattern

else you can try:

```bash
apt-file find '/dig$' -x
```

That will search all packets that contain a script named `dig`
`-x` specify that pattern is a regex.

Example output:

``` bash
apt-file find -x /dig$
    apparmor: /etc/apparmor.d/dig
    bind9-dnsutils: /usr/bin/dig
    epic4: /usr/share/epic4/script/dig
    epic4-help: /usr/share/epic4/help/8_Scripts/dig
```

Here we can guess that to correct one is `bind9-dnsutils`

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

## Misc

### tldr

Get useful command usage example

Install

```bash
sudo snap install tldr
```

Get tar usage example:

```bash
tldr tar
```

### sudoedit

To edit a root file use `sudoedit` instead of `sudu vi`.
It allows you to still have your user `.vimrc` config.

### Files and folders size

Get size of a folder

```bash
du -sh a_folder/
```

Get files and folders size with a TUI

Install

```bash
sudo apt install ncdu
```

Use (press q to quit)

```bash
ncdu .
```
