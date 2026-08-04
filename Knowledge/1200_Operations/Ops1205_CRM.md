---
id: Ops1205
title: CRM Architecture（客戶關係管理架構）
category: Operations
version: 3.0
priority: 12005
layer: Operations
tags:
  - CRM
  - Customer
  - Membership
  - AI
  - LINE OA
related:
  - Ops1204
  - Ops1206
  - Engine1008
---

# 建立目的

統一定義 ShuYi-RAG V3.0 CRM（Customer Relationship Management）架構。

---

# CRM Flow

```text
LINE User

↓

Register

↓

Customer Profile

↓

Membership

↓

Conversation

↓

Project

↓

AI Analysis

↓

Service Record

↓

Follow-up
```

---

# Customer Profile

固定：

```text
Customer ID

LINE User ID

Name

Gender

Birthday

Phone

Email

Role

Status

Created At

Updated At
```

---

# Membership

記錄：

```text
Plan

Start Date

Expire Date

Auto Renew

Status
```

---

# Customer Tags

支援：

```text
New

Potential

Member

Teacher

VIP

Enterprise

Inactive
```

可同時擁有多個 Tag。

---

# Conversation Record

保存：

```text
Question

Answer

Intent

Knowledge

Engine

Timestamp
```

---

# Personality Record

保存：

```text
Life Number

Main Personality

Dream

Five Elements

Missing Numbers

Five Blessings

Life Cycle
```

---

# Project Record

保存：

```text
Project ID

Project Name

Progress

Last Update
```

---

# Service Record

保存：

```text
Consultation

Course

Purchase

Payment

Support

Feedback
```

---

# AI Interaction

保存：

```text
Prompt

Response

Token

Duration

Engine

Model
```

---

# Customer Timeline

依時間排序：

```text
Register

↓

First Analysis

↓

Course

↓

Payment

↓

Renew

↓

Support
```

---

# Search

支援：

```text
Customer Name

LINE User ID

Phone

Email

Tag

Membership

Project
```

---

# Statistics

統計：

```text
Total Users

Active Users

Teacher Users

VIP Users

Renew Rate

Retention Rate
```

---

# CRM Schema

```json
{
  "customer_id":"",
  "line_user_id":"",
  "membership":"Teacher",
  "status":"Active",
  "tags":[
    "VIP",
    "Course"
  ],
  "projects":[],
  "conversation_count":0,
  "last_active":""
}
```

---

# Synchronization

固定同步：

```text
LINE OA

↓

CRM

↓

Membership

↓

Conversation

↓

Project

↓

Analytics
```

---

# Validation

□ Customer

□ Membership

□ Conversation

□ Project

□ Service

□ Statistics

全部完成。

---

# Deployment

支援：

- LINE Official Account
- Web App
- Mobile App
- Admin Portal
- API

---

# 關聯

Ops1204_LINEOAIntegration

Ops1206_KnowledgeSyncArchitecture

Engine1008_ConversationMemory
