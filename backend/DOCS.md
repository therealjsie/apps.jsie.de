# Apps Backend

Shared Go server for the portal, Gift Planner (`/gifts/`), Blackjack
(`/blackjack/`), and their APIs.

Set these options before startup:

- `access_team_domain`: your Cloudflare Access team domain, without `https://`.
- `access_audience`: the audience of the Access application for your hostname.
- `database_host`: `43f3da93-apps-postgres` for PostgreSQL from this repository.
- `gifts_database_password`: the PostgreSQL app's `gifts_password`.
- `blackjack_database_password`: its `blackjack_password`.

Start PostgreSQL first. The backend's host port defaults to 8090. Route the
protected hostname through Cloudflare Tunnel to that port. Production requests
require a valid Access JWT, including requests for frontend pages.

Gift Planner writes shared PostgreSQL state and refreshes connected browsers.
Existing browser-only data is not imported automatically; export/import it
explicitly. Legacy Blackjack SQLite data is not migrated.

Back up PostgreSQL before upgrading. Image rollback requires a compatible
schema; otherwise restore the matching database backup. This repository's app
has a separate identity from a previously installed local backend.
