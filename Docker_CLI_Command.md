# Docker CLI Command

Docker is a popular containerization platform that allows you to package and run applications and their dependencies in isolated containers. The Docker Command Line Interface (CLI) provides a wide range of commands for managing containers and images. Here's an explanation of some common Docker CLI commands with examples:

1. `docker pull`:

   - Description: Used to download a Docker image from a registry, such as Docker Hub.
   - Example: `docker pull ubuntu`
2. `docker run`:

   - Description: Create and start a new container from an image.
   - Example: `docker run -it ubuntu`
     - `-it` flags allow you to interact with the container's terminal.
3. `docker ps`:

   - Description: List running containers.
   - Example: `docker ps`
4. `docker ps -a`:

   - Description: List all containers, including stopped ones.
   - Example: `docker ps -a`
5. `docker stop`:

   - Description: Stop a running container.
   - Example: `docker stop container_name_or_id`
6. `docker start`:

   - Description: Start a stopped container.
   - Example: `docker start container_name_or_id`
7. `docker restart`:

   - Description: Restart a running or stopped container.
   - Example: `docker restart container_name_or_id`
8. `docker rm`:

   - Description: Remove one or more containers.
   - Example: `docker rm container_name_or_id`
9. `docker rmi`:

   - Description: Remove one or more images.
   - Example: `docker rmi image_name_or_id`
10. `docker build`:

    - Description: Build a Docker image from a Dockerfile.
    - Example: `docker build -t myapp:1.0 .`
      - `-t` assigns a name and tag to the image, and `.` specifies the build context.
11. `docker images`:

    - Description: List all locally available Docker images.
    - Example: `docker images`
12. `docker exec`:

    - Description: Run a command inside a running container.
    - Example: `docker exec -it container_name_or_id bash`
13. `docker logs`:

    - Description: View the logs of a container.
    - Example: `docker logs container_name_or_id`
14. `docker network`:

    - Description: Manage Docker networks for container communication.
    - Example: `docker network create mynetwork`
15. `docker volume`:

    - Description: Manage Docker volumes for data persistence.
    - Example: `docker volume create myvolume`
16. `docker-compose`:

    - Description: Define and run multi-container applications using a `docker-compose.yml` file.
    - Example: `docker-compose up -d`
      - `-d` runs containers in the background.
17. `docker save` and `docker load`:

    - Description: Save an image to a tar archive file and load it from a file.
    - Example:
      - `docker save -o myimage.tar myimage:1.0`
      - `docker load -i myimage.tar`
18. `docker inspect`:

    - Description: Display detailed information about a container, image, network, or volume.
    - Example: `docker inspect container_name_or_id`
19. `docker cp`:

    - Description: Copy files or directories between the host and a container.
    - Example: `docker cp local_file_or_directory container_name_or_id:/path/in/container`
20. `docker top`:

    - Description: Display the running processes in a container.
    - Example: `docker top container_name_or_id`
21. `docker commit`:

    - Description: Create a new image from a container's changes.
    - Example: `docker commit container_name_or_id mycustomimage:1.0`
22. `docker tag`:

    - Description: Create a tag for an image.
    - Example: `docker tag image_name_or_id myrepository/myimage:1.0`
23. `docker login` and `docker logout`:

    - Description: Log in to or log out from a Docker registry, such as Docker Hub.
    - Example:
      - `docker login`
      - `docker logout`
24. `docker push`:

    - Description: Push an image to a registry.
    - Example: `docker push myrepository/myimage:1.0`
25. `docker pull`:

    - Description: Pull an image from a registry.
    - Example: `docker pull myrepository/myimage:1.0`
26. `docker stats`:

    - Description: Display a live stream of container resource usage statistics.
    - Example: `docker stats container_name_or_id`
27. `docker system prune`:

    - Description: Remove all unused containers, networks, images, and volumes.
    - Example: `docker system prune`
28. `docker info`:

    - Description: Display system-wide information about Docker.
    - Example: `docker info`
29. `docker version`:

    - Description: Show the Docker version information.
    - Example: `docker version`

These additional Docker CLI commands cover various aspects of container management, image handling, and registry interactions. Depending on your use case, you may find these commands helpful in your Docker workflow.
