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

## Dockerfile encoding in UTF16 instead of UTF8

### Issue

\[INPUT]&#x20;

`docker build --tag java-docker:dev .`

\[OUTPUT]

```
[+] Building 0.1s (2/2) FINISHED
 => [internal] load build definition from Dockerfile                                                                                                                                                      0.0s 
 => => transferring dockerfile: 32B                                                                                                                                                                       0.0s 
 => [internal] load .dockerignore                                                                                                                                                                         0.1s 
 => => transferring context: 34B                                                                                                                                                                          0.0s 
failed to solve with frontend dockerfile.v0: failed to create LLB definition: dockerfile parse error line 1: unknown instruction: 
```

### Solution

Solved by changing the Dockerfile encoding (notepad, save as utf8)

## Failed to solve with frontend dockerfile.v0

### Issue

\[INPUT]

```
docker build --tag java-docker:dev .
```

\[OUTPUT]

```
[+] Building 1.1s (3/3) FINISHED
 => [internal] load .dockerignore                                                                                                                                                                         0.0s 
 => => transferring context: 34B                                                                                                                                                                          0.0s 
 => ERROR resolve image config for docker.io/docker/dockerfile:1                                                                                                                                          0.6s 
------
 > resolve image config for docker.io/docker/dockerfile:1:
------
failed to solve with frontend dockerfile.v0: failed to solve with frontend gateway.v0: rpc error: code = Unknown desc = error getting credentials - err: exec: "docker-credential-desktop": executable file not
 found in %PATH%, out: ``

```

### Solution

* Run Dockerdesktop->Settings->DockerEngine
* Disable "buildkit" to false

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Docker Desktop- change Buildkit enable status</p></figcaption></figure>

