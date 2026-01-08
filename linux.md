# Linux

## Change hostname

Change permanantly with
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