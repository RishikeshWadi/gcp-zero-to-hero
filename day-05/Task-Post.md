#Day 5 of #GCPZeroToHero series – GCP Storage Service 

📝 Here’s a breakdown of the services:
	🔹 Cloud Storage (GCS) -> Stores data/files as objects in buckets - perfect for logs, backups, artifacts and media.
	🔹 Filestore -> Provides a managed NFS file system for shared access across workloads.
	🔹 Bigtable -> Scalable, wide-column NoSQL database designed for large datasets and time-series data.
	🔹 Pub/Sub -> Messaging system for real-time Event -Driven messaging and microservice communication.
	🔹 Local SSDs -> High-speed, temporary block storage directly connected to VM hosts.

Cloud storage is the backbone of modern applications. When it comes to storing data at scale, Google Cloud Storage (GCS) stands out as a simple, secure, durable, and highly available solution (similar to AWS S3 & Azure Blob).

🔑 Key Features of GCS:
	🔹 Object Storage - Stores unstructured data like logs, media, and build artifacts.
	🔹 Durability & Security - Encryption by default - Data is Safe, and fine-grained roles & service accounts.
	🔹 Availability & Storage Classes - Standard, Nearline, Coldline, Archive – to optimize cost and access frequency.
	🔹 Regions & Multi-Regions - Choose Region, Multi-Region Storage for performance and availability.
	🔹 Cost Efficiency – Pay-as-you-go with lifecycle policies to optimize costs automatically.
	🔹 DevOps Ready - store CI/CD artifacts, host static content, manage logs, and power analytics pipelines.

🖥️ Hands-On: Google Cloud Storage + Compute Engine VM

In my demo, I integrated a Compute Engine VM with Cloud Storage.

📝 Steps I followed: [ ]
 1️⃣ Created a Cloud Storage Bucket
 2️⃣ Configured a Service Account with Storage Object Admin role
 3️⃣ Launched a VM with the Service Account attached
 4️⃣ Read & wrote files between the VM and GCS bucket
 5️⃣ Cleaned up resources to avoid charges

👉Takeaways:

	Cloud Storage is more than just "saving files or data" — it’s about security, scalability, and integration into real-world workflows.

Thanks to Abhishek Veeramalla for making the #GCPZeroToHero series and creating content that makes concepts simple and practical.

#GoogleCloud #GCP #CloudStorage #Day5 #AKVA #LearningJourney #ComputeEngine #CloudComputing #HandsOnLearning #DevOps #CloudSecurity #GCPZeroToHero #IAM #Role #Principal #SA #ServiceAccount #GCS #FileStore #Bigtable #PubSub #Bucket #Objects #CICD #Security #Region 