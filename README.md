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

# Current Development Status

Beulafy Commerce OS has reached the MVP stage.

The core commerce engine—including merchant onboarding, store management, product management, checkout, subscriptions, dashboards, and order management—is functional.

Current development is focused on completing a full migration to the Nomba payment ecosystem using the official Sandbox APIs. The remaining work includes end-to-end payment validation, webhook verification, recurring subscription support, and final production hardening.

This repository represents the Stage 1 Build progress for the DevCareer × Nomba Hackathon and will continue to evolve throughout the remaining build period.


Current Implementation: 

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

  # Nomba Integration Highlights

The payment layer has been redesigned around the official Nomba APIs using a server-authoritative architecture.

Current implementation includes:

- Secure Checkout Initialization
- Sandbox Environment Integration
- Payment Verification
- Callback Handling
- Webhook Processing
- Kobo-based Currency Handling
- Replay Protection
- Audit Logging
- Idempotent Transaction Processing

The final implementation will route all payment operations exclusively through Nomba.

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

![Homepage](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/01-homepage.png)

Landing page and entry point.

---

## Dashboard

![Dashboard](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/02-dashboard.png)

Business overview dashboard.

---

## Store Management

![Store Management](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/03-store-management.png)

Manage stores and products.

---

## Product Checkout

![Product Checkout](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/04-product-checkout.png)

Customer checkout process.

---

## Subscription Payment

![Subscription Payment](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/05-subscription-payment.png)

Subscription purchase flow.

---

## Payment Success

![Payment Success](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/07-payment-success.png)

Successful payment confirmation.

---

## Database Design

![Database Design](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/08-database.png)

Current relational database structure.

---

## Payment Architecture

![Payment Architecture](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/09-payment-architecture.png)

Nomba payment architecture.

---

## Product Structure

![Product Structure](https://raw.githubusercontent.com/alhemdrew/beulafy-commerce-os/main/docs/screenshots/10-project-structure.png)

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
# Roadmap

## Stage 1 ✅

- Commerce platform
- Merchant management
- Store management
- Product management
- Checkout architecture
- Nomba payment architecture
- Security layer
- Documentation

---

## Stage 2 🚧

- Complete Sandbox integration
- Webhook validation
- Recurring subscriptions
- Production deployment
- Merchant analytics
- Performance optimization
  
# Current Status

This repository represents our Stage 1 MVP.

The application architecture is complete, while the final Nomba payment flow is undergoing end-to-end sandbox validation before production deployment.
