<!-- TITLE: Devops -->
<!-- SUBTITLE: General Dev Ops Notes -->

# General Dev Ops Notes

## Deploying this Wiki
The Thirstie Engineering Wiki uses [Wiki.js](https://wiki.js.org) as a front-end, deployed via docker to a DigitalOcean droplet. Wiki.js is configured for federated user authentication via Google ID, and uses GitHub as a backing store for the individual pages. Building and deploying is done via a Jenkins task, which interpolates environment variables into configuration templates before uploading the docker compose configuration to the droplet.

All of the configuration is stored in the main branch [of the Wiki Repository](https://github.com/ThirstieAdmin/memoryhole). Content is stored in the [wiki branch of the repository](https://github.com/ThirstieAdmin/memoryhole/tree/wiki).
