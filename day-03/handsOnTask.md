# 🔐 GCP IAM Fundamentals for Beginners 

## 🧭 What is IAM?

IAM (Identity and Access Management) in GCP is a framework that controls:
- **Who** can do **what** on **which resources**

Formula:
Who → Can do what → On which resource?

## 🧪 Hands-On Lab

### 🔧 Lab 1: Create Project & Assign Viewer Role

    export PROJECT_ID="devops-iam-demo-$(date +%s)"
    gcloud projects create $PROJECT_ID
    gcloud config set project $PROJECT_ID

    gcloud projects add-iam-policy-binding $PROJECT_ID \
      --member="user:devops.engineer@example.com" \
      --role="roles/viewer"

---

### 🔧 Lab 2: Create a Service Account & Grant Role

    gcloud iam service-accounts create devops-bot \
      --display-name="DevOps Pipeline Bot"

    gcloud projects add-iam-policy-binding $PROJECT_ID \
      --member="serviceAccount:devops-bot@$PROJECT_ID.iam.gserviceaccount.com" \
      --role="roles/cloudbuild.builds.editor"

---

## 📦 Real-World DevOps Scenario

**Use Case**:  
Your Cloud Build pipeline should deploy to GKE but NOT delete clusters.

**Solution**:
- Create a **Custom Role** with only `container.deployments.create`
- Assign that role to a **Service Account**
- Use that Service Account in your CI/CD pipeline

---