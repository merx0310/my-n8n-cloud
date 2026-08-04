---
id: Ops1201
title: User Management Architecture（使用者管理架構）
category: Operations
version: 3.0
priority: 12001
layer: Operations
tags:
  - User
  - Membership
  - LINE OA
  - CRM
related:
  - Engine1002
  - Ops1202
---

# 建立目的

統一定義 ShuYi-RAG V3.0 使用者管理架構。

---

# User Lifecycle

```text
Visitor

↓

Register

↓

Verify

↓

Member

↓

Teacher

↓

VIP

↓

Admin
```

---

# User Profile

固定：

```text
User ID

LINE User ID

Name

Email

Phone

Birthday

Role

Status

Created At

Updated At
```

---

# Membership

支援：

```text
Guest

Free

Member

Teacher

VIP

Admin
```

---

# Status

固定：

```text
Active

Pending

Suspended

Expired

Deleted
```

---

# Authentication

支援：

```text
LINE Login

Email

OAuth

JWT
```

---

# User Preference

保存：

```text
Language

Output Format

Teacher Mode

Notification

Theme
```

---

# Project Binding

每位使用者：

可綁定：

```text
Knowledge

Conversation

Projects

Subscription
```

---

# Validation

□ User

□ Role

□ Status

□ Authentication

□ Preference

全部完成。

---

# 關聯

Engine1002_Permission

Ops1202_SubscriptionArchitecture
