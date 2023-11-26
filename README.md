# Deployment Guide for App Engine

This brief guide will assist you in deploying our microservices to App Engine. It is unnecessary to repeat the Requirements and Initial Setup sections for each microservice.

## Requirements

Before starting, ensure the following is installed:
- Google Cloud SDK (gcloud CLI): For step-by-step instructions, follow the [installation guide](https://cloud.google.com/sdk/docs/installing).

## Initial Setup

After installing the gcloud CLI, authenticate and configure your project:

1. Initialize gcloud:

   ```sh
   gcloud init
   ```

2. Authenticate using the on-screen instructions and your Google account.

3. Choose the project you want to work on from the gcloud tool's provided list.

## Deployment

Execute the following command to deploy the User Management service to production:

```sh
gcloud app deploy ./app.yaml
```

Before executing the command, ensure you're in the directory containing the `app.yaml` file. This action will start the deployment of your application to Google App Engine.

Proceed with these steps:

```sh
cp app.example.yml app.yml
```

Then, update the `.env` section with your specific values.

For more detailed information on deployment, visit the [App Engine Deployment Guide](https://cloud.google.com/appengine/docs/standard/python3/deploying).
