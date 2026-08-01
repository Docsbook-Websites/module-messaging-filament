---
title: Liberu
description: Open-source Laravel/Filament platform of enterprise applications — CRM, ERP, CMS, ecommerce, billing and more
---

# Liberu

Liberu is an open-source suite of enterprise applications built on Laravel 13, PHP 8.5, Filament 5 and Livewire 4 — each one a self-hosted alternative to a category-leading SaaS: [CRM](https://github.com/liberusoftware/crm-laravel) instead of HubSpot or Salesforce, [ecommerce](https://github.com/liberusoftware/ecommerce-laravel) instead of Shopify or WooCommerce, [accounting](https://github.com/liberusoftware/accounting-erp-laravel) instead of QuickBooks or Xero, [CMS](https://github.com/liberusoftware/cms-laravel) instead of WordPress, [billing](https://github.com/liberusoftware/billing-laravel) instead of WHMCS.

Every application shares the same architecture: a Laravel host app that installs Liberu capabilities as independently versioned Composer modules — `liberusoftware/messaging-filament`, `liberusoftware/accounting-filament`, and dozens more. You take only the modules a given app needs; the host stays thin and each module stays testable on its own.

<!-- widget:cards -->

## Applications

- [CRM](./applications/crm.md) — HubSpot / Salesforce alternative {users}
- [ERP & Accounting](./applications/erp-accounting.md) — QuickBooks / Xero / FreeAgent alternative {calculator}
- [Ecommerce](./applications/ecommerce.md) — Shopify / WooCommerce / Magento alternative {shopping-cart}
- [CMS](./applications/cms.md) — WordPress / Drupal alternative {layout-template}
- [Billing](./applications/billing.md) — WHMCS / Blesta / HostBill alternative {receipt}
- [Real Estate](./applications/real-estate.md) — property agency platform with Rightmove/Zoopla/OnTheMarket feeds {home}

## Platform

- [Module architecture](./platform/module-architecture.md) — how capabilities are versioned and composed {puzzle}
- [Boilerplate](./platform/boilerplate.md) — the SaaS starting point every app is built on {rocket}
- [Messaging](./platform/messaging.md) — the inbox and conversation layer, including this Filament module {mail}

<!-- /widget -->

## Why modular

Most self-hosted alternatives to SaaS tools are single monoliths — fork it, or don't. Liberu splits each application into Composer modules with declared public boundaries: a module owns one capability, ships its own tests, and is installed only where it's needed. An ERP host doesn't carry ecommerce code it never runs; a CMS host doesn't carry accounting tables it never queries.

That's also why the platform is easy to underestimate from any single repository — `module-messaging-filament` on its own reads like a small UI package, and it is one. Its context is the twelve-plus applications built from packages like it.
