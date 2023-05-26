# Step 1 - Run a database in a container

* [Official Source](https://docs.docker.com/language/java/develop/#run-a-database-in-a-container)

## Prerequisites

Take the time to read a first time this documentation : [Docker and Volumes](https://docs.docker.com/storage/volumes/)

Environment setup





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

* [ ] List all Dockers currently running on your local environment. Observe the port forwarding for your "petclinic" docker.

```
[INPUT]
//TODO

[OUTPUT]
//TODO

```

* [ ] Stop your "petclinic" docker

```
[INPUT]
//TODO

[OUTPUT]
//TODO
```

* [ ] Rename your docker as "petclinic-app"

<!---->

* [Official doc](https://docs.docker.com/engine/reference/commandline/rename/)

```
[INPUT]
//TODO

[OUTPUT]
//TODO
```

* [ ] Restart your docker using the new name

```
[INPUT]
//TODO

[OUTPUT]
//TODO
```

* [ ] Display all running dockers with this output format

<!---->

* [Official doc](https://docs.docker.com/config/formatting/)

Result expected:

```
IMAGE                              PORTS.                  NAMES
eclipse-petclinic:version1.0.dev   0.0.0.0:80->8080/tcp.   petclinic-server
```

```
[INPUT]
//TODO

[OUTPUT]
//TODO
```

