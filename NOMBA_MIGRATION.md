# Flutterwave to Nomba Migration

## Purpose

This document describes the migration of Beulafy from a multi-provider payment implementation to a Nomba-first payment architecture.

The migration removes legacy gateway dependencies and consolidates every payment operation through a unified Nomba service layer.

---

# Migration Objectives

Replace

- Flutterwave
- Legacy payment wrappers
- Mixed verification logic

With

- Nomba Checkout
- Nomba Verification API
- Nomba Webhooks
- Shared Payment Services

---

# Payment Philosophy

The application never trusts:

- browser responses
- callback query parameters
- frontend payment status
- frontend amounts

Every payment is confirmed directly from Nomba.

---

# Verification Flow

Customer

↓

Pay on Nomba

↓

Return Callback

↓

Receive Transaction Reference

↓

Server Requests Verification

↓

Nomba Responds

↓

Validate

- payment status
- transaction reference
- merchant account
- amount
- currency
- customer email

↓

Update Database

↓

Complete Business Logic

---

# Security Principles

## Server Authoritative

Only the server decides whether payment succeeded.

---

## Amount Validation

Every amount is stored internally.

Returned Nomba values are compared against the stored transaction amount.

Amounts are converted using Kobo.

No browser amount is trusted.

---

## Replay Protection

Every verified transaction is stored.

Duplicate verification attempts are rejected.

Duplicate webhooks are ignored.

---

## Pending Transactions

Orders remain pending until verification succeeds.

No inventory updates occur before verification.

No subscriptions activate before verification.

---

## Webhooks

Webhooks become the source of truth.

Callbacks improve user experience.

Business actions depend on successful verification.

---

# Current Payment Modules

Payments/

├── CheckoutService

├── ProductPaymentService

├── SubscriptionPaymentService

├── VerificationService

├── WebhookService

├── ReplayProtection

├── MoneyService

├── AuditService

├── TransactionRepository

---

# Environment Variables

```
NOMBA_PUBLIC_KEY=

NOMBA_SECRET_KEY=

NOMBA_ACCOUNT_ID=

NOMBA_WEBHOOK_SECRET=

NOMBA_BASE_URL=
```

---

# Sandbox

Current development uses the official Nomba Sandbox.

Before production deployment:

- replace sandbox credentials
- update webhook URL
- enable production API
- verify SSL
- perform end-to-end payment testing

---

# Remaining Work

- Complete sandbox validation
- Inclusion of multi/recurring sub. payment feature.
- Final webhook signature verification
- Performance optimization
- UI polishing
- Production deployment

---

# Outcome

The final platform will operate exclusively on Nomba with:

- one payment provider
- one verification process
- one webhook architecture
- centralized payment services
- secure server-authoritative payment handling
- scalable payment infrastructure

This migration aligns the platform with modern payment security standards and demonstrates a production-ready Nomba integration suitable for deployment after final testing.
