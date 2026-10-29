# HomeFinance for Home Assistant

Home Assistant app based on the multilingual fork:
https://github.com/immortalserg/HomeFinance

## Install

1. Ensure the package `ghcr.io/immortalserg/homefinance-ha` is public.
2. In Home Assistant open Settings -> Apps -> App repositories.
3. Add https://github.com/immortalserg/HomeFinance-HA.
4. Refresh the app store, install HomeFinance and start it.
5. Open the app at http://HOME_ASSISTANT_IP:8223.

## Persistent data

The SQLite database, uploads, documents, logs and generated secret keys
are stored in the app's persistent `/data` directory.

A fresh installation starts with a new database. Existing Docker data is
not migrated automatically. Back up the old database before any migration
and preserve the original SECRET_KEY and NOTIFICATION_ENCRYPTION_KEY.

## Releases

The `homefinance/config.yaml` version must match the Git tag.
Pushing `v1.0.0` builds and publishes the `1.0.0` and `latest` images for
linux/amd64 and linux/arm64.
