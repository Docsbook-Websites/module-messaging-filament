---
title: Module architecture
description: How Liberu composes independently versioned Composer modules into full applications
---

# Module architecture

Every Liberu application — CRM, ERP, CMS, ecommerce, billing — is a Laravel host app that installs capabilities as separately versioned Composer packages rather than baking them into the host codebase.

<!-- widget:stepper -->

### Declare the capability

A module owns one capability boundary, for example `messaging.filament` (authenticated inbox and conversation presentation for Filament panels). The boundary is declared in the module's README, not inferred from its code.

### Install through Composer

```bash
composer require liberusoftware/messaging-filament
```

The `liberusoftware/composer-installer` places the package in a predictable path (`/modules/messaging-filament`). Composer and its lock file remain the source of version truth — the installed directory is tracked by the host repo but not hand-edited.

### Wire the service provider

Each module ships a service provider (e.g. `Liberu\Messaging\Filament\MessagingFilamentServiceProvider`) that the host registers. Installation does not imply runtime enablement — a host can carry a module without turning it on.

### Consume through public contracts only

Host applications and other modules integrate through the module's declared public contracts, never its internal classes or database tables. A module that owns no migration (like the Filament messaging layer) stays a pure presentation boundary over data another module owns.

<!-- /stepper -->

## Why this over a monolith

- **Selective installation** — a CMS host never carries accounting tables it doesn't query.
- **Independent testing** — each module ships its own Pest test suite, run in isolation from the host: `vendor/bin/pest modules/<module>/tests`.
- **Independent versioning** — a module can ship a fix without a full-platform release.
- **Clear ownership boundary** — "enabled by default: no" is a real, declared property of a module, not a convention.

The tradeoff is that reading one module's README in isolation undersells it — the interesting unit is the application it's composed into, covered under [Applications](/index.md#applications).
