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
docker-compose --env-file config.env up -d --build
```

## Starting the MLflow UI
`localhost:5000`

## Starting The MinIO console
`localhost:9001`