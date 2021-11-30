# Create container and open interactive shell in docker container
    docker run --interactive --tty container bash
    docker run -it container bash
    
# Run docker in background
    docker run -d

# start container
    docker start container

# Open interactive bash in contaner - must be running
    docker exec -it [continer] bash

# Copy data between host and docker container
    docker cp ./test.file [container id/ container name]:/home/test
    
# Create build with name
    docker build --tag name . 
    
# Open ports on docker and assign it to host's random port
    docker run --publish 5000 container 

# Open ports on docker and assign it to host's specific port
host port : container port
    docker run --publish 5005:5000 container 
    
# Reattach to docker session
    docker attach [container]
    
# Login into container as root
docker-compose exec -u 0 app bash

# Delete all containers
docker rm -f $(docker ps -a -q)

# Delete all volumes
docker volume rm $(docker volume ls -q)

# Delete all not used networks
docker network prune