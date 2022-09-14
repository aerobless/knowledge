---
description: Google Cloud Platform
---

# 🌤 GCP

## Camp22 Stable-Diffusion Project

<figure><img src=".gitbook/assets/DeploymentDiagram (1).png" alt=""><figcaption></figcaption></figure>

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
