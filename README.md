# Beulafy Commerce OS
### A Modern Multi-Tenant Commerce Platform Powered by Nomba Payments

![PHP](https://img.shields.io/badge/PHP-8.x-blue)
![MySQL](https://img.shields.io/badge/MySQL-orange)
![Architecture](https://img.shields.io/badge/Architecture-Modular-success)
![Nomba](https://img.shields.io/badge/Nomba-Sandbox-green)

---

## Overview

Beulafy Commerce OS is a modern multi-tenant commerce platform that enables businesses to create digital storefronts, manage products, accept secure online payments, and manage subscriptions.

For the DevCareer × Nomba Hackathon, the platform is being migrated from multiple payment providers into a **Nomba-first payment architecture** using the official Nomba APIs.

Our focus is not simply integrating a payment gateway, but redesigning the entire payment domain around Nomba best practices.

---

# Current Progress

Current completion is approximately **80-85%**.

Completed:

- Multi-tenant architecture
- Business management
- Store creation
- Product management
- Shopping cart
- Checkout flow
- Subscription plans
- Order management
- Transaction recording
- Payment abstraction layer
- Nomba payment architecture
- Sandbox configuration
- Secure verification layer
- Callback structure
- Webhook architecture
- Audit logging
- Replay protection
- Payment verification strategy

Remaining before production:

- Final end-to-end sandbox testing
- Complete webhook verification
- Subscription recurring payment implementation
- Production credential switch
- Final UI polish
- Complete integration testing

---

# Architecture

```
Business
      │
      ▼
Store
      │
      ▼
Products
      │
      ▼
Checkout
      │
      ▼
Nomba Checkout
      │
      ▼
Callback
      │
      ▼
Server Verification
      │
      ▼
Webhook Validation
      │
      ▼
Order Confirmation
      │
      ▼
Notifications
```

---

# Core Features

## Business Management

- Create businesses
- Manage multiple stores
- Business dashboard
- Subscription management

---

## Product Management

- Product catalogue
- Categories
- Inventory
- Product images
- Pricing

---

## Customer Checkout

Customers can

- Purchase products
- Make secure payments
- Receive payment confirmations
- View order status

---

## Subscription Billing

Businesses subscribe to Beulafy through Nomba payments.

Current work includes:

- Subscription checkout
- Subscription verification
- Renewal architecture
- Future recurring billing support

---

# Nomba Integration

Current implementation includes:

- Checkout initialization
- Sandbox support
- Secure callbacks
- Payment verification
- Webhook processing
- Server-side validation
- Amount verification
- Kobo conversion
- Replay attack protection
- Transaction logging

---

# Security

The payment flow is designed to be completely server-authoritative.

We never trust:

- browser payment status
- callback success parameters
- client amounts
- frontend references

Instead we verify every payment directly with Nomba before updating any records.

---

# Technology

- PHP 8
- MySQL
- JavaScript
- HTML5
- CSS3
- REST APIs
- Nomba Sandbox APIs

---

# Screenshots

## Homepage

![](./docs/screenshots/1-homepage.png)

Landing page and entry point.

---

## Dashboard

![](./docs/screenshots/2-dashboard.png)

Business overview dashboard.

---

## Store Management

![](./docs/screenshots/3-store-management.png)

Manage stores and products.

---

## Product Checkout

![](./docs/screenshots/4-product-checkout.png)

Customer checkout process.

---

## Subscription Payment

![](docs/screenshots/5-subscription-payment.png)

Subscription purchase flow.

---

## Payment Success

![](./docs/screenshots/7-payment-success.png)

Successful payment confirmation.

---

## Database Design

![](docs/screenshots/8-database.png)

Current relational database structure.

---

## Payment Architecture

![](./docs/screenshots/9-payment-architecture.png)

Nomba payment architecture.

---

## Product Structure

![](./docs/screenshots/10-product-structure.png)

Commerce domain model.

---

# Repository Structure

```
src/
config/
payments/
pay/
admin/
public/
docs/
```

---

# Current Status

This repository represents our Stage 1 MVP.

The application architecture is complete, while the final Nomba payment flow is undergoing end-to-end sandbox validation before production deployment.
