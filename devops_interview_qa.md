## 6️⃣ Azure Virtual Network (VNet)

Q1. What is a VNet?
A1. A VNet is a private network in Azure that allows resources to communicate securely. It isolates resources from the public internet. Subnets, NSGs, and routing rules control connectivity. VNets provide a secure architecture for deploying cloud workloads.

Q2. How do you implement subnets and NSGs?
A2. I divide VNets into subnets based on environment or service. NSGs are applied to control inbound and outbound traffic. This ensures proper isolation between resources. Security is maintained without impacting connectivity.

Q3. What is VNet peering and why did you use it?
A3. VNet peering connects two VNets privately within or across regions. It allows secure communication between networks without using the public internet. Latency is minimal since traffic stays on Azure’s backbone. I used it to connect Dev and QA environments safely.

Q4. How do you connect on-premises networks with Azure VNet?
A4. I use VPN Gateway or ExpressRoute to establish a secure hybrid connection. Traffic is encrypted and routed privately. On-premises services can access cloud resources seamlessly. This enables a hybrid cloud setup securely.

Q5. How do you handle multiple environments in a VNet?
A5. I create separate subnets or VNets for Dev, QA, and Prod. NSGs and route tables enforce isolation between them. This prevents accidental access or interference. Each environment operates independently and securely.

Q6. How do you secure VNet resources?
A6. I use NSGs, Azure Firewall, private endpoints, and service endpoints. Only authorized resources can communicate. Logging and monitoring track access activity. Security is enforced and breaches are minimized.

Q7. How do you troubleshoot VNet connectivity issues?
A7. I check NSGs, route tables, and subnet configurations for misconfigurations. Network Watcher helps capture and analyze traffic. Alerts guide initial troubleshooting. This helps quickly restore connectivity.

---

## 7️⃣ Azure Key Vault

Q1. Why did you use Azure Key Vault?
A1. We used Key Vault to store all our secrets, like passwords, API keys, and certificates, so nothing sensitive was hardcoded. Applications accessed secrets securely using managed identities. This reduced risk of leaks. It also made rotating secrets easy without redeploying apps.

Q2. How do you rotate secrets in Key Vault?
A2. Secrets can be rotated manually or automatically using Key Vault policies. Applications always reference the latest version. Rotation prevents downtime. It also helps meet compliance requirements.

Q3. How do you control access to Key Vault?
A3. Use RBAC and access policies so users or services get only required permissions. Applications use managed identities to access secrets. Monitor access logs regularly. Ensures only authorized access occurs.

Q4. How is Key Vault integrated into CI/CD?
A4. Pipelines pull secrets at runtime instead of storing credentials in code. Jenkins or GitHub Actions can fetch them securely. Secret rotation doesn’t affect pipelines. This keeps deployments secure.

Q5. How do you handle certificates in Key Vault?
A5. Certificates are stored securely and can be auto-renewed. Applications retrieve them programmatically. Prevents manual errors and downtime. Alerts ensure timely renewals.

Q6. How do you monitor Key Vault usage?
A6. Enable logging in Azure Monitor to track access and operations. Alerts notify on unusual activity. Logs help auditing and troubleshooting. Security and compliance are maintained.

Q7. How do you integrate Key Vault with Azure services?
A7. Services like App Service, AKS, and Functions access Key Vault via managed identities. No secrets are stored locally. Centralized management improves security. Deployments remain simple and safe.

---

## 8️⃣ Azure Storage Account

Q1. What types of storage accounts have you used in Azure?
A1. Worked mainly with Blob, File, and Queue storage. Blob stores unstructured data, File shares configs, Queue manages messaging. Each serves specific workloads. Choosing correctly improves efficiency and cost.

Q2. How do you secure Azure Storage accounts?
A2. Use firewall rules, private endpoints, and SAS tokens. Encrypt data at rest and in transit. Only authorized services can access. Prevents accidental exposure.

Q3. How do you manage lifecycle and retention of storage data?
A3. Implement lifecycle policies to archive or delete old data. Automates cleanup and saves cost. Logs are rotated efficiently. Important data remains safe.

Q4. How do you integrate storage with applications?
A4. Access storage using Azure SDKs or REST APIs. Credentials stored securely in Key Vault or via managed identities. Supports dynamic scaling. Avoids hardcoding secrets.

Q5. How do you handle large files in storage?
A5. Use block blobs with parallel upload. Consider compression or chunking. Access via SAS tokens. Reliable storage without performance issues.

Q6. How do you monitor storage account usage?
A6. Use Azure Monitor metrics like request counts and errors. Alerts notify unusual activity. Logs analyzed for performance. Maintains reliability.

Q7. How do you handle storage account scaling?
A7. Use standard or premium tiers. Partition data if needed. Adjust resources based on traffic. Ensures performance and cost efficiency.

---

## 9️⃣ Azure Kubernetes Service (AKS)

Q1. How do you deploy applications in AKS?
A1. I use YAML manifests or Helm charts to define deployments, services, and configurations. Pipelines build Docker images and push to a registry. AKS pulls these images and runs pods automatically. This ensures repeatable and consistent deployments.

Q2. How do you handle scaling in AKS?
A2. I use Horizontal Pod Autoscaler to scale pods based on CPU, memory, or custom metrics. Cluster Autoscaler manages node scaling. This allows the app to handle traffic spikes. Scaling optimizes cost and performance.

Q3. How do you manage secrets in AKS?
A3. I store secrets in Kubernetes Secrets or integrate with Key Vault via CSI driver. Pods access secrets securely at runtime. This avoids hardcoding sensitive data. Rotation can be done without downtime.

Q4. How do you monitor AKS cluster health?
A4. Azure Monitor for containers and Prometheus/Grafana dashboards track performance. Alerts notify the team of failures or resource issues. Logs are collected for troubleshooting. This ensures high availability and performance.

Q5. How do you handle zero-downtime deployments?
A5. Rolling updates and canary deployments ensure new pods are healthy before routing traffic. Health probes verify readiness. Failed pods are rolled back automatically. Users experience uninterrupted service.

Q6. How do you manage multi-environment AKS clusters?
A6. Separate clusters or namespaces are maintained for Dev, QA, and Prod. Helm values or ConfigMaps provide environment-specific configs. Pipelines deploy to the appropriate environment. This ensures isolation and prevents interference.

Q7. How do you troubleshoot AKS issues?
A7. I check pod logs, events, and node status using `kubectl` and Azure Monitor. Network, RBAC, and resource quotas are reviewed. Alerts guide investigation. Quick diagnostics minimize downtime.

---

## 10️⃣ Azure Container Registry (ACR)

Q1. How do you secure ACR?
A1. Enable RBAC, use private endpoints, and scan images for vulnerabilities. Restrict who can push or pull images. Regular monitoring helps maintain security. This keeps the registry safe and compliant.

Q2. How do you manage Docker images in ACR?
A2. Tag each image properly and set retention policies for old images. Automate builds and pushes via CI/CD. Prevents registry clutter. Tagging also helps with rollbacks.

Q3. How do you integrate ACR with CI/CD pipelines?
A3. Pipelines push images to ACR after builds. AKS or other services pull images during deployments. This automates workflow from code to production. Reduces manual errors and speeds delivery.

Q4. How do you handle multi-environment registries?
A4. Separate repositories or tags per environment are used. CI/CD pipelines promote images across environments. Testing doesn’t affect production. Ensures environment isolation.

Q5. How do you scan images for vulnerabilities?
A5. Enable ACR image scanning or use tools like Trivy. Scans detect outdated packages or security issues. Alerts notify the team. Improves overall security posture.

Q6. How do you automate image cleanup in ACR?
A6. Retention policies delete untagged or old images automatically. Ensures storage efficiency. Pipelines maintain only relevant images. Registry remains organized and cost-effective.

Q7. How do you handle access for different teams?
A7. Assign roles via RBAC giving appropriate permissions. Regularly audit access. Use secure credential management. Ensures controlled and safe access.

---

## 11️⃣ Terraform

Q1. How do you use Terraform for Azure?
A1. Write `.tf` files to provision resources like VMs, VNets, AKS, ACR, and Key Vault. Terraform ensures repeatable deployments. Remote state in Azure Storage tracks changes. This makes infrastructure reliable and auditable.

Q2. How do you manage Terraform state?
A2. Use remote state with Azure Storage and enable locking. Prevents concurrent modifications. Tracks resource changes accurately. Allows safe collaboration.

Q3. How do you handle multiple environments in Terraform?
A3. Use workspaces or separate variable files for Dev, QA, and Prod. The same code can deploy safely across environments. Variables are environment-specific. Maintains isolation and consistency.

Q4. How do you integrate Terraform with CI/CD?
A4. Pipelines run `terraform plan` to preview and `terraform apply` to provision resources. Automates infrastructure deployment. Detects errors early. Keeps infrastructure in sync with code.

Q5. How do you manage secrets in Terraform?
A5. Sensitive values are stored in Key Vault or environment variables. Terraform references them at runtime. Avoids hardcoding credentials. Secrets can be rotated safely.

Q6. How do you handle Terraform versioning?
A6. Specify Terraform and provider versions in config files. CI/CD pipelines enforce versions. Avoids compatibility issues. Ensures consistent deployments.

Q7. How do you troubleshoot Terraform issues?
A7. Review plan outputs, state files, and provider logs. Common issues include resource conflicts or misconfigurations. Debugging identifies root causes. Testing prevents deployment failures.

