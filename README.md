# Shopify Order Automation using Pipedream

The Pipedream workflow used for this assignment can be accessed using the link below:

https://pipedream.com/new?h=tch_p7fv0n

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

## Sample Webhook Payload
```
{
  "tags": "MakeOrder",
  "current_total_price": 3000,
  "customer": {
    "email": "customer@example.com",
    "tags": "ColdCustomer"
  }
}
```

## Workflow 

<img width="605" height="660" alt="image" src="https://github.com/user-attachments/assets/74a62661-8e1e-4120-a053-4e7aa7215de3" />

## Email Notification

<img width="1427" height="97" alt="image" src="https://github.com/user-attachments/assets/1d633260-bd5a-44be-9001-982c4a7e3547" />


