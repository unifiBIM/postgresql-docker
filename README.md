# postgresql-docker
This repository provide a configuration file for the deployment of a stack, composed by postgreSQL and pgAdmin, on a local environment using Docker (Docker Compose precisely).

## Tools
First, we need to install the tools required, based on the our OS:
- [Docker](https://docs.docker.com/get-docker/);
- [Docker Compose](https://docs.docker.com/compose/install/).

Instead the services that we are going to use are:
- [**PostgreSQL**]([https://hub.docker.com/_/telegraf](https://hub.docker.com/_/postgres));
- [**pgAdmin4**]([https://hub.docker.com/_/influxdb](https://hub.docker.com/r/dpage/pgadmin4))

## ⚡️ Getting Started

Clone the project

```bash
git clone https://github.com/unifiBIM/postgresql-docker
```

Navigate to the project directory

```bash
cd postgresql-docker
```

Change the environment variables define in `.env` that are used to setup and deploy the stack
```bash
├── .env         <---
├── docker-compose.yml
└── ...
```

Start the services
```bash
docker-compose up -d
```

## Open pgAdmin
After running Docker Compose services, open web browser and go to 8888:80. The port number is based on the mapping we configured under pgadmin service. Then key-in the email and password configured using the environment variable: PGADMIN_DEFAULT_EMAIL and PGADMIN_DEFAULT_PASSWORD.

The next steps are:
- click "Add New Server" under "Quick Links";
- enter "Name" under "General". The value can be anything;
- enter "Host name/address", "Username" and "Password" under Connection:
  - for "Host name/address", the value is the Docker Compose database service name, in our case is postgres;
  - for "Username", the value is the environment variable POSTGRES_USER;
  - for "Password", the value is the environment variable POSTGRES_PASSWORD;
- click "Save" to finish create. After done, we can get access to the database from the sidebar.

## Stopping Docker Compose
To stop Docker Compose service, just execute command: 
```bash
docker-compose down
```

