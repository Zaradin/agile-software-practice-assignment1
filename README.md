# Agile Software Practice - Assignment 1.

## Previous labs

The first part was looking back at the previous labs where the mongo and express containres were used and incorperate them into this projects compose file.

### commands

- docker-compose -f docker-compose.yml --profile dev up -d --force-recreate
- docker stop $(docker ps -q)
- docker-compose down --volumes
