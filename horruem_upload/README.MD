# Horreum Upload

## Setup

1. Create `.env` file with the following entries specific to your horreum installation;

```
HORREUM_USER=
HORREUM_PASS=

JENKINS_HOST=
HORREUM_HOST=
KEYCLOAK_HOST=
KEYCLOAK_REALM=
KEYCLOAK_CLIENT_ID=
```

2. Export environmental params;

```shell
$ export $(cat .env | xargs)
```

3. Create job configuration file, e.g.;

```json
{
    "jobPath": "job/Products/job/Quarkus/job/regression/job/quarkus-startup",
    "artefacts": [
        { 
            "horreumTest": "Quarkus - getting-started - JVM",
            "filePath": "myserver.example.com/getting-started.JVM.json"
        },
        { 
            "horreumTest": "Quarkus - getting-started - native",
            "filePath": "myserver.example.com/getting-started.native.json"
        },
        { 
            "horreumTest": "Quarkus - config-quickstart - JVM",
            "filePath": "myserver.example.com/config-quickstart.JVM.json"
        },
        { 
            "horreumTest": "Quarkus - config-quickstart - native",
            "filePath": "myserver.example.com/config-quickstart.native.json"
        }
    ]

}
```

4. [Install Jbang](https://www.jbang.dev/download/)


## Run upload

```shell
 $ ./horreumUpload.java -b 1255 -c ./config.json
```

where;

  -b : Jenkins build id

  -c : path to config file creates in step 1
