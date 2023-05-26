# Known issues

## Context

* Windows 10
* Docker Desktop v4.15.0
* WSL Version

```
ps> wsl --status
Default Distribution: Debian
Default Version: 2

Windows Subsystem for Linux was last updated on 22/09/2022
WSL automatic updates are on.

Kernel version: 5.10.16
```

## Port 3306 already in use

### Issue

```
[INPUT]
When try to run a docker that use the 3306 port and the port is already used by another process.


[OUTPUT]
docker: Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:3306 -> 0.0.0.0:0: listen tcp 0.0.0.0:3306: bind: Only one usage of each socket address (protocol/network address/port) is normally permitted.
```

### Solution

Identify the service concerned and either:
* change the port used for one of the service (on the host)
* change the port forwarded to the dockerized service