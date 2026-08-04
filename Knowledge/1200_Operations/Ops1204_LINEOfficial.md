---
id: Ops1204
title: LINE Official Account Integration（LINE 官方帳號整合架構）
category: Operations
version: 3.0
priority: 12004
layer: Operations
tags:
  - LINE OA
  - Messaging API
  - Rich Menu
  - LIFF
  - CRM
related:
  - Ops1203
  - Ops1205
  - Engine1010
---

# 建立目的

統一定義 ShuYi-RAG V3.0 與 LINE Official Account 整合架構。

---

# System Flow

```text
LINE User

↓

LINE Official Account

↓

Webhook

↓

n8n

↓

Engine1010

↓

OpenAI

↓

LINE Reply API

↓

User
```

---

# Integration Module

固定：

```text
Messaging API

Webhook

LIFF

Rich Menu

Rich Menu Alias

Flex Message

Push Message

Broadcast
```

---

# User Binding

每位使用者：

固定綁定：

```text
LINE User ID

↓

User Profile

↓

Membership

↓

Conversation

↓

Project
```

---

# Authentication

支援：

```text
LINE Login

LIFF Login

JWT

Member Token
```

---

# Rich Menu

建議：

```text
開始解析

完整人格

今年流年

課程資訊

會員中心

客服中心
```

---

# Message Type

支援：

```text
Text

Image

Flex

Template

Quick Reply

Carousel

Video
```

---

# Webhook Event

支援：

```text
Follow

Unfollow

Message

Postback

Beacon

Member Joined

Member Left
```

---

# Reply Flow

```text
Receive

↓

Permission

↓

Retrieval

↓

Prompt

↓

OpenAI

↓

Reply API
```

---

# Push Flow

```text
System Event

↓

n8n

↓

LINE Push API

↓

User
```

---

# CRM Sync

同步：

```text
LINE User

↓

CRM

↓

Membership

↓

Conversation

↓

Project
```

---

# Message Log

固定保存：

```json
{
  "message_id":"",
  "user_id":"",
  "type":"",
  "intent":"",
  "status":"",
  "created_at":""
}
```

---

# Rich Menu Alias

支援：

```text
Guest

Free

Member

Teacher

VIP
```

不同身份：

顯示不同選單。

---

# Notification

支援：

```text
會員到期

付款成功

課程通知

AI完成解析

系統公告
```

---

# Validation

□ LINE Login

□ Webhook

□ Messaging API

□ Reply API

□ Push API

□ Rich Menu

□ CRM Sync

全部完成。

---

# Deployment

支援：

- LINE Official Account
- LINE Login
- LIFF
- Messaging API
- Webhook
- n8n

---

# 關聯

Ops1203_BillingArchitecture

Ops1205_CRMArchitecture

Engine1010_MasterEngine
