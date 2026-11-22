# Apps PostgreSQL

Set three distinct passwords of at least 20 characters before first startup:
`admin_password`, `gifts_password`, and `blackjack_password`.

Initialization creates databases `gifts` and `blackjack` and their respective
roles `gifts_app` and `blackjack_app`. The port is internal only by default.
Its hostname is `43f3da93-apps-postgres` when this repository is added using its
canonical URL.

Data persists in `/data/postgres`. Cold Home Assistant backups stop this app
while backing it up. Keep off-device database backups and test restores.

Passwords are applied when initializing empty storage. Editing options later
does not rotate PostgreSQL roles: change the role password and matching backend
option together.

Keep updates manually approved, particularly PostgreSQL major version upgrades.
A repository-installed app has separate storage from a local app. Restore an
existing database backup before switching if local PostgreSQL already has data.
