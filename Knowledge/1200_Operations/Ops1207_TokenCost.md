---
id: Ops1207
title: Token Cost Management Architecture（Token 成本管理架構）
category: Operations
version: 3.0
priority: 12007
layer: Operations
tags:
  - Token
  - Cost
  - OpenAI
  - Billing
  - AI
related:
  - Ops1206
  - Ops1208
  - Engine1001
  - Engine1004
---

# 建立目的

統一定義 ShuYi-RAG V3.0 Token 使用與成本管理架構。

---

# Cost Flow

```text
User Request

↓

Permission

↓

Retrieval

↓

Prompt Assemble

↓

Token Estimate

↓

LLM

↓

Token Record

↓

Cost Analysis

↓

Statistics
```

---

# Token Type

固定：

```text
Input Token

Output Token

Embedding Token

Cached Token

Reasoning Token（如模型支援）
```

---

# Token Record

每次請求：

固定記錄：

```text
Input

↓

Output

↓

Total

↓

Cost
```

---

# Usage Scope

統計：

```text
Per User

Per Session

Per Project

Per Model

Per Day

Per Month
```

---

# Cost Formula

固定：

```text
Input Cost

+

Output Cost

+

Embedding Cost

=

Total Cost
```

---

# Model Record

保存：

```text
Model

Version

Provider

Input Price

Output Price
```

---

# User Quota

Guest：

```text
每日 Token 上限
```

---

Free：

```text
每月 Token 上限
```

---

Member：

```text
會員方案限制
```

---

Teacher：

```text
高額度
```

---

Admin：

```text
Unlimited
```

---

# Token Optimization

固定：

```text
Metadata Filter

↓

Top-K Optimization

↓

Prompt Compression

↓

Conversation Summary

↓

Cache Reuse
```

---

# Cache Policy

可重複使用：

```text
Embedding

Metadata

Prompt Template

Static Knowledge
```

---

# Cost Alert

通知條件：

```text
80%

90%

100%
```

---

# Cost Statistics

統計：

```text
Daily

Weekly

Monthly

Yearly
```

---

# Report

固定產生：

```text
User Cost

Project Cost

Model Cost

Total Cost
```

---

# Token Log

```json
{
  "request_id":"",
  "user_id":"",
  "model":"",
  "input_tokens":0,
  "output_tokens":0,
  "total_tokens":0,
  "estimated_cost":0,
  "timestamp":""
}
```

---

# Cost Dashboard

顯示：

```text
Today's Tokens

Monthly Tokens

Monthly Cost

Average Cost

Top Users

Top Projects
```

---

# Validation

□ Input Token

□ Output Token

□ Cost

□ Quota

□ Statistics

□ Alert

全部完成。

---

# Deployment

支援：

- OpenAI API
- Azure OpenAI
- Anthropic
- Google Gemini
- 本地 LLM（可擴充）

---

# 關聯

Ops1206_KnowledgeSynchronization

Ops1208_UsageAnalytics

Engine1001_Retrieval

Engine1004_PromptAssembler
