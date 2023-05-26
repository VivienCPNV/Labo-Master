# Labo 00 - Set up Docker Environment

## Docker Setup

### [Get Docker](https://docs.docker.com/get-docker/) and install it

{% hint style="info" %}
When prompted, ensure the <mark style="color:red;">**Use WSL 2 instead of Hyper-V**</mark> option on the Configuration page is selected or not depending on your choice of backend
{% endhint %}

{% hint style="info" %}
<mark style="color:red;">To run Windows containers, you need Windows 10 or Windows 11 Professional or Enterprise edition</mark>. Windows Home or Education editions will only allow you to run Linux containers.
{% endhint %}

### Launch docker desktop and run this command to check all versions (Client, Server)

```
[INPUT]
docker version

[OUTPUT]
docker version
Client:
 Version:           20.10.21
 API version:       1.41
 Go version:        go1.18.7
 Git commit:        baeda1f
 Built:             Tue Oct 25 18:08:16 2022
 OS/Arch:           windows/amd64
 Context:           default
 Experimental:      true

Server: Docker Desktop 4.15.0 (93002)
 Engine:
  Version:          20.10.21
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.18.7
  Git commit:       3056208
  Built:            Tue Oct 25 18:00:19 2022
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.6.10
  GitCommit:        770bd0108c32f3fb5c73ae1264f7e503fe7b2661
 runc:
  Version:          1.1.4
  GitCommit:        v1.1.4-0-g5fd4c4d
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
```

* [ ] [Enable BuildKit on your machine](https://docs.docker.com/build/buildkit/#getting-started).

{% hint style="info" %}
If you have installed Docker Desktop, you don’t need to enable BuildKit. If you are running a version of Docker Engine version earlier than 23.0, you can enable BuildKit either by setting an environment variable, or by making BuildKit the default setting in the daemon configuration.
{% endhint %}

### Result expected

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p>This screen shot can differ from your own installation.</p></figcaption></figure>

## Git Setup

### Check if the version of your installation is up to date&#x20;

* Check the current stable version.
* Check your local version.

```
[INPUT]
git --version

[OUTPUT]
git version 2.40.1.windows.1
```

### Proceed to update if needed and [read the release note](file:///C:/Program%20Files/Git/ReleaseNotes.html).

## IDE

{% hint style="info" %}
Docker recommends using [IntelliJ Community Edition](https://www.jetbrains.com/idea/download/).\
\
Do not forget to enable Docker plugin:\
\* [Enable Docker plug-in](https://www.jetbrains.com/help/idea/docker.html)\
\
On Ultimate Version, the plug-in is enabled by default.
{% endhint %}
