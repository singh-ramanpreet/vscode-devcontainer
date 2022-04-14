# Visual Studio Code Remote Development Containers
[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/singh-ramanpreet/vscode-devcontainers/DockerHub?logo=github)](#) [![Docker Pulls](https://img.shields.io/docker/pulls/singhramanpreet/vscode-devcontainers.svg?logo=docker)](#) [![Docker Stars](https://img.shields.io/docker/stars/singhramanpreet/vscode-devcontainers?logo=docker)](#)

1. [Latex](#latex)
2. [Data Science](#data-science)

### References
`devcontainer.json`: https://code.visualstudio.com/docs/remote/devcontainerjson-reference

### Setup
   1. Get template `devcontainer.json` from corresponnding directory.
   2. Open directory/workspace in `vscode`, if you have `vscode` remote container extension installed, it will prompt you to re-open workspace in container or you can give command `reopen in container`.
   3. If you change `devcontainer.json` you will have to do `rebuild and reopen in container` for changes to take effect.
 
--------------------------------------------------

## Latex
[Versions](latex/README.md)

### About Docker Image
   1. Built using `ubuntu` image.
   2. `doc`, `man`, `cache` removed.
   3. Basic tools installed `git`, `ssh`, etc.
   4. `texlive` installed with custom scheme (see `latex/Dockerfile`), without source and documentation.
      1. Only major `collection` not installed is `collection-fontsextra`, this `collection` adds about ~ 1.5 GB.
      2. Install project specific packages later with `tlmgr` (see `latex/devcontainer.json`).
   5. Image size about ~1.2 GB (docker-hub compressed size ~600 MB)

### Get template
   
   ```bash
   # from latex project dir
   curl https://raw.githubusercontent.com/singh-ramanpreet/vscode-devcontainers/main/latex/devcontainer.json \
   --create-dirs -o .devcontainer/devcontainer.json
   ```

--------------------------------------------------

## Data Science
[Versions](data-science/README.md)

### About Docker Image

### Get template

   ```bash
   # from latex project dir
   curl https://raw.githubusercontent.com/singh-ramanpreet/vscode-devcontainers/main/data-science/devcontainer.json \
   --create-dirs -o .devcontainer/devcontainer.json
   ```
--------------------------------------------------
