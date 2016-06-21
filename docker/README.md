# Docker

Remove all stopped containers

    docker rm $(docker ps -a -q)

Remove all images

    docker rmi $(docker images -q)

Remove all images without tag

    docker rmi $(docker images | grep "^<none>" | awk "{print $3}")

Remove all volumes

    docker volume rm $(docker volume ls -qf dangling=true)

Enter a container

    docker exec -it <CONTAINER_ID|CONTAINER_NAME> bash
