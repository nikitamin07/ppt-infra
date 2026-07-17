# ppt-infra
Infrastructure of ppt.by for Docker deploy


Copy .env.example file in root-directory, rename it to ".env", enter environment variables before deploy.

Command to deploy project for production on server:

docker compose up --build

`--build` still reuses Docker's layer cache — if a rebuild doesn't pick up your changes (stale `COPY . .` layer, common on Windows/WSL2 bind mounts), force a clean rebuild instead:

docker compose build --no-cache frontend
docker compose up -d --force-recreate frontend

(swap `frontend` for `backend`, or drop the service name to do both.)

To look backend PHP logs type:

docker compose -f docker-compose.dev.yml logs -f backend