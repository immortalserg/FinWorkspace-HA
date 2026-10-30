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

All application state is stored in the app's persistent `/data` directory:

- SQLite database (`finance.db`).
- Uploads, documents and logs.
- Generated `SECRET_KEY` and `NOTIFICATION_ENCRYPTION_KEY`.
- Admin application settings (`app-settings.json`).
- Encrypted admin secrets (`app-secrets.json`) and their encryption key
  (`app-settings.key`).
- The Enable Banking private key under `secrets/enablebanking.pem`.

Back up the entire `/data` directory. In particular, keep
`app-settings.key` together with `app-secrets.json`; encrypted secrets
cannot be recovered if their matching key is lost.

A fresh installation starts with a new database. Existing Docker data is
not migrated automatically. Before migrating from Docker, back up the old
database and preserve the original `SECRET_KEY` and
`NOTIFICATION_ENCRYPTION_KEY`.

## Releases

The `homefinance/config.yaml` version must match the Git tag without its
leading `v`. Pushing a matching tag (for example, `v1.0.2`) builds and
publishes versioned and `latest` images for linux/amd64 and linux/arm64.
The Home Assistant image is built on top of the matching version of
`ghcr.io/immortalserg/homefinance`.
