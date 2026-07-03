# Nomba Migration Documentation

## Overview

This document explains the migration of Beulafy Commerce OS from a multi-provider payment architecture to a Nomba-first payment platform.

The migration focuses on correctness, security, maintainability and compliance with the official Nomba integration recommendations.

---

# Migration Goals

Previous architecture

```
Application

↓

Flutterwave

↓

Verification
```

New architecture

```
Application

↓

Payment Domain

↓

Nomba Services

↓

Verification

↓

Webhook

↓

Database
```

---

# Why the Migration?

The previous implementation tightly coupled payment logic to specific gateways.

The new architecture introduces:

- Payment abstraction
- Shared verification
- Modular services
- Centralized logging
- Better testing
- Secure callbacks

---

# Current Implementation

Implemented

- Checkout initialization
- Payment services
- Verification service
- Callback handlers
- Transaction repository
- Audit service
- Replay protection
- Sandbox configuration
- Shared money service

Currently Completing

- End-to-end sandbox validation
- Recurring subscription flow
- Production deployment testing

---

# Security Model

Every payment follows this sequence.

```
Customer

↓

Checkout

↓

Nomba

↓

Callback

↓

Verify with Nomba API

↓

Validate Amount

↓

Validate Currency

↓

Validate Reference

↓

Store Transaction

↓

Activate Product
```

No customer data is trusted until Nomba confirms the payment.

---

# Amount Handling

All amounts are processed internally in Kobo.

Workflow

```
NGN

↓

MoneyService

↓

Kobo

↓

Nomba

↓

Verify

↓

Convert Back
```

This avoids floating-point inaccuracies.

---

# Callback Strategy

Client callback

Purpose

User experience only.

Server callback

Purpose

Display payment result.

Webhook

Purpose

Actual payment confirmation.

Only webhook/API verification updates records.

---

# Current Progress

Completed

- Architecture
- Services
- Payment verification
- Database integration
- Logging
- Sandbox support

Remaining

- Final recurring billing
- Complete webhook production validation
- Production credentials

---


## Current Development Focus

The migration is currently in its integration and validation phase.

The remaining implementation focuses on:

- Completing Sandbox payment execution
- Webhook verification using live events
- Recurring subscription lifecycle
- Final callback validation
- Production deployment preparation

No legacy payment providers will remain in the final implementation. Every payment operation will execute exclusively through Nomba.
