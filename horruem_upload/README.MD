# Horreum Upload

## Setup

1. Create job configuration file, e.g.;

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

2. [Install Jbang](https://www.jbang.dev/download/)

3. Update `.env` file with configuration specific to your horreum installation

4. Export environmental params;

```shell
$ export $(cat .env | xargs)
```

## Run upload

```shell
 $ ./horreumUpload.java -b 1255 -c ./config.json
```

where;

  -b : Jenkins build id

  -c : path to config file creates in step 1
