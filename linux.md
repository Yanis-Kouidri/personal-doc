# Linux

## Change hostname

Change permanantly with

    sudo hostnamectl set-hostname linuxconfig

Check

    hostnamectl

Reboot is required to show it in the prompt

## Message Of The Day (MOTD)

### Add a new message

    sudo vi /etc/update-motd.d/99-custom

Write something like that:

```bash
#!/bin/bash
echo """
SOME TEXT or ASCII Art
"""
```

Change permissions

    sudo chmod 755 /etc/update-motd.d/99-custom

Logout login to check