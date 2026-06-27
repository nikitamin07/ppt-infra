# ppt-infra
Infrastructure of ppt.by for Docker deploy


Copy .env.example file in root-directory, rename it to ".env", enter environment variables before deploy.

Command to deploy project locally for developing:
docker compose -f docker-compose.dev.yml up --build

Command to deploy project for production on server:
docker compose up --build

To look backend PHP logs type:
docker compose -f docker-compose.dev.yml logs -f backend