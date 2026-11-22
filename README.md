# apps.jsie.de

Home Assistant app repository for the apps.jsie.de platform.
This repository contains deployment manifests and documentation only.
Application source and container images are private.

[![Add repository to Home Assistant](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Ftherealjsie%2Fapps.jsie.de)

## Install

1. Add `https://github.com/therealjsie/apps.jsie.de` under Settings → Apps →
   Install app → ⋮ → Repositories. Use this exact URL without a trailing slash,
   `.git`, or branch suffix to keep the repository identity stable.
2. In the app store's Registries menu, configure `ghcr.io` with your GitHub
   username and a dedicated classic token with `read:packages`. The account
   must have permission to read the private images.
3. Install **Apps PostgreSQL**, set three distinct passwords of at least
   20 characters, and start it.
4. Install **Apps Backend** and set the Cloudflare Access team domain, audience,
   and the two matching service database passwords. Its database hostname
   defaults to `43f3da93-apps-postgres`.
5. Stop any previous server using host port 8090 before starting this backend.
   Verify it through Cloudflare Access, then route `apps.jsie.de` to port 8090.
   Keep the Home Assistant tunnel route unchanged.

## Updates

Successful stable releases publish the private images first, then update these
manifests. Home Assistant discovers changes when its app store refreshes.
Enable automatic updates for Apps Backend if desired. Keep PostgreSQL updates
manually approved, with a backup before upgrading.

Adding this repository does not automatically update or replace an existing
local app. Repository-installed apps have a different identity and separate
persistent data/options. If PostgreSQL was already installed locally, back up
and restore its data into the new installation and copy credentials/options
before switching. Do not run both backends on port 8090 simultaneously.

Do not put passwords or tokens into files in this public repository.
