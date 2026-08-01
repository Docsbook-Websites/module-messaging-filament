---
title: Messaging
description: The authenticated inbox and conversation layer shared across Liberu applications
---

# Messaging

Liberu's messaging capability is split into two modules that follow the platform's [module architecture](./module-architecture.md):

- **`liberusoftware/messaging`** — the domain layer: conversations, messages, persistence.
- **[`liberusoftware/messaging-filament`](https://github.com/liberusoftware/module-messaging-filament)** — authenticated inbox and conversation presentation for Filament panels, covered by this site.

## Install

```bash
composer require liberusoftware/messaging-filament
```

Requires `php ^8.5`, `filament/filament ^5.1` and `liberusoftware/messaging ^1.0`. The `liberusoftware/composer-installer` places the package at `/modules/messaging-filament`.

## Scope

- Service provider: `Liberu\Messaging\Filament\MessagingFilamentServiceProvider`
- Category: `presentation` — owns no database migration; authorization stays the host application's responsibility.
- Enabled by default: no.
- No console commands, no published events currently.

## Testing

```bash
vendor/bin/pest modules/messaging-filament/tests
```

## Where this fits

Any Liberu application — [CRM](../applications/crm.md), [ERP](../applications/erp-accounting.md), [ecommerce](../applications/ecommerce.md) — can install this module to add an authenticated inbox to its Filament admin panel without owning the messaging domain logic itself.

## Security

Report vulnerabilities privately to `security@liberusoftware.com` — not through public GitHub issues.
