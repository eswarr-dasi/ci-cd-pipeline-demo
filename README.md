# 🔄 ci-cd-pipeline-demo

> **Project 7 of 10** · [30-Day Dev Roadmap](https://github.com/eswarr-dasi/dev-project-roadmap) · Jul 9, 2026
>
> A production-grade **GitHub Actions CI/CD pipeline** for a Spring Boot application. Covers the full
> pipeline: lint → test → Docker build → push to registry → deploy with environment promotion and
> branch protection rules.
>
> ---
>
> ## ✨ Pipeline Stages
>
> ```
> Pull Request
>   └── [CI] lint → unit-tests → integration-tests → SonarQube
>
> Merge to main
>   └── [CI]  lint → test → build JAR
>   └── [CD]  Docker build → push (staging tag)
>   └── [DEPLOY] deploy to staging
>
> Tag (v*.*.*)
>   └── [RELEASE] build → push Docker (latest + version) → production deploy
> ```
>
> ---
>
> ## ✨ Features
>
> - **PR quality gates** — Lint, test, and analysis block merges automatically
> - - **Multi-stage Docker builds** — Minimal production images
>   - - **Environment promotion** — staging → production with manual approval
>     - - **Branch protection** — `main` requires passing checks + 1 review
>       - - **Maven dependency caching** — Fast CI builds
>         - - **Matrix testing** — Java 17 and Java 21 in parallel
>           - - **Release automation** — GitHub Release on version tags
>            
>             - ---
>
> ## 🛠️ Tech Stack
>
> | Tool | Role |
> |------|------|
> | GitHub Actions | CI/CD orchestration |
> | Docker | Containerization |
> | Docker Hub | Image registry |
> | Maven | Build tool |
> | SonarQube | Code quality |
> | Spring Boot | Sample app |
>
> ---
>
> ## 📂 Structure
>
> ```
> .github/workflows/
> ├── ci.yml           # PR checks
> ├── cd-staging.yml   # Deploy staging on merge to main
> └── release.yml      # Production release on version tag
> Dockerfile
> docker-compose.yml
> src/                 # Spring Boot app
> ```
>
> ---
>
> ## 🚀 How to Use
>
> 1. Fork this repo
> 2. 2. Add secrets: `DOCKER_USERNAME`, `DOCKER_PASSWORD`
>    3. 3. Enable branch protection on `main`
>       4. 4. Open a PR — CI triggers automatically
>          5. 5. Merge → staging deploy runs
>             6. 6. Create a `v*.*.*` tag → production release runs
>               
>                7. ---
>               
>                8. ## 🎯 Career Relevance
>               
>                9. Converts my Concourse CI experience into GitHub Actions — the most widely used CI/CD platform today.
> Demonstrates containerization, environment promotion, and automated quality gates.
>
> ---
>
> ## 📅 Part of the 30-Day Dev Challenge
>
> See the full roadmap: [dev-project-roadmap](https://github.com/eswarr-dasi/dev-project-roadmap)
>
> *Built by [Eswarr Dasi](https://github.com/eswarr-dasi) · Jul 2026*
