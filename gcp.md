---
description: Google Cloud Platform
---

# 🌤 GCP

## Camp22 Stable-Diffusion Project

<figure><img src=".gitbook/assets/DeploymentDiagram (2).png" alt=""><figcaption><p>GCP deployment diagram</p></figcaption></figure>

### Cloud Compute

**Machine Type**: n1-standard-4, 4 vCPU, 15GB memory, Nvidia Tesla T4 GPU

**Details**: [Stable Diffusion Dream Fork](https://github.com/lstein/stable-diffusion/) on Linux

### Cloud Run

**Machine Type**: 1GB memory, 1 vCPU, 0-4 instance, running a docker container

**Details**: Cloud Run runs our spring boot backend connecting between the flutter app and the stable diffusion image generator. The backend has a database that saves the prompt and some other image metadata to be served to the frontend.

### Cloud SQL

**Machine Type**: PostgreSQL 14.4, 1vCPU, 3.75GB memory, 100GB storage

**Details**: We use a managed Postgres database to store image metadata such as the prompt, seed, user that created the image and whether they chose to publish it.

### Artifact Registry

**Details**: Artifact registry is used to provide a docker registry for our backend. Docker images are built and published to the repository via GitHub actions.

## Notes

*   [See Compute Engine Startup Script Output: ](https://cloud.google.com/compute/docs/instances/startup-scripts/linux#viewing-output)

    ```
    sudo journalctl -u google-startup-scripts.service
    ```
* [Nohup](https://linuxhint.com/how\_to\_use\_nohup\_linux/): Keep application running in background even when disconnected: `nohup CMD &`
* [Export GCP project as terraform infrastructure as code (IAC)](https://cloud.google.com/docs/terraform/resource-management/export)
* [Deploy dockerized application via GitHub Action to Google Cloud Run](https://cloud.google.com/community/tutorials/cicd-cloud-run-github-actions)

<pre class="language-yaml"><code class="lang-yaml"><strong>name: Build spring boot backend
</strong>
on:
  push:
    paths:
      - backends/spring-backend/**
      - .github/**

jobs:

  deploy:

    name: Setup Gcloud Account
    runs-on: ubuntu-latest
    env:
      IMAGE_NAME: gcr.io/${{ secrets.GCP_PROJECT_ID }}/camp-22-stable-diffusion
    steps:

      - name: Login
          uses: google-github-actions/setup-gcloud@v0
          with:
            project_id: ${{ secrets.GCP_PROJECT_ID }}
            service_account_email: ${{ secrets.GCP_EMAIL }}
            service_account_key: ${{ secrets.GCP_CREDENTIALS }}

      - name: Configure Docker
        run: gcloud auth configure-docker --quiet

      - name: Checkout repository
        uses: actions/checkout@v2

      - uses: actions/setup-java@v3
        with:
          distribution: 'temurin' # See 'Supported distributions' for available options
          java-version: '17'

      - name: Setup Gradle
        uses: gradle/gradle-build-action@v2

      - name: Execute Gradle build
        working-directory: backends/spring-backend
        run: ./gradlew bootJar

      - name: Build Docker image
        working-directory: backends/spring-backend
        run: docker build --build-arg JAR_FILE=build/libs/\*.jar . -t $IMAGE_NAME

 #     - name: Test Docker image
 #       run: docker run $IMAGE_NAME sh -c "go test -v"

      - name: Push Docker image
        run: docker push $IMAGE_NAME

      - name: Deploy Docker image
        run: gcloud run deploy ${{ secrets.GCP_PROJECT_ID }} --image $IMAGE_NAME --region us-central1 --platform managed</code></pre>
