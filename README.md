# website

[![CI](https://github.com/MuskaanDhanda/website/actions/workflows/ci.yml/badge.svg)](https://github.com/MuskaanDhanda/website/actions/workflows/ci.yml)

Sample static website used as the application in [DevOps Capstone Project 1](https://github.com/MuskaanDhanda/devops-capstone-project-1). Forked from [hshar/website](https://github.com/hshar/website).

## What's inside

| File | Purpose |
|------|---------|
| `index.html` | The web page served by Apache |
| `images/` | Background image for the page |
| `Dockerfile` | Builds an Ubuntu + Apache2 image and copies the site into `/var/www/html` |

## Branches

- `master` — production branch. A commit here triggers the Jenkins build → test → prod jobs.
- `develop` — a commit here is built and tested only, never pushed to prod.

## Run it locally

```bash
docker build . -t website
docker run -d -p 81:80 --name c1 website
# open http://localhost:81
```

## CI

GitHub Actions lints the Dockerfile with hadolint, builds the image, starts a container and checks that the page is served.
