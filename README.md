
## Sample Rails app with PostgreSQL dockerized :whale:

This repo contains the source code for a dockerized sample Rails app in its own isolated container along with another isolated container for persisting data into PostgreSQL database.

To play with it just pull the docker image and run it with Docker Compose:

```
docker pull ingmarsk/rails-sample
```

```
docker-compose up
```

Then visit http://localhost:3005/

