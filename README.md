# mlflow-docker


## Environment Variables

```
# Postgres configuration
PG_USER=XXXX
PG_PASSWORD=XXXX
PG_DATABASE=XXXX
PG_PORT=5432

# MLflow configuration
MLFLOW_PORT=5000
MLFLOW_BUCKET_NAME=XXXX

# MinIO access keys - these are needed by MLflow
MINIO_ACCESS_KEY=XXXX
MINIO_SECRET_ACCESS_KEY=XXXX

# MinIO configuration
MINIO_ROOT_USER: XXXX
MINIO_ROOT_PASSWORD: XXXX
MINIO_ADDRESS: ':9000'
MINIO_STORAGE_USE_HTTPS: False
MINIO_CONSOLE_ADDRESS: ':9001'
MINIO_PORT=XXXX
MINIO_CONSOLE_PORT=XXXX
```

## How to run
```
# Log in to the ACR
az acr login --name myContainerRegistry

# Build the images
docker-compose build

# Tag the images with the ACR URL
docker tag mlflow_server myContainerRegistry.azurecr.io/mlflow_server:latest
docker tag postgres myContainerRegistry.azurecr.io/mlflow_db:latest
docker tag minio/minio myContainerRegistry.azurecr.io/mlflow_minio:latest

# Push Images to Azure Container Registry
docker push myContainerRegistry.azurecr.io/mlflow_server:latest
docker push myContainerRegistry.azurecr.io/mlflow_db:latest
docker push myContainerRegistry.azurecr.io/mlflow_minio:latest
```

## Starting the MLflow UI
`localhost:5000`

## Starting The MinIO console
`localhost:9001`