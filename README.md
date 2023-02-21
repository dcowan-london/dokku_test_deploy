# Deploy a Svelte app on Dokku with DroneCI

[![Build Status](https://droneci.fnukhosting.net/api/badges/dcowan/dokku_test_deploy/status.svg?ref=refs/heads/main)](https://droneci.fnukhosting.net/dcowan/dokku_test_deploy)

This repository is a test for deploying a Svelte app on [Dokku](https://dokku.com/) with DroneCI.

This is a simple Svelte+Vite template app (created with `npm init vite`). The only files that have been changed are:
* `README.md`
* `.drone.yml`
* `.static`

The pipeline connects to a [self-hosted Dokku server](https://dokku.com/docs/getting-started/installation/) over `ssh` via a local jump host. It configures the new app via the `dokku` CLI tool, deploys the app to Dokku via `git`, then requests a LetsEncrypt SSL certificate for the site.

The same pipeline should work with no modification for any static site generator which uses `npm build` to build the site. Dokku will look for the compiled site in `dist/`.

## GitHub
Note - GitHub is just a mirror for this repository. The main repository is at [https://git.fnukhosting.net/dcowan/dokku_test_deploy](https://git.fnukhosting.net/dcowan/dokku_test_deploy)