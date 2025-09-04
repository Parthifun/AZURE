ACR
"In our project, we had several microservices running in containers that needed reliable and secure deployment. To manage the container images, I used Azure Container Registry. This allowed me to store, organize, and control access to all our container images efficiently."

“When we built a new version of a service, my first responsibility was to push the Docker image to the registry. This was important because it gave us a central and secure place to store all our container images. We couldn’t use public registries since some images had proprietary code and sensitive configuration, so keeping them private was necessary."  Next, I ensured proper versioning and tagging of every image. Each release was tagged with clear identifiers, like v1.0 or v1.1. This made it easy to roll back to a previous version if we discovered a bug, ensuring minimal disruption in production.

Integration with Azure Kubernetes Service (AKS) was another key part of my work. I configured Kubernetes to securely pull images directly from ACR by setting up service principals and permissions. This ensured that only authorized nodes could access our images, maintaining security while enabling automated deployments.

Security and governance were always top priorities. I implemented role-based access control (RBAC) in ACR, giving developers, QA, and deployment services the exact permissions they needed—nothing more, nothing less. This kept our workflow safe and auditable.

Finally, I automated the entire process using CI/CD pipelines in Azure DevOps. Whenever code was merged into the main branch, the pipeline would build the Docker image, push it to ACR, and update the Kubernetes deployment with the new version. This automation not only sped up our release cycles but also eliminated human errors, making deployments reliable and repeatable.
