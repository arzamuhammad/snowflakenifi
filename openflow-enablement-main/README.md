# Openflow Enablement

### 1.2: Run NiFi locally in Docker
#### Prerequistes
The prereqs for this are very simple:
* Docker Desktop installed on your laptop.


#### Step 1: Clone this repository locally
To clone this repository locally, open a terminal and run the following commands:


#### Step 2: Start Nifi
To start NiFi simply open a Terminal, change to the `nifi_docker` folder, and then run Docker Compose. It's just these two commands:
```bash
cd nifi_docker
docker compose up -d --build
```

Note: This will first build the Docker image and then start the container, both in one step! If you're interested, you can review the [Dockerfile](nifi_docker/Dockerfile) and [docker-compose.yml](nifi_docker/docker-compose.yml) files for the details.

Once the container has started, you can access NiFi by visiting the following URL:
[https://localhost:8443/nifi](https://localhost:8443/nifi)

And use the following credentials to login (set in the [docker-compose.yml](nifi_docker/docker-compose.yml) file):
* Username: admin
* Password: adminpassword

Note: You won’t be able access the NiFi UI with the Prisma Access browser, use Chrome or Safari instead and accept the localhost certificate warning.


#### Step 3: Stop and/or restart NiFi
When finished working with NiFi you can stop the Docker container by running the following command:
```bash
docker compose down
```

And if you need to restart Nifi for any reason, you can run this command:
```bash
docker compose restart nifi
```

#### Other useful Docker commands
To list the contents of a folder in the running container, for debugging, try this:
```bash
docker exec nifi ls /opt/nifi/nifi-current/lib
```

To clean up when done and delete the related Docker volumes and image, run the following commands:
```bash
docker compose down --volumes --rmi 'all'
```

