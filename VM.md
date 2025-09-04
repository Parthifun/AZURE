VM’s
 In our project, we had a mix of modern applications and some legacy workloads that couldn’t run on containers or serverless platforms. One of my main responsibilities was managing Azure Virtual Machines to support these workloads.

For instance, we had a legacy reporting service that generated daily sales and analytics reports. I deployed this service on a Windows VM and configured it to run automatically every night using Task Scheduler. This ensured that the reports were ready every morning without any manual intervention.

We also needed a secure way to access internal servers. So, I set up a Linux VM as a jump server which allowed our team to connect to other VMs safely without exposing them to the public internet.

Security was very important for our VMs. I placed all of them inside a Virtual Network and applied Network Security Groups. This meant that only specific admin IPs could access the VMs through RDP for Windows and SSH for Linux. I also integrated Azure Key Vault to securely manage credentials, ensuring no sensitive information was stored directly on the VMs.

I kept the VMs reliable by setting up monitoring and alerts in Azure Monitor, so we were notified right away if there were any performance issues or failures. I also took care of patching and updates to keep the systems secure, and I configured Azure Backup to create regular backups. That way, the VMs were always secure and could be quickly restored if something went wrong.

Lastly, these VMs weren’t working in isolation. They were connected with other Azure services, like Storage Accounts, where they accessed or processed large datasets for reports.

Overall, managing these VMs was like being the caretaker of a small, critical ecosystem. I made sure they were secure, reliable, and always ready to support the project’s workloads, which was crucial for keeping our operations smooth.
