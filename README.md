![enter image description here](https://nayan.co/blog/Rails/rails-docker/rails-docker.jpg)

## Sample dockerized Rails app with PostgreSQL

This repo contains the source code for a dockerized sample Rails app in its own isolated container along with another isolated container for persisting data into PostgreSQL database.

To play with it just pull the docker image and run it with Docker Compose:

**Pull docker image**
```
docker pull ingmarsk/rails-sample
```

**Run Rails + Postgres services all-in-one**
```
docker-compose up
```

Then visit http://localhost:3005/

**To apply codebase changes**
```
docker-compose build
docker-compose up
```

**To stop the app**
```
docker-compose down
```

**To remove the image**
```
docker rmi ingmarsk/rails-sample
```

## Visualize persisted data on TablePlus

All Postgres data from the rails app is persisted in a volume from the host machine so the web and database services can be rebuild without data loss.

To visualise the data, you can connect to the postgres container `rails-sample_db_1`  which is mapped to the same port wich Postgres uses on the host machine: `0.0.0.0:5432->5432/tcp`

You can check it by running `docker ps`:

![enter image description here](https://i.ibb.co/dDR28L8/Screenshot-2021-04-05-at-21-08-10.png)

Open up a new TablePlus PostgreSQL Conenction:
* **Name:** docker-sample-app-development
* **Tag:** local
* **Host/Socker:** 0.0.0.0
* **Port:** 5432
* **User:** postgres
* **Password:** password
* **Database:** myapp_development
