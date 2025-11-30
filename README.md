# CI/CD Demo with GitHub Actions and Google Cloud Run

This is a simple demo project showing how to build a **CI/CD pipeline** using **GitHub Actions** and **Google Cloud Platform (GCP)**.  
The application is a lightweight Python Flask web app that returns a "Hello from GCP CI/CD demo!" message. The CI/CD workflow is the focus of this project. 

---

## Overview
- **Language:** Python (Flask)
- **Containerization:** Docker
- **CI/CD Tool:** GitHub Actions
- **Deployment Target:** Google Cloud Run

---

## Repository Structure

gcp-github-workflow/ \
app.py --- # Flask app \
requirements.txt ---  # Python dependencies \
Dockerfile --- # Container build instructions \
.gitignore --- # Files Git should ignore \

.github/ \
workflows/ \
main.yml --- # CI/CD pipeline definition

---

## Prerequisites
### Installations and Accounts
 + Create GCP account w/ Free Credits
 + Create Github account
 + Install VS Code or have a text editor
 + Install Docker

 ### Enable GCP APIs 
+ Cloud Run
+ Cloud Storage
+ Cloud Build
+ Artifact Registry

### Create Service Account
 + Go to Service Accounts in GCP
 + Create new Service Account with Owner role
    + If Least Privilege policy is being used enable neccesary roles in IAM section
+ Download Secret Key in .json

### Create Github Repo
+ Create repo with desired name
+ Follow instructions to link remote repo to local directory

 ### Authenticate GItHub to GCP (GitHub Secrets Required)
 + Copy Project ID
 + Copy json key contents
 + Go to GitHub Settings > Secrets and Variables > Actions
 + Fill in Secrets variables
    + GCP_PROJECT_ID
    + GCP_SA_KEY

---

# Steps
### 1. Clone the Repository
```bash
git clone https://github.com/james-scales/gcp-github-workflow.git
```
```bash
cd gcp-github-workflow
```
### 2. Test Locally
``` bash 
pip install -r requirements.txt
```

``` bash
python app.py
```
### 3. Push Local Repo to GitHub

``` bash
git add <filename>
```
``` bash
git commit -m "Commit Text"
```
``` bash
git push
```
### 4. Configure GitHub Actions

+ GitHub > Actions
+ Select Setup workflow yourself
+ Use main.yaml contents and insert
+ Commit changes
+ Save

Note: Make sure all files are merged to repo.

### 5. Update app.py and push to Repo
+ Update text
    + "Hello from GCP CI/CD demo v2"
+ Push to repo
+ Observe updates in GitHub
+ Observe updates in GCP
    + Artifact Registry
    + Cloud Run
        + Use URL to view application output

