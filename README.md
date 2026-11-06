# alacarte-builds

Nightly container builds of [alacarte](https://github.com/norifm/alacarte), an Apple Music downloader. Upstream publishes no images, so this repo's [workflow](.github/workflows/build.yml) checks out `norifm/alacarte` at `main` every night (and on manual dispatch), builds two amd64 images, and pushes them to GitHub Container Registry:

- `ghcr.io/adam-fox/alacarte-wrapper:latest`, built from `./wrapper`
- `ghcr.io/adam-fox/alacarte-web:latest`, built from `backend/Dockerfile` with the repo root as context

Nothing from upstream is modified. The images are used on Unraid through two user templates.
