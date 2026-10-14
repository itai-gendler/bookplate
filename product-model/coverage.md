---
scope: The Bookplate web app and its server commands, for the library, notes, progress, vocabulary, statistics, showcases, import and export, settings and accounts.
method: Static inspection of source, schema, tests and documentation at the pinned commit; nothing was run.
covered:
  - description: Library, book details, add and edit form, covers, progress and statistics pages and components.
    paths: [app/page.tsx, app/statistics/, components/]
  - description: Book notes pages and their editor.
    paths: ["app/books/"]
  - description: Vocabulary page.
    paths: [app/vocabulary/]
  - description: Settings page and its tabs.
    paths: [app/settings/, lib/settingsTabs.ts, lib/featureList.ts, lib/features.ts, lib/hints.ts]
  - description: Sign-in, set-up, sign-up, password reset and legal pages.
    paths: [app/login/, app/setup/, app/signup/, app/forgot-password/, app/reset-password/, app/privacy/, app/terms/, lib/legal.ts]
  - description: Public showcase pages, their covers and preview image.
    paths: ["app/s/"]
  - description: Library, notes, progress, vocabulary, covers, avatar, showcase, account, catalogue and dictionary route handlers.
    paths: [app/api/books/, app/api/notes/, app/api/progress/, app/api/vocabulary/, app/api/covers/, app/api/avatar/, app/api/showcases/, app/api/account/, app/api/booksearch/, app/api/define/, app/api/email/, app/api/export/, app/api/import/, app/api/signup-challenge/, app/api/auth/]
  - description: Domain logic for records, progress, ratings, showcases, imports, exports, limits and cover lookup.
    paths: [lib/library.ts, lib/types.ts, lib/validate.ts, lib/progress.ts, lib/ratings.ts, lib/showcase.ts, lib/showcaseYear.ts, lib/archive.ts, lib/csvImport.ts, lib/csv.ts, lib/limits.ts, lib/coverLookup.ts, lib/openLibrary.ts, lib/palette.ts, lib/image.ts, lib/callout.ts]
  - description: Accounts, sessions, sign-up checks, email and housekeeping.
    paths: [lib/auth.ts, lib/auth-client.ts, lib/authThrottle.ts, lib/botCheck.ts, lib/email.ts, lib/housekeeping.ts, lib/config.ts, lib/db/schema.ts, proxy.ts]
  - description: Server commands for resetting a password and removing a showcase.
    paths: [scripts/]
exclusions:
  - description: Styling, fonts, icons and the web app manifest.
    paths: [app/globals.css, app/layout.tsx, app/manifest.ts, app/icon.svg, app/apple-icon.png, app/favicon.ico, public/]
  - description: Database connection, migrations and image storage drivers.
    paths: [lib/db/index.ts, lib/db/migrate.ts, drizzle/, drizzle.config.ts, lib/storage/]
  - description: Logging, request ids, client error reports, health check, outbound pacing, caching, startup and client address handling.
    paths: [lib/log.ts, lib/outbound.ts, lib/cache.ts, lib/startup.ts, lib/clientIp.ts, lib/api.ts, lib/id.ts, instrumentation.ts, app/api/client-errors/, app/api/health/, app/error.tsx]
  - description: Tests, fixtures and test configuration.
    paths: [test/, vitest.config.mts]
  - description: Build, container, CI, release and editor configuration.
    paths: [Dockerfile, docker-compose.yml, docker-compose.dev.yml, .dockerignore, .github/, next.config.ts, tsconfig.json, eslint.config.mjs, package.json, package-lock.json, RELEASING.md]
unmapped:
  - description: Contact form endpoint that emails messages from a website on the same domain.
    paths: [app/api/contact/]
  - description: Prometheus metrics endpoint of server-wide totals.
    paths: [app/api/metrics/, lib/metrics.ts]
limitations: []
---

# Coverage
