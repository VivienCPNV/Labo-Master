# Step 3 - Run your image as a container

* [Official Source](https://docs.docker.com/language/java/run-containers/)

<!---->

* [x] Run your "petclinic" docker based on the image created in the previous step.
  * [x] We should access to your application using the http standard port.

Result expected:

{% hint style="info" %}
Linux user, change ^ by ' to execute multi lines commands.
{% endhint %}

```
[INPUT]
curl --request GET ^
--url http://localhost/actuator/health ^
--header 'content-type: application/json'

[OUTPUT]
{"status":"UP"}

//disregard the message curl: (6) Could not resolve host: application
```

* [x] List all Dockers currently running on your local environment. Observe the port forwarding for your "petclinic" docker.

```
[INPUT]
docker container list

[OUTPUT]
CONTAINER ID   IMAGE        COMMAND                  CREATED         STATUS         PORTS     NAMES
84d517f132ec   spring:dev   "./mvnw spring-boot:…"   7 minutes ago   Up 7 minutes             nostalgic_hermann

```

* [x] Stop your "petclinic" docker

```
[INPUT]
docker container stop festive_hermann

[OUTPUT]
festive_hermann
```

* [x] Rename your docker as "petclinic-app"

<!---->

* [Official doc](https://docs.docker.com/engine/reference/commandline/rename/)

```
[INPUT]
docker container rename festive_hermann petclinic-app

[OUTPUT]

```

* [x] Restart your docker using the new name

```
[INPUT]
docker container start petclinic-app

[OUTPUT]
petclinic-app
```

* [x] Display all running dockers with this output format

<!---->

* [Official doc](https://docs.docker.com/config/formatting/)

Result expected:

```
IMAGE                              PORTS.                  NAMES
eclipse-petclinic:version1.0.dev   0.0.0.0:80->8080/tcp.   petclinic-server
```

```
[INPUT]
docker container list --format "table {{.Image}}\t{{.Ports}}\t{{.Names}}"

[OUTPUT]
IMAGE        PORTS                  NAMES
spring:dev   0.0.0.0:80->8080/tcp   petclinic-app
```

