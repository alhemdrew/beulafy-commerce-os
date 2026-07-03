# Beulafy Commerce OS

> A modern multi-tenant commerce platform powered entirely by Nomba Payments.

![PHP](https://img.shields.io/badge/PHP-8.x-blue)
![MySQL](https://img.shields.io/badge/MySQL-Database-orange)
![Nomba](https://img.shields.io/badge/Payments-Nomba-success)
![Status](https://img.shields.io/badge/Build-Stage%201-brightgreen)

---

# Overview

Beulafy Commerce OS enables businesses to launch complete online stores while managing products, subscriptions, customers and payments from one platform.

For the DevCareer × Nomba Hackathon, the platform has been redesigned to use **Nomba as the only payment infrastructure**.

Every payment flow—including merchant subscriptions and customer product purchases—is now being migrated into a unified Nomba payment domain following Nomba's recommended payment architecture.

---

# Current Progress

Current completion:

✅ Multi-tenant business platform

✅ Store management

✅ Product management

✅ Customer ordering

✅ Merchant subscriptions

✅ Transaction recording

✅ Notification engine

✅ Commission system

✅ Nomba payment architecture

✅ Payment abstraction layer

✅ Webhook infrastructure

✅ Verification infrastructure

✅ Replay protection

✅ Audit logging

🚧 Final API integration

🚧 Sandbox verification

🚧 Recurring subscription implementation

🚧 Production deployment

---

# Core Features

## Merchant Features

- Business registration
- Store creation
- Product management
- Subscription management
- Dashboard
- Analytics
- Order management

---

## Customer Features

- Browse stores
- Purchase products
- Secure checkout
- Order confirmation
- Payment receipts

---

## Payment Features

Entire payment infrastructure powered by **Nomba**

Supports

- Product Checkout
- Merchant Subscription Checkout
- Server-side Verification
- Webhook Processing
- Transaction Logging
- Replay Protection
- Audit Trail
- Signature Validation
- Callback Validation
- Idempotent Processing

---

# Architecture

```
Customer

↓

Checkout

↓

Payment Service Factory

↓

Nomba Checkout Service

↓

Nomba API

↓

Webhook

↓

Verification

↓

Order Processing

↓

Notifications

↓

Database
```

---

# Technology

PHP 8

MySQL

HTML

CSS

JavaScript

Nomba API

Apache

REST API

---

# Repository Structure

```
src/

Payments/

Nomba/

Repositories/

DTOs/

Shared/

Models/

pay/

admin/

config/

database/

public/
```

---

# Current Build Stage

The project is currently undergoing the final payment migration from legacy providers into a completely Nomba-powered architecture.

Remaining work primarily focuses on

- Final sandbox validation
- Recurring subscriptions
- End-to-end payment testing
- Production hardening

The business platform itself is operational.

---

# Screenshots

## Login

docs/screenshots/login.png

## Dashboard

docs/screenshots/dashboard.png

## Businesses

docs/screenshots/businesses.png

## Store

docs/screenshots/store.png

## Products

docs/screenshots/products.png

## Subscription

docs/screenshots/subscription.png

## Product Checkout

docs/screenshots/product-checkout.png

## Nomba Checkout

docs/screenshots/nomba-checkout.png

---

# Documentation

See

- NOMBA_IMPLEMENTATION_SUMMARY.md
- NOMBA_MIGRATION.md

---

Built for the DevCareer × Nomba Hackathon 2026.
