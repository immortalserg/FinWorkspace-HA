# FinWorkspace for Home Assistant

FinWorkspace for Home Assistant — a self-hosted personal finance and investment workspace.

This Home Assistant add-on packages the FinWorkspace application. FinWorkspace is an independent continuation of the original [HomeFinance project by Lefyd24](https://github.com/Lefyd24/HomeFinance).

## Install

1. Ensure the package `ghcr.io/immortalserg/finworkspace-ha` is public.
2. In Home Assistant open Settings -> Apps -> App repositories.
3. Add https://github.com/immortalserg/FinWorkspace-HA.
4. Refresh the app store, install FinWorkspace and start it.
5. Open the app at http://HOME_ASSISTANT_IP:8223.

## Configuration

Application settings such as SMTP, AI provider, notification preferences,
legal details, URLs, limits and administrator email list are configured
inside FinWorkspace under **Admin -> Application Settings**.

The Home Assistant app configuration intentionally contains only the
three fields used to bootstrap the first administrator on a fresh database:

- `initial_admin_email`
- `initial_admin_name`
- `initial_admin_password`

A new installation requires an initial administrator because registration
uses invite codes created by an administrator. Set these three fields before
the first start. Once the first administrator has been created, clear these
three values in the Home Assistant app configuration; the existing account
will remain in the database.

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

The `finworkspace/config.yaml` version must match the Git tag without its
leading `v`. Pushing a matching tag (for example, `v1.1.0`) builds and
publishes versioned and `latest` images for linux/amd64 and linux/arm64.
The Home Assistant image is built on top of the matching application image,
currently `ghcr.io/immortalserg/finworkspace:1.5.0`.
