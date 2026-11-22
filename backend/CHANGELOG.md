# 2026.11.22.083222

Automated release (UTC timestamp).

# 2.1.0

- Use generic apps.jsie.de source and image names.
- Share verification and frontend artifacts, cache builds, and compile Go natively for each architecture.

# 2.0.0

- Replace the Python API with a shared Go portal and API server.
- Add Gift Planner with PostgreSQL persistence and live updates.
- Move Blackjack storage to its own PostgreSQL database; no SQLite migration.
- Preserve the app slug and legacy API routes.

Requires PostgreSQL credentials before startup. Back up before upgrading.
