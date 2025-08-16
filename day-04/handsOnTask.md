# 💻 Day-4: Compute Engine in GCP (VMs, SSH, Images, Firewall)

## 🎯 Goal
To learn how to provision virtual machines in GCP, access them securely, run startup automation, install software like NGINX, and create reusable custom images — all through a DevOps lens.

---

##  Hands-On Lab

### 🛠️ Launch a VM and Connect via SSH

    gcloud compute instances create first-vm-devops \
      --zone=asia-south1-a \
      --machine-type=e2-micro \
      --image-family=ubuntu-2004-lts \
      --image-project=ubuntu-os-cloud \
      --tags=http-server

    # SSH into the instance
    gcloud compute ssh first-vm-devops --zone=asia-south1-a

---

### 🛠️ Manually Install NGINX on Ubuntu VM

Once inside the VM via SSH, run the following:

    sudo apt update
    sudo apt install -y nginx
    sudo systemctl enable nginx
    sudo systemctl start nginx

### To test:

    curl http://localhost

---


### 🛠️ Install NGINX Automatically via Startup Script

    gcloud compute instances create nginx-vm-instance \
      --zone=asia-south1-a \
      --machine-type=e2-micro \
      --image-family=ubuntu-2004-lts \
      --image-project=ubuntu-os-cloud \
      --metadata startup-script='#! /bin/bash
    apt update
    apt install -y nginx
    systemctl enable nginx
    systemctl start nginx' \
      --tags=http-server

---

### 🛠️ Enable Firewall Rule for HTTP Access

    gcloud compute firewall-rules create allow-http \
      --allow tcp:80 \
      --target-tags=http-server \
      --description="Allow HTTP traffic" \
      --direction=INGRESS \
      --priority=1000 \
      --network=default

---

### 🛠️ Create a Custom Image from Existing VM

    # Stop the VM before creating image
    gcloud compute instances stop nginx-vm-instance --zone=asia-south1-a

    # Create image from disk
    gcloud compute images create nginx-custom-image \
      --source-disk=nginx-vm \
      --source-disk-zone=asia-south1-a

    # Launch a new VM from custom image
    gcloud compute instances create nginx-from-image \
      --zone=asia-south1-a \
      --machine-type=e2-micro \
      --image=nginx-custom-image \
      --tags=http-server

---

## 🧠 Real-World DevOps Use Case

> You want to:
> - Automatically install NGINX during VM creation
> - Expose the app to the internet
> - Reuse that base image in CI/CD pipelines

✅ Use **startup scripts** for provisioning  
✅ Enable **firewall rules** for public access  
✅ Use **custom images** to standardize deployments

---