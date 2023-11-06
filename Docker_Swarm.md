# **Docker Swarm**

Docker Swarm is a container orchestration tool, meaning it allows you to manage multiple containers deployed across multiple host machines. It's native clustering for Docker which turns a group of Docker engines into a single, virtual Docker engine. Here are the key points about Docker Swarm:

- **Cluster Management**: Docker Swarm provides a standard Docker API, which means that any tool that communicates with a Docker daemon can use Swarm to transparently scale to multiple hosts. It involves multiple Docker hosts pooled together to form a cluster.
- **Decentralized Design**: Swarm uses a decentralized design, where services can be deployed and managed across multiple nodes in the cluster. Swarm managers can use several strategies to run containers, such as “emptiest node” – which fills the least utilized machines with containers, or “global” – which ensures each machine gets exactly one instance of the specified container.
- **Declarative Service Model**: With Docker Swarm, you can define your desired state of the service, and it will maintain that state. For example, if you declare that you want four instances of a service to be running, Swarm will create those instances across the nodes in the cluster. If a container or host fails, Swarm will recognize this and start a new container to maintain the desired state.
- **Scaling**: Docker Swarm allows you to scale out/in your application as needed. You can specify how many replicas of a service you want to run in your cluster. Swarm will take care of distributing and running that number of instances.
- **Load Balancing**: Swarm has internal load balancing by distributing service discovery information to all nodes in the swarm. It can also integrate with external load balancers.
- **Rolling Updates**: When you update a service, Swarm can perform rolling updates, which allows you to update a service with zero downtime by incrementally updating containers with new ones.
- **Security**: Docker Swarm includes mutual TLS (Transport Layer Security) and automatic generation of certificates to ensure that all nodes in the cluster are secure and encrypted.

# Docker Swarm Command:

Docker Swarm is a native clustering and orchestration solution for Docker. It allows you to create and manage a swarm of Docker nodes to deploy and manage services across multiple containers. Here's a list of some common Docker Swarm commands with explanations and examples:

**1. `docker swarm init`:**

- Initializes a new Docker Swarm on the current Docker host, making it a manager node.
- Example:

```bash
   docker swarm init --advertise-addr <manager-ip>
```

**2. `docker swarm join`:**

- Adds a worker or manager node to an existing Docker Swarm.
- Example:

```bash
   docker swarm join --token <worker-token> <manager-ip>:<manager-port>
```

**3. `docker swarm leave`:**

- Removes a node (worker or manager) from the swarm.
- Example:

```bash
   docker swarm leave
```

**4. `docker node ls`:**

- Lists all nodes in the swarm.
- Example:

```bash
   docker node ls
```

**5. `docker service create`:**

- Deploys a new service to the swarm.
- Example:

```bash
   docker service create --replicas 3 --name my-web-app -p 8080:80 my-web-image
```

**6. `docker service ls`:**

- Lists the services running in the swarm.
- Example:

```bash
   docker service ls
```

**7. `docker service scale`:**

- Scales a service up or down to a specific number of replicas.
- Example:

```bash
   docker service scale my-web-app=5
```

**8. `docker service update`:**

- Updates the configuration of a running service.
- Example:

```bash
   docker service update --replicas 3 my-web-app
```

**9. `docker service rm`:**

- Removes a service from the swarm.
- Example:

```bash
   docker service rm my-web-app
```

**10. `docker stack deploy`:**
    - Deploys a new stack of services to the swarm.
    - Example:

    ``bash     docker stack deploy -c my-stack.yml my-stack     ``

**11. `docker stack ls`:**
    - Lists the stacks running in the swarm.
    - Example:

    ``bash     docker stack ls     ``

**12. `docker stack services`:**
    - Lists the services within a specific stack.
    - Example:

    ``bash     docker stack services my-stack     ``

**13. `docker stack rm`:**
    - Removes a stack and its associated services from the swarm.
    - Example:

    ``bash     docker stack rm my-stack     ``

**14. `docker secret create` and `docker secret ls`:**
    - Manages secrets that can be used by services in the swarm.
    - Example:

    ``bash     echo "my_secret_password" | docker secret create db_password -     ``

**15. `docker config create` and `docker config ls`:**
    - Manages configurations that can be used by services in the swarm.
    - Example:

    ``bash     docker config create my-config my-config.txt     ``

**16. `docker service inspect`:**

    - Displays detailed information about a specific service, including its configuration and status.
    - Example:

    ``bash     docker service inspect my-web-app     ``

**17. `docker node inspect`:**
    - Provides detailed information about a specific node in the swarm.
    - Example:

    ``bash     docker node inspect <node-id>     ``

**18. `docker service logs`:**
    - Retrieves the logs of a service or tasks within a service.
    - Example:

    ``bash     docker service logs my-web-app     ``

**19. `docker node update`:**
    - Updates the attributes of a node in the swarm, such as availability or role.
    - Example:

    ``bash     docker node update --availability drain <node-id>     ``

**20. `docker secret rm`:**
    - Removes a secret from the swarm. This action revokes access to the secret for services.
    - Example:

    ``bash     docker secret rm db_password     ``

**21. `docker config rm`:**
    - Deletes a configuration from the swarm. Services using the configuration will no longer have access to it.
    - Example:

    ``bash     docker config rm my-config     ``

**22. `docker node promote` and `docker node demote`:**
    - Promotes or demotes a node in the swarm, changing its role between manager and worker.
    - Example:

    ``bash     docker node promote <node-id>     ``

    ``bash     docker node demote <node-id>     ``

**23. `docker service rollback`:**
    - Rolls back a service update to a previous version, reverting to the previous service definition.
    - Example:

    ``bash     docker service rollback my-web-app     ``

**24. `docker node rm`:**
    - Removes a node from the swarm, effectively disconnecting it.
    - Example:

    ``bash     docker node rm <node-id>     ``

**25. `docker info`:**
    - Provides information about the Docker Swarm, such as the number of nodes, managers, and worker nodes.
    - Example:

    ``bash     docker info     ``

**26. `docker service ps`:**

    - Lists the tasks (replica containers) for a service, showing details about each task's state, ID, and node assignment.
    - Example:

    ``bash     docker service ps my-web-app     ``

**27. `docker node ls --filter`:**
    - Lists nodes in the swarm based on filters. You can filter nodes by role (e.g., manager, worker) or availability (e.g., active, drain).
    - Example:

    ``bash     docker node ls --filter "role=worker"     ``

**28. `docker network create` and `docker network ls`:**
    - Manages overlay networks in Docker Swarm, allowing containers in the swarm to communicate across different nodes.
    - Example:

    ``bash     docker network create -d overlay my-overlay-network     ``

**29. `docker service logs`:**
    - Retrieves logs for a specific service or task within a service. This command is useful for debugging and monitoring services.
    - Example:

    ``bash     docker service logs my-web-app     ``

**30. `docker service update`:**
    - Updates the configuration of a running service, allowing you to change replicas, images, or other service settings.
    - Example:

    ``bash     docker service update --image my-new-image:latest my-web-app     ``

**31. `docker node update`:**
    - Modifies node attributes like availability or role in the swarm, which can be useful for maintenance and management tasks.
    - Example:

    ``bash     docker node update --availability drain <node-id>     ``

**32. `docker service inspect --pretty`:**
    - Provides a detailed, human-readable representation of a service's configuration and status.
    - Example:

    ``bash     docker service inspect --pretty my-web-app     ``

**33. `docker node demote`:**
    - Demotes a manager node to a worker node, changing its role in the swarm.
    - Example:

    ``bash     docker node demote <node-id>     ``

**34. `docker node promote`:**
    - Promotes a worker node to a manager node, changing its role in the swarm.
    - Example:

    ``bash     docker node promote <node-id>     ``

These additional Docker Swarm commands allow you to manage services, nodes, and networks within a Docker Swarm cluster, making it easier to deploy and maintain complex containerized applications in a distributed environment.

# Docker Swarm Example :

Here's a simple Docker Swarm example that demonstrates how to create a Docker Swarm cluster and deploy a service using images from Docker Hub. In this example, we'll deploy a simple web service using NGINX.

**Prerequisites:**

- Ensure that you have Docker installed on multiple hosts or virtual machines (at least two) that can communicate with each other. You'll need one manager node and one or more worker nodes.
- The Docker Swarm cluster should be initialized on the manager node. You can use the `docker swarm init` command on the manager to initiate the swarm.

**1. Initialize the Docker Swarm:**

- On your manager node, run the following command to initialize the Docker Swarm. This will make it the manager node.

```bash
   docker swarm init
```

- After running the command, it will output a token for joining worker nodes to the swarm. Save this token; you'll need it to join worker nodes.

**2. Join Worker Nodes:**

- On your worker nodes, run the following command to join them to the Docker Swarm using the token you obtained from the manager.

```bash
   docker swarm join --token <your-worker-token> <manager-ip>:<manager-port>
```

**3. Deploy a Simple NGINX Service:**

- Create a `docker-compose.yml` file with the following content to deploy an NGINX service. This will create a simple web server.

```yaml
   version: '3'

   services:
     nginx:
       image: nginx:latest
       ports:
         - "80:80"
```

**4. Deploy the Service:**

- Run the following command on your manager node to deploy the NGINX service to the swarm.

```bash
   docker stack deploy -c docker-compose.yml my-stack
```

**5. Check Service Status:**

- Check the status of your service using the following command. This will show the number of replicas running.

```bash
   docker service ls
```

**6. Access NGINX:**

- You can access the NGINX web server by opening a web browser and navigating to the IP address or domain name of any node in your Docker Swarm, on port 80.

**7. Scaling the Service:**

- One of the advantages of Docker Swarm is the ability to easily scale services. You can scale the NGINX service to run on multiple replicas across the swarm using the following command:

```bash
   docker service scale my-stack_nginx=3
```

   This command scales the NGINX service to run three replicas. You can adjust the number as needed.

**8. Updating the Service:**

- You can update the NGINX service with a new image or configuration. To do so, modify the `docker-compose.yml` file with your desired changes and redeploy the service:

```bash
   docker stack deploy -c docker-compose.yml my-stack
```

   This will apply the changes to the NGINX service in the swarm.

**9. Rolling Back the Service:**

- If you need to roll back a service update, you can use the following command to revert to the previous version:

```bash
   docker service rollback my-stack_nginx
```

**10. Removing the Service and Stack:**
    - When you're done with your service and stack, you can remove them using the following commands:

    ``bash     docker stack rm my-stack     ``

    This will remove the NGINX service and the stack.

**11. Leave the Swarm:**
    - If you want to leave the Docker Swarm on a node, run the following command on that node:

    ``bash     docker swarm leave     ``

**12. Inspecting the Swarm:**
    - You can inspect the swarm to view detailed information about nodes, services, and tasks using commands like `docker node ls`, `docker service ps`, and `docker service inspect`.

**13. Node Labels:**
    - You can assign labels to nodes in your Docker Swarm, allowing you to target specific nodes for service placement based on their attributes. To assign a label to a node, you can use a command like:

    ``bash     docker node update --label-add mylabel=web node-1     ``

    You can then use these labels in your service definitions to control where services are deployed.

**14. Service Constraints:**
    - You can use service constraints to specify rules for where a service should run within the swarm. For example, you can place a service on nodes with specific labels using the `--constraint` flag when creating a service.

    ``bash     docker service create --constraint "node.labels.mylabel==web" my-service     ``

**15. Service Networks:**
    - Docker Swarm provides built-in overlay networks that allow services running on different nodes to communicate with each other. You can create a service-specific network or use an existing one.

**16. Service Updates with Health Checks:**
    - When updating services, you can specify health checks to ensure new replicas are healthy before old ones are removed. This ensures zero-downtime updates.

**17. Stacks and Compose Files:**
    - Docker Compose files can be used to define stacks, which are groups of services. Stacks make it easier to manage multi-service applications within a swarm.

**18. Secrets Management:**
    - Docker Swarm provides a way to manage sensitive data like passwords and API keys as secrets. You can create, update, and use secrets in service definitions.

**19. Deploying with High Availability:**
    - Docker Swarm is designed for high availability. By deploying manager nodes across multiple hosts and configuring a quorum of managers, you ensure that the swarm remains available even if some manager nodes fail.

**20. Interacting with the Swarm API:**
    - You can use the Docker Swarm API to programmatically manage the swarm, create and update services, and obtain information about nodes and services.

**21. Monitoring and Logging:**
    - You can integrate monitoring and logging solutions with Docker Swarm to gain insights into the health and performance of your services and nodes.

These advanced concepts and operations provide additional flexibility and control over your Docker Swarm deployment. Docker Swarm is a versatile tool for orchestrating containerized applications and can handle complex use cases in production environments.
