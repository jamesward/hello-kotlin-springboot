# Hello Kotlin Spring Boot

Run Locally:
```
./mvnw spring-boot:run
```

Deploy on Google Cloud Run:

[![Run on Google Cloud](https://deploy.cloud.run/button.svg)](https://deploy.cloud.run)

Local Docker Run:
```
./mvnw compile jib:build -Dimage=gcr.io/YOUR_GCR_PROJECT/hello-kotlin-springboot
docker run -it -ePORT=8080 -p8080:8080 gcr.io/YOUR_GCR_PROJECT/hello-kotlin-springboot
```
