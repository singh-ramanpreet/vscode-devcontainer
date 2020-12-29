# Visual Studio Code Remote Development Containers

1. [Latex](#latex)

### References
`devcontainer.json`: https://code.visualstudio.com/docs/remote/devcontainerjson-reference

--------------------------------------------------

## Latex
Tag|Build|Size|Pulls|Stars|Docker Hub
---|---|---|---|---|---
[![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/singhramanpreet/vscode-devcontainers/latex-2020?logo=docker)](#) | [![GitHub Workflow Status](https://img.shields.io/github/workflow/status/singh-ramanpreet/vscode-devcontainers/DockerHub?logo=github)](#) | [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/singhramanpreet/vscode-devcontainers/latex-2020?logo=docker)](#) | [![Docker Pulls](https://img.shields.io/docker/pulls/singhramanpreet/vscode-devcontainers.svg?logo=docker)](#) | [![Docker Stars](https://img.shields.io/docker/stars/singhramanpreet/vscode-devcontainers?logo=docker)](#) | [vscode-devcontainers](https://hub.docker.com/r/singhramanpreet/vscode-devcontainers/)

### About Docker Image
   1. Built using `ubuntu` image.
   2. `doc`, `man`, `cache` removed.
   3. Basic tools installed `git`, `ssh`, etc.
   4. `texlive` installed with custom scheme (see `latex/Dockerfile`), without source and documentation.
      1. Only major `collection` not installed is `collection-fontsextra`, this `collection` adds about ~ 1.5 GB.
      2. Install project specific packages later with `tlmgr` (see `latex/devcontainer.json`).
   5. Image size about ~1.2 GB (docker-hub compressed size ~600 MB)

### Setup

```bash
```

--------------------------------------------------
