# 2026.11.22.111156

Automated release (UTC timestamp).

# Startup configuration fix

- Read Supervisor-owned options securely before dropping to the service user.
- Report configuration read errors instead of ignoring saved settings.

# 2.1.0

- Use generic apps.jsie.de source and image names.
- Share verification and frontend artifacts, cache builds, and compile Go natively for each architecture.

# 2.0.0

- Replace the Python API with a shared Go portal and API server.
- Add Gift Planner with PostgreSQL persistence and live updates.
- Move Blackjack storage to its own PostgreSQL database; no SQLite migration.
- Preserve the app slug and legacy API routes.

Requires PostgreSQL credentials before startup. Back up before upgrading.
