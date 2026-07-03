> [!IMPORTANT]
> - This public repository is a sanitized architecture skeleton of Luminy’s private production codebase.
> - The full source code is private because Luminy is an active production platform w/ 1k+ real users.

# Luminy

Luminy is a personal finance automation platform I built to help users connect financial accounts, sync transactions, track spending, detect recurring subscriptions, and view account-level insights from one dashboard.

This public repository is a **sanitized architecture skeleton** of the private production codebase.  
The full repository is private because Luminy is an active production application with real users, financial integrations, deployment configs, and security-sensitive implementation details.

## Why this repo is public

The goal of this repository is to show the structure and engineering approach behind Luminy without exposing:

- API keys or environment configuration
- Plaid integration internals
- Authentication/security logic
- Production database schema details
- Deployment infrastructure
- Proprietary business logic

## System Overview

Luminy is built around a backend-first architecture that supports account linking, transaction syncing, user-specific financial data processing, and scheduled refresh automation.

Core backend responsibilities include:

- Plaid Link token creation and public token exchange
- Account and transaction ingestion through Plaid APIs
- Transaction synchronization using cursor-based sync
- Webhook handling for account and item updates
- Scheduled background refresh jobs
- User-authenticated financial dashboards
- Subscription and recurring payment detection
- Account-level aggregation for cash, credit, loans, and investments

## Architecture

```text
luminy/
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── auth/
│   │   ├── services/
│   │   ├── routers/
│   │   ├── db/
│   │   └── integrations/
│   │       └── plaid/
│   ├── tests/
│   └── README.md
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── hooks/
│   ├── services/
│   └── README.md
│
├── mobile/
│   ├── app/
│   ├── screens/
│   ├── components/
│   ├── hooks/
│   ├── navigation/
│   └── services/
│
├── shared/
│   ├── types/
│   ├── constants/
│   └── utils/

├── infrastructure/
│   ├── nginx/
│   ├── systemd/
│   └── monitoring/
│
└── docs/
    ├── architecture.md
    ├── data-flow.md
    └── scaling-notes.md
