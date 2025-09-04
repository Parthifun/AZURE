Docker

What is Docker?
Docker is a platform for creating, deploying, and running applications in containers.
* A container is a lightweight, portable package that includes:
    1. Your application code
    2. All necessary libraries and dependencies
    3. Runtime environment
Think of it like packing your app and everything it needs into a self-contained box that can run anywhere—on your laptop, on a cloud server, or on someone else’s computer—without any “it works on my machine” problems.

Why do we use Docker?
1. Consistency across environments
    * Developers, testers, and production servers all run the same container.
    * No more surprises like “it worked on my laptop but failed on the server.”
2. Isolation
    * Each container runs independently.
    * You can run multiple apps on the same server without them interfering with each other.
3. Lightweight
    * Unlike virtual machines, containers share the OS kernel and don’t need a full OS each, so they start fast and use fewer resources.
4. Portability
    * Move containers from development → testing → production easily.
5. Simplifies CI/CD
    * Works perfectly with Jenkins.
    * Jenkins can build a Docker image, run tests inside it, and deploy it automatically.


There is problem faced b/w the the developer & the production

Why it is Popular
It made container technology accessible, simple & developer-friendly.
It is a Cross Platform tool.

Commands for docker
To list out the images      - docker images/docker images ls
To check the containers  -   docker ps shows only running containers
					    -	docker ps -a it display all containers even if it is in pause or stop or running
docker run -d <any tool> - it does two things, it pulls the images & It creates container.
To change the names       - docker run -d —name <any name original name>
To stop container              - docker stop <container name/container id>
To start container             -  docker start <container name/container id>
To delete container           - we has to stop first, we need list the containers, then we can remove
						docker stop <container name/container id>,
						docker ps -a,
						docker rm <container name/container id>
