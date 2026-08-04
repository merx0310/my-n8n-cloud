---
id: Ops1203
title: Billing Architecture（金流管理架構）
category: Operations
version: 3.0
priority: 12003
layer: Operations
tags:
  - Billing
  - Payment
  - Invoice
  - Subscription
  - Finance
related:
  - Ops1202
  - Ops1204
  - Engine1002
---

# 建立目的

統一定義 ShuYi-RAG V3.0 金流管理架構。

---

# Billing Flow

```text
Select Plan

↓

Create Order

↓

Payment Gateway

↓

Payment Verify

↓

Update Subscription

↓

Issue Invoice

↓

Notify User
```

---

# Payment Gateway

支援：

```text
綠界 ECPay

藍新 NewebPay

Stripe

PayPal

Apple Pay

Google Pay

LINE Pay
```

---

# Payment Method

固定：

```text
Credit Card

ATM Transfer

Bank Transfer

LINE Pay

Apple Pay

Google Pay
```

---

# Order Status

固定：

```text
Pending

Paid

Failed

Refunded

Cancelled

Expired
```

---

# Invoice Status

固定：

```text
Pending

Issued

Voided

Refunded
```

---

# Billing Cycle

支援：

```text
One Time

Monthly

Quarterly

Yearly

Lifetime
```

---

# Payment Verify

付款完成：

```text
Gateway Callback

↓

Verify Signature

↓

Update Order

↓

Activate Subscription

↓

Permission Refresh
```

---

# Refund Flow

```text
Refund Request

↓

Review

↓

Gateway Refund

↓

Update Order

↓

Update Subscription

↓

Notify User
```

---

# Order Schema

```json
{
  "order_id":"",
  "user_id":"",
  "plan":"",
  "amount":0,
  "currency":"TWD",
  "status":"Pending",
  "created_at":"",
  "paid_at":""
}
```

---

# Payment Schema

```json
{
  "payment_id":"",
  "gateway":"",
  "transaction_id":"",
  "amount":0,
  "status":"Paid",
  "paid_at":""
}
```

---

# Invoice Schema

```json
{
  "invoice_id":"",
  "order_id":"",
  "number":"",
  "status":"Issued",
  "issued_at":""
}
```

---

# Permission Sync

付款成功：

固定同步：

```text
Ops1202

↓

Engine1002

↓

Engine1010
```

---

# Failure Policy

付款失敗：

```text
Retry

↓

Notify User

↓

Keep Pending
```

最多：

3 次。

---

# Security

固定：

```text
HTTPS

Webhook Signature

Transaction Verify

Encrypted Storage

Audit Log
```

---

# Audit Log

```json
{
  "order_id":"",
  "payment_id":"",
  "gateway":"",
  "status":"",
  "operator":"",
  "timestamp":""
}
```

---

# Validation

□ Order

□ Payment

□ Verify

□ Subscription

□ Permission

□ Invoice

全部完成。

---

# Deployment

支援：

- LINE OA
- Web App
- Mobile App
- API
- Enterprise Portal

---

# 關聯

Ops1202_SubscriptionArchitecture

Ops1204_LINEOAIntegration

Engine1002_Permission
