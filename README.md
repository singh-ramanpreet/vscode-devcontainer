# Visual Studio Code Remote Development Containers
[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/singh-ramanpreet/vscode-devcontainers/DockerHub?logo=github)](#) [![Docker Pulls](https://img.shields.io/docker/pulls/singhramanpreet/vscode-devcontainers.svg?logo=docker)](#) [![Docker Stars](https://img.shields.io/docker/stars/singhramanpreet/vscode-devcontainers?logo=docker)](#)

1. [Latex](#latex)

### References
`devcontainer.json`: https://code.visualstudio.com/docs/remote/devcontainerjson-reference

--------------------------------------------------

## Latex
Tag  | Status 
 --- | ---    
`latex` -> `latex-2021-0.2`
[`latex-2021-0.2`](https://github.com/singh-ramanpreet/vscode-devcontainers/blob/latex-2021-0.2/latex/Dockerfile) | [![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/singhramanpreet/vscode-devcontainers/latex-2021-0.2?logo=docker)](#) [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/singhramanpreet/vscode-devcontainers/latex-2021-0.2?logo=docker)](#)
[`latex-2021-0.1`](https://github.com/singh-ramanpreet/vscode-devcontainers/blob/latex-2021-0.1/latex/Dockerfile) | [![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/singhramanpreet/vscode-devcontainers/latex-2021-0.1?logo=docker)](#) [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/singhramanpreet/vscode-devcontainers/latex-2021-0.1?logo=docker)](#)
[`latex-2020-final`](https://github.com/singh-ramanpreet/vscode-devcontainers/blob/latex-2020-final/latex/Dockerfile) | [![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/singhramanpreet/vscode-devcontainers/latex-2020-final?logo=docker)](#) [![Docker Image Size (tag)](https://img.shields.io/docker/image-size/singhramanpreet/vscode-devcontainers/latex-2020-final?logo=docker)](#)
[`latex-2020-0.1`](https://github.com/singh-ramanpreet/vscode-devcontainers/blob/latex-2020-0.1/latex/Dockerfile) | Deleted

### About Docker Image
   1. Built using `ubuntu` image.
   2. `doc`, `man`, `cache` removed.
   3. Basic tools installed `git`, `ssh`, etc.
   4. `texlive` installed with custom scheme (see `latex/Dockerfile`), without source and documentation.
      1. Only major `collection` not installed is `collection-fontsextra`, this `collection` adds about ~ 1.5 GB.
      2. Install project specific packages later with `tlmgr` (see `latex/devcontainer.json`).
   5. Image size about ~1.2 GB (docker-hub compressed size ~600 MB)

### Setup

   1. Get template, run from `latex` project directory

   ```bash
   # from latex project dir
   curl https://raw.githubusercontent.com/singh-ramanpreet/vscode-devcontainers/main/latex/devcontainer.json \
   --create-dirs -o .devcontainer/devcontainer.json
   ```

   2. Open `latex` directory/workspace in `vscode`, if you have `vscode` remote container extension installed, it will prompt you to re-open workspace in container or you can give command `reopen in container`.
   3. If you change `devcontainer.json` you will to do `rebuild and reopen in container` for changes to take effect.

--------------------------------------------------
