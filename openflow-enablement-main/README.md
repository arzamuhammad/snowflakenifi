# Openflow Enablement

## Part 1: NiFi Enablement
### 1.1: Watch NiFi overview and tech deep dive
Start by watching the recording (and associated deck) here:
* [NiFi Overview and Tech Deep Dive](https://drive.google.com/file/d/1HHAVhXMM76kKnByHQGDtnUmm3wV66NMU/view?usp=drive_link) (Recording)
* [NiFi Overview and Tech Deep Dive](https://docs.google.com/presentation/d/1B7A9NdbY7urz0_scG0gyVee8di_5mucizX70s3pYyoU/edit) (Deck)

### 1.2: Run NiFi locally in Docker
#### Prerequistes
The prereqs for this are very simple:
* Docker Desktop installed on your laptop. If you don't have Docker installed, please follow the [Docker Setup](https://snowflake.service-now.com/lift?id=kb_article&sysparm_article=KB0015333) article on the Lift.
* Access to the [Sales Engineering group in GitLab](https://snow.gitlab-dedicated.com/snowflakecorp/SE/sales-engineering). If you don't have access, submit a [Gitlab Service Request](https://lift.snowflake.com/lift?id=esc_sc_cat_item&table=sc_cat_item&sys_id=2fcd5379dbd58214d36db8f3f3961966&searchTerm=gitlab) on the Lift and to choose the following values:
    * Who is this Request for? &lt;Your name&gt;
    * Select Category:  Get Access to Gitlab
    * Do you need access to a group or team in Gitlab? Yes
    * Gitlab Team Groups Name: Sales Engineering
    * Gitlab Access Role Name: Developer
    * Description / Justification: &lt;Fill out&gt;
* The Chrome or Safari web browser installed on your laptop. Needed to access NiFi running locally, due to Prisma restrictions with self-signed certificates.

#### Step 1: Clone this repository locally
To clone this repository locally, open a terminal and run the following commands:
```bash
git clone https://snow.gitlab-dedicated.com/snowflakecorp/SE/sales-engineering/openflow-enablement.git
cd openflow-enablement
```

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

### 1.3: Complete NiFi Hands On Labs
There are 3 Hands On Labs associated with the NiFi enablement:
1. [NiFi HOL Shakespeare](https://docs.google.com/document/d/14hUZGPxIdcsrAjKlPMWYnc-FzDOyrUrzp0IXEP2jpUU/edit?tab=t.0)
1. [NiFi HOL Snowflake Read](https://docs.google.com/document/d/1PsNdjHYSx5Kl3UIWohD2mInAQ1XBzEzNmtmBCm08qyY/edit?tab=t.0)
1. [NiFi HOL Snowflake Write](https://docs.google.com/document/d/1MaJBwCKG5_ndTkDOqrgF9WA_YcHTJSdSN6oCipyL2As/edit?tab=t.0)
