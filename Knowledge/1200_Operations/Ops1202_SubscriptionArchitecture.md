---
id: Ops1202
title: Subscription Architecture（訂閱管理架構）
category: Operations
version: 3.0
priority: 12002
layer: Operations
tags:
  - Subscription
  - Membership
  - Billing
  - LINE OA
  - CRM
related:
  - Ops1201
  - Ops1203
  - Engine1002
---

# 建立目的

統一定義 ShuYi-RAG V3.0 訂閱管理架構。

---

# Subscription Flow

```text
Register

↓

Select Plan

↓

Payment

↓

Activate

↓

Permission Update

↓

Service Available

↓

Renew

↓

Expire
```

---

# Membership Plan

固定：

```text
Guest

Free

Member

Teacher

VIP

Enterprise

Admin
```

---

# Plan Permission

## Guest

```text
系統介紹

基本操作

不得使用AI解析
```

---

## Free

```text
免費解析

限制次數

限制功能
```

---

## Member

```text
完整知識

一般AI解析

會員功能
```

---

## Teacher

```text
老師版解析

Master Engine

完整人格融合

專案管理
```

---

## VIP

```text
Teacher全部功能

優先AI

高Token

專屬服務
```

---

## Enterprise

```text
API

多帳號

管理平台

團隊權限
```

---

## Admin

```text
全部功能

系統管理

Debug

Deployment
```

---

# Subscription Status

固定：

```text
Pending

Active

Expired

Suspended

Cancelled
```

---

# Billing Cycle

支援：

```text
Monthly

Quarterly

Yearly

Lifetime
```

---

# Auto Renewal

固定：

```text
Enable

Disable
```

---

# Permission Update

付款成功：

```text
Update Role

↓

Refresh Permission

↓

Refresh Retrieval

↓

Refresh Prompt
```

---

# Expire Flow

```text
Expire

↓

Downgrade

↓

Keep History

↓

Disable Premium
```

---

# Grace Period

固定：

```text
7 Days
```

---

# Subscription Schema

```json
{
  "user_id":"",
  "plan":"Teacher",
  "status":"Active",
  "billing":"Monthly",
  "start_date":"",
  "expire_date":"",
  "auto_renew":true
}
```

---

# Validation

□ Plan

□ Status

□ Billing

□ Permission

□ Renewal

全部完成。

---

# Engine

付款完成：

固定同步：

```text
Engine1002

Permission Engine
```

---

# 關聯

Ops1201_UserManagement

Ops1203_BillingArchitecture

Engine1002_Permission
