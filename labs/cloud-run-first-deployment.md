# Lab 01: Deploy a Container to Cloud Run

## Objective

Deploy a containerized web application to Google Cloud Run, a managed service for running containers without managing servers.

## Prerequisites

- A Google Cloud account and project
- Billing enabled for the project
- Google Cloud CLI (`gcloud`) installed
- A sample container application (or use the Cloud Run quickstart sample)

## 1. Set the project

Replace `PROJECT_ID` with your Google Cloud project ID:

```bash
gcloud config set project PROJECT_ID
```

Check the active configuration:

```bash
gcloud config get-value project
```

## 2. Enable Cloud Run

```bash
gcloud services enable run.googleapis.com
```

## 3. Deploy a sample service

Deploy the official sample container:

```bash
gcloud run deploy hello   --image us-docker.pkg.dev/cloudrun/container/hello   --region us-central1   --allow-unauthenticated
```

When prompted, confirm the deployment and public access if appropriate for this demo.

## 4. Verify

The deployment command prints a service URL. Open it in a browser and verify that the sample page loads.

Check the service:

```bash
gcloud run services describe hello --region us-central1
```

## 5. Clean up

Delete the service when finished to avoid potential ongoing charges:

```bash
gcloud run services delete hello --region us-central1
```

Review your project and billing dashboard for any remaining resources.

## What I learned

- Cloud Run deploys containers as managed services.
- A service URL is provided after deployment.
- IAM and public-access settings affect who can reach a service.
- Deleting unused resources is an important part of cloud cost management.

> This is a practice lab. Review current Google Cloud pricing and permissions before deploying.
