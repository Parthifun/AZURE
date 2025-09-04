Azure Key Vault 
 In our provect, we were dealing with sensitive information - thing like database connetion stings, ARI Kays & certificates. At finst, some of these were being stored in contiguration files or shaved manually among develapers. Relying an manually stored crendentials loos, risky, because if even one password or key got enposed, it could put the entire sustern at risk. To solve this, we started using Azurekk, which allowed us to securely stone & Centrally manage all our secets E Keys & Certification.
 
As devops Engineer, I was responsible for seting up & manging key Vout acoss all environments. I created separate loults of for devlopment team, qA, & production to Keep things isolated a secure. Them, l set up access policies & RBAC So that each team member, application, or pipeline anly bad access to He secrets they needed - nothing more.

The real power come when I started integrating Key vault with our infrastructure. For en; our applications that rar, on VMs & Kuberetes used Managed Identities, so they didn't even need to store credentials. Whenever they needed a secret, they just called the key vault securely & got it at runtine. The some piled to our cI/CD pipelines in Azure Devaps - I made sure the pipelines could fetch secrets from KV ding deplayment instead of bawing deveropers manually pass in passwords.

