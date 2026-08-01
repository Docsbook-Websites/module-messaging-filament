---
title: CRM
description: HubSpot / Salesforce alternative built on Laravel 12, PHP 8.5, Filament 5
---

# CRM

[liberusoftware/crm-laravel](https://github.com/liberusoftware/crm-laravel) is a self-hosted CRM — an alternative to HubSpot or Salesforce for teams that want contact, pipeline and deal data on their own infrastructure instead of a per-seat SaaS.

Built on the same [module architecture](../platform/module-architecture.md) as the rest of Liberu, so a CRM deployment installs only the Composer modules it needs — the messaging inbox module documented here among them — rather than a fixed monolith.

## Stack

- Laravel 12, PHP 8.5
- Filament 5 for the admin panel
- Livewire 4 for interactive components

See [Module architecture](../platform/module-architecture.md) for how CRM-specific modules compose with shared platform modules like messaging.
