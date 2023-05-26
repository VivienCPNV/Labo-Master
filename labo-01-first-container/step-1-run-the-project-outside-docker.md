# Step 1 - Run the project outside Docker

* [Official Source](https://docs.docker.com/language/java/build-images/)

## Get the project source code

* Clone the repo

```
git clone https://github.com/spring-projects/spring-petclinic.git
```

* Read the readme file carefully

<!---->

* [x] What type of application is it ?
* [x] Which database engine is used ?
* [x] Do we need to install the package manager _MAVEN_ before building the project ?

<!---->

* Inspect the dependencies (pom.xml)

<!---->

* [x] Which version of Java should compatible with the code provided ?

## Setup Java components

### Check your current Java installation

* [x] Where is java installed ?

```
[INPUT]
echo %JAVA_HOME%

[OUTPUT]
C:\Program Files\Java\jdk1.8.0_211
```

* [x] Which current compiler is installed (JDK) ?

```
[INPUT]
javac -version

[OUTPUT]
javac 1.8.0_211
```

* [x] Which current runtime is installed (JRE) ?

```
[INPUT]
java -version

[OUTPUT]
java version "1.8.0_281"
Java(TM) SE Runtime Environment (build 1.8.0_281-b09)
Java HotSpot(TM) 64-Bit Server VM (build 25.281-b09, mixed mode)
```

* [x] Do we need to install the java virtual machine (JVM) ?

```
No, the JVM is bundled with the JRE
```

### Install the Open JDK

* [Oracle Download WebSite](https://jdk.java.net/20/)

{% hint style="info" %}
* Accept the end user license before trying, then
* Then get the target URL (cookies).
{% endhint %}

```powershell
[INPUT]
//TODO

[OUTPUT]
//TODO
```

#### Check the archive integrity before installing the JDK

* [Get the hash provided by Oracle](https://download.java.net/java/GA/jdk20.0.1/b4887098932d415489976708ad6d1a4b/9/GPL/openjdk-20.0.1\_windows-x64\_bin.zip.sha256)
* Generate your local hash based on the archive downloaded ([help](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.3))
* Compare both hashes...

```powershell
[INPUT]
certutil -hashfile openjdk-20.0.1_windows-x64_bin.zip SHA256

[OUTPUT]
31ca4a8cbdea1da7fb441194e756dd1adbedfc05bd1135a1ecc46b4288ea8942
```

#### Unzip jdk archive

```
[INPUT]
unzip openjdk-20.0.1_windows-x64_bin.zip

[OUTPUT]
jdk-20.0.1
```

#### Move the unzip folder to Programs Folder

```
[INPUT]
move jdk-20.0.1 "C:\Program Files\"

[OUTPUT]
//TODO
```

#### Set environment variables

* [Java official documentation](https://dev.java/learn/getting-started/)

<!---->

* [ ] Set JAVA\_HOME variable

```
[INPUT]
set JAVA_HOME=C:\Program Files\jdk-20.0.1

[OUTPUT]
//TODO
```

* [ ] Update PATH environment variable

{% hint style="info" %}
Back up your current path before updating it.

echo %PATH% > path.back
{% endhint %}

```
[INPUT]
set PATH=%JAVA_HOME%\bin;%PATH%

[OUTPUT]
//TODO

```

* [ ] Check the variables

```f
[INPUT]
echo %PATH%

[OUTPUT]
C:\Program Files\jdk-20.0.1\bin;C:\Python311\Scripts\;C:\Python311\;C:\Program Files\ImageMagick-7.1.1-Q16-HDRI;C:\Program Files\Ruby31-x64\bin;C:\Program Files (x86)\VMware\VMware Workstation\bin\;C:\Program Files (x86)\Common Files\Oracle\Java\javapath;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\ProgramData\chocolatey\bin;C:\Program Files\MariaDB 10.10\bin;C:\tools\php81;C:\Program Files\Microsoft VS Code\bin;C:\ProgramData\ComposerSetup\bin;C:\Program Files\Amazon\AWSCLIV2\;C:\Program Files\nodejs\;C:\tools\php82;C:\Program Files\Git\cmd;C:\Program Files\GitHub CLI\;C:\Program Files\Microsoft SQL Server\130\Tools\Binn\;C:\Program Files\Microsoft SQL Server\Client SDK\ODBC\170\Tools\Binn\;C:\Program Files\dotnet\;C:\Program Files\Microsoft SQL Server\150\Tools\Binn\;C:\Program Files\Java\jdk1.8.0_211\bin;;C:\Program Files\Docker\Docker\resources\bin;f
```

## Build and test the project

```
[INPUT]
mvnw package
java -jar target/*.jar

[OUTPUT]
SUCCESS
```

### Result expected 

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
