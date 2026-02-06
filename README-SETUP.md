Local setup (Windows with Docker)

Prerequisites
- Docker Desktop (WSL2 recommended) or a Linux host with Docker
- Optional: pnpm and Node.js if you want to build outside Docker

Quick start (Docker)
1. Build the image:

```powershell
cd <repo-root>
.
# from repo root
docker build -t simple-ecom-deploy ./build-template
```

2. Run the container (interactive):

```powershell
docker run --rm -it -p 8000:8000 -p 6188:6188 simple-ecom-deploy
```

3. Or use the provided helper (PowerShell):

```powershell
# from repo root
powershell -ExecutionPolicy Bypass -File .\scripts\setup-local.ps1
# or detached
powershell -ExecutionPolicy Bypass -File .\scripts\setup-local.ps1 -Detach
```

What the container does
- Starts a local ICP network via `icp network start -d`
- Creates canisters for `frontend` and `backend`
- Deploys canisters using `icp deploy --environment local frontend backend`
- Keeps running until you Ctrl+C (so local Identity/II and storage gateway stay up)

Native (without Docker)
- Install Node.js, pnpm, icp-cli, and mops per `build-template/Dockerfile` to match versions
- Then run:

```bash
bash build-template/deploy.sh
```

CI/CD notes
- See `.github/workflows/ci-deploy.yml` for a workflow that builds the Docker image and can push to a registry when secrets are configured.

Next steps I can take for you
- Run the local Docker setup now (requires Docker installed on your machine)
- Add a GitHub Actions job to run `icp deploy` inside the image (requires secrets)
- Prepare a step-by-step production deploy guide for ICP mainnet

