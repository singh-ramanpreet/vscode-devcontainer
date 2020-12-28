# Visual Studio Code Remote Development Containers

1. [Latex](#latex)

## Latex
---------
### About Docker Image
   1. Built using `ubuntu` image.
   2. `doc`, `man`, `cache` removed.
   3. Basic tools installed `git`, `ssh`, etc.
   4. `texlive` installed with custom scheme (see `latex/Dockerfile`), without source and documentation.
      1. Only major `collection` not installed is `collection-fontsextra`, this `collection` adds about ~ 1.5 GB.
      2. Install project specific packages later with `tlmgr` (see `latex/devcontainer.json`).
   5. Image size about ~1.2 GB (docker-hub compressed size ~600 MB)

### Setup

### References
`devcontainer.json`: https://code.visualstudio.com/docs/remote/devcontainerjson-reference
