# Shopify Order Automation using Pipedream

## Overview

This project implements an automated order-processing workflow using Pipedream.

The workflow receives a Shopify order webhook, validates specific business rules, and sends automated emails to eligible customers.

## Business Requirements

The workflow performs the following checks:

1. Receives a Shopify order webhook.
2. Verifies that the order contains the tag **MakeOrder**.
3. Verifies that the customer contains the tag **ColdCustomer**.
4. Verifies that the order amount is greater than **₹2500**.

If all conditions are satisfied:

* Send an immediate welcome email to the customer.
* Wait for 5 minutes.
* Send a second email informing the customer that a discount has been unlocked.

If any condition fails, the workflow terminates without sending emails.

---

## Workflow Architecture

```text
Webhook Trigger
       │
       ▼
Validate Order (Python)
       │
       ▼
Check Order Conditions
       │
 ┌─────┴─────┐
 │           │
 ▼           ▼
Eligible    Stop Workflow
 │
 ▼
Send Welcome Email
 │
 ▼
Delay Workflow (5 Minutes)
 │
 ▼
Send Discount Email
```
