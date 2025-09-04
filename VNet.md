VNet
 In our project, security and proper communication between services were very important. That’s where Azure Virtual Network (VNet) came in.

I set up a dedicated VNet to make sure all our Azure resources—like VMs, Kubernetes clusters, and storage accounts—could communicate securely with each other, instead of being exposed to the public internet.

To keep things organized, I divided the VNet into subnets. For example, we had one subnet for application servers, another for databases, and one more for the jump server. This separation made sure that traffic was controlled and services only talked to what they needed to.

On top of that, I applied Network Security Groups (NSGs). These worked like firewall rules. I configured inbound rules so that only specific ports like 22 (SSH) or 3389 (RDP) were open to trusted admin IPs, and outbound rules so the servers could only reach the internet when necessary.

For extra security, I also enabled service endpoints and private links. This allowed resources like Storage Accounts and Key Vault to be accessed privately through the VNet instead of going over the internet. 

That way, sensitive data never left the secure boundary of our network.
Finally, to connect our on-premises environment with the cloud, I set up a VPN Gateway. This made sure that our internal users could securely connect to Azure resources as if they were part of the same internal network.

In short, the VNet acted like the backbone of our entire Azure setup. It gave us control over traffic flow, security boundaries, and private access—making the whole environment secure and well-structured.
