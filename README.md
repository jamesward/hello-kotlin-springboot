# Hello Kotlin Spring Boot

Run Locally:
```
./mvnw spring-boot:run
```

Deploy on Google Cloud Run:

[![Run on Google Cloud](https://deploy.cloud.run/button.svg)](https://deploy.cloud.run)


Set GCP `PROJECT_ID`:
```
export PROJECT_ID=YOUR_GCR_PROJECT
```

Create a JVM Container Image:
```
./mvnw spring-boot:build-image -Dspring-boot.build-image.imageName=gcr.io/$PROJECT_ID/hello-kotlin-springboot
```

Or create a GraalVM Native Image Container Image:
```
./mvnw spring-boot:build-image -Pnative -Dspring-boot.build-image.imageName=gcr.io/$PROJECT_ID/hello-kotlin-springboot
```

Local Docker Run:
```
docker run -p8080:8080 gcr.io/$PROJECT_ID/hello-kotlin-springboot
```

Manually Deploy on Cloud Run:
```
docker push gcr.io/$PROJECT_ID/hello-kotlin-springboot

gcloud run deploy \
  --image=gcr.io/$PROJECT_ID/hello-kotlin-springboot \
  --memory=1Gi \
  --cpu=2. \
  --platform=managed \
  --allow-unauthenticated \
  --project=$PROJECT_ID \
  --region=us-central1 \
  hello-kotlin-springboot
```
