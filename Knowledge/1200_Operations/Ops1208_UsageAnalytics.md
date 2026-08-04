---
id: Ops1208
title: Usage Analytics Architecture（使用分析架構）
category: Operations
version: 3.0
priority: 12008
layer: Operations
tags:
  - Analytics
  - Dashboard
  - KPI
  - BI
  - Operations
related:
  - Ops1207
  - Ops1209
  - Engine1010
---

# 建立目的

統一定義 ShuYi-RAG V3.0 使用分析與營運數據架構。

---

# Analytics Flow

```text
User Activity

↓

Data Collection

↓

Data Processing

↓

Statistics

↓

Dashboard

↓

Business Insights
```

---

# Analytics Scope

固定統計：

```text
Users

Membership

Conversation

Knowledge

Engine

Workflow

API

Token

Revenue
```

---

# User Analytics

統計：

```text
New Users

Active Users

Returning Users

Retention Rate

Churn Rate
```

---

# Membership Analytics

統計：

```text
Guest

Free

Member

Teacher

VIP

Enterprise
```

---

# Conversation Analytics

統計：

```text
Conversation Count

Average Messages

Average Session Time

Completion Rate
```

---

# Knowledge Analytics

統計：

```text
Top Knowledge

Top Module

Search Success Rate

Knowledge Hit Rate

Knowledge Coverage
```

---

# Engine Analytics

統計：

```text
Retrieval Count

Prompt Count

Memory Usage

Fallback Count

JSON Output Count
```

---

# Workflow Analytics

統計：

```text
Workflow Success

Workflow Failure

Average Duration

Retry Count
```

---

# API Analytics

統計：

```text
API Requests

Success Rate

Error Rate

Average Response Time
```

---

# Token Analytics

統計：

```text
Input Tokens

Output Tokens

Embedding Tokens

Total Cost
```

---

# Revenue Analytics

統計：

```text
Monthly Revenue

New Subscription

Renewal Rate

ARPU

LTV
```

---

# Dashboard

固定：

```text
Executive

Operations

AI

Business

Finance
```

---

# KPI

固定：

```text
DAU

MAU

Retention

Conversion

Revenue

Cost

Response Time

Knowledge Accuracy
```

---

# Report

支援：

```text
Daily

Weekly

Monthly

Quarterly

Yearly
```

---

# Export

支援：

```text
CSV

Excel

JSON

PDF
```

---

# Analytics Schema

```json
{
  "date":"",
  "users":0,
  "conversations":0,
  "tokens":0,
  "cost":0,
  "revenue":0,
  "response_time":0,
  "success_rate":0
}
```

---

# Alert

通知：

```text
Traffic Spike

High Error Rate

Low Conversion

High Token Cost

Low Knowledge Hit Rate
```

---

# Validation

□ Users

□ Membership

□ Conversation

□ Workflow

□ API

□ Token

□ Revenue

□ Dashboard

全部完成。

---

# Deployment

支援：

- Grafana
- Metabase
- Power BI
- Looker Studio
- PostgreSQL
- Supabase

---

# 關聯

Ops1207_TokenCostManagement

Ops1209_CustomerServiceArchitecture

Engine1010_MasterEngine
