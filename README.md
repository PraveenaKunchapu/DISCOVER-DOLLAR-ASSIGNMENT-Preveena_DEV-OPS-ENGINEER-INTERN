# Discover Dollar Assignment --- Image Build & Push (Frontend + Backend)

**Frontend Repository:** https://github.com/PraveenaKunchapu/DISCOVER-DOLLAR-Praveena_ASSIGNMENT_frotnend\
**Backend Repository:** https://github.com/PraveenaKunchapu/DISCOVER-DOLLAR-Praveena_ASSIGNMENT_backend

------------------------------------------------------------------------

## 🚀 Overview

This project demonstrates a complete CI/CD workflow for building and
pushing Docker images for both **Frontend** and **Backend** applications
using **GitHub Actions**.

The workflow securely authenticates to Docker Hub, builds images on
every push to the `main` branch, and pushes them to two Docker
repositories.

------------------------------------------------------------------------

## 🧩 Steps Followed (Frontend & Backend)

### 1️⃣ **Created Dockerfiles**

Both repositories contain Dockerfiles defining how to build the
respective application images.

------------------------------------------------------------------------

### 2️⃣ **Added GitHub Actions Workflow**

Files created in each repository under:

    .github/workflows/docker-image.yml

The workflow:

-   Checks out repo\
-   Sets up Node (frontend) or Python/other runtime (backend if
    required)\
-   Builds Docker image\
-   Logs into Docker Hub using encrypted GitHub Secrets\
-   Pushes image to Docker Hub

------------------------------------------------------------------------

### 3️⃣ **Docker Hub Repositories**

Two separate repositories in Docker Hub:

  Service    Image Name
  ---------- --------------------------------------------------
  Frontend   `kunchapupraveena/discover_dollar-assignment-fe`
  Backend    `kunchapupraveena/discover_dollar-assignment-be`

------------------------------------------------------------------------

## 🔐 Authentication to GitHub (Secure Setup)

### GitHub Secrets Used:

-   `DOCKERHUB_USERNAME`
-   `DOCKERHUB_TOKEN` (Access Token --- safer than password)

These secrets were added under:

    GitHub Repo → Settings → Secrets & Variables → Actions → New Repository Secret

Secrets were injected inside workflow as:

``` yaml
username: ${{ secrets.DOCKERHUB_USERNAME }}
password: ${{ secrets.DOCKERHUB_TOKEN }}
```

This is the security best practice recommended by GitHub.

------------------------------------------------------------------------

## 🛠️ Build & Push Commands (GitHub Actions)

### Frontend Build:

    docker build -t kunchapupraveena/discover_dollar-assignment-fe:latest .
    docker push kunchapupraveena/discover_dollar-assignment-fe:latest

### Backend Build:

    docker build -t kunchapupraveena/discover_dollar-assignment-be:latest .
    docker push kunchapupraveena/discover_dollar-assignment-be:latest

------------------------------------------------------------------------

## 🛡️ Best Practices Followed

### ✔️ Secrets stored in GitHub Secrets (Never in repo)

### ✔️ Immutable build process using GitHub Actions

### ✔️ Docker Hub Access Token used (not password)

### ✔️ Tags can be dynamically generated for CI/CD

### ✔️ Minimal actions workflow for cleaner & faster execution

### ✔️ Separate images for frontend & backend for modular deployment

------------------------------------------------------------------------

## 📌 Final Notes

This README acts as a documentation reference for anyone trying to
understand how Docker-based CI/CD is handled using GitHub Actions in
this project.

------------------------------------------------------------------------
