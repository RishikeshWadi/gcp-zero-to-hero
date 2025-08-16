🚀 #Day4 of #GCPZeroToHero - GCP Compute Engine (VMs, SSH, Images & Firewall)

Hi Everyone! 
Today’s deep dive was all about Compute Engine service, GCP’s Infrastructure as a Service that lets you launch and manage virtual machines - the backbone of running scalable VMs in the cloud.

Here’s what I explored and practiced:
🔹 What is Compute Engine?
   • GCP’s IaaS for creating and running VMs.
   • Customizable w.r.t (CPU, RAM, OS, disk, networking).
   • Supports automation, startup scripts, auto-healing, and reusable custom images.

🔹 Key Concepts:
   • Instance = Your virtual server (VM)
   • Zone = A data center inside a region
   • Machine Type = Defines CPU & RAM (e.g., e2-micro, e2-small)
   • Boot Disk = Persistent storage with OS
   • Startup Script = Auto-run configuration when VM starts
   • Firewall Rule = Manages Inbound & Outbound traffic to/from VM

🔹 Hands-On Labs:
   ✅ Created and connected to a VM via SSH
   ✅ Installed and tested NGINX manually
   ✅ Automated NGINX setup using a startup script
   ✅ Enabled firewall rules to allow HTTP traffic
   ✅ Built a custom image and launched a new VM from it

🔹 Real-World DevOps Scenario 💡:
   • Automate provisioning with startup scripts
   • Enable secure & controlled access with firewall rules
   • Standardize deployments using custom images in CI/CD

✨ Key Takeaway: 
   • Compute Engine = scalable VMs on demand.
   • Automate everything (startup scripts, Terraform, CLI).
   • Always secure & standardize deployments.

Thanks to Abhishek Veeramalla for making the #GCPZeroToHero series and creating content that makes concepts simple and practical.

#DevOps #GoogleCloud #GCP #ComputeEngine #CloudComputing #Automation #GCPZeroToHero #Cloud #EC2 #Instance #VM #VirtualMachine