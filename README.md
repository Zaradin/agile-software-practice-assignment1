# Agile Software Practice - Assignment 1.

## Previous labs

The first part was looking back at the previous labs where the mongo and express containers were used and incorperate them into this projects compose file.

## Adding the redis image

The next part I focused on adding the redis image. The redis server is used to cache responses from the API and rate-limit requests to it. It was important to get this redis working before going any further because the api relies on it.

## Adding a seeding container

When the movie-api was running I logged into it using the `docker exec -it movie-api /bin/sh` command. Poking around and looking at files I found a `docker-compose.yml` file which included some docker commands and starter code for mongodb seeding. Using this got me started in setting up seeding.

Also creating another container for seeding was important to get the development and production profiles working. This made it easier for running the `docker-compose.yml` file for the different environments (dev, prod).

## Docker profiles

Using the docker profiles feature made it trvial to set up dynamic docker container execution. adding the `- profile dev` to mongo express and the mongo seeding containers ensured that those containers only ran when the `--profile dev` argument was passed when running the docker compose file.

### commands

- docker-compose -f docker-compose.yml --profile dev up -d --force-recreate
- docker-compose -f docker-compose.yml up -d --force-recreate
- docker stop $(docker ps -q)
- docker-compose down --volumes
