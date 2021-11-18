---
title: Security
---

# Connections

- Copy ssh public key
- Set ssh password authentication to `PasswordAuthentication no`
- Enable Fail2Ban
- Disable root account login (default on Ubuntu)
- Use non-standard ports (e.g. 2897 instead of 22)

# Updates

`ansible webservers -m apt -a "upgrade=dist update_cache=yes"`
- `apt-mark hold` to prevent certain packages updating

# Monitor Logs

- Rotate and archive, don't let log files fill up disk
