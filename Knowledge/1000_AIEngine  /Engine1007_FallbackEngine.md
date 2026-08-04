---
id: Engine1007
title: Fallback Engine（降級處理引擎）
category: AIEngine
version: 3.0
priority: 10006
layer: System
tags:
  - Fallback
  - ErrorHandling
  - Recovery
  - AIEngine
  - n8n
related:
  - Engine1001
  - Engine1002
  - Engine1006
  - Engine1008
---

# 建立目的

統一所有 AI 異常與降級處理流程。

---

# Engine流程

```text
User Request

↓

Query Router

↓

Retrieval

↓

Prompt Assemble

↓

LLM

↓

Success

↓

Output

或

Error

↓

Fallback

↓

Recovery

↓

Output
```

---

# Error Type

固定：

```text
KnowledgeNotFound

PermissionDenied

RetrievalFailed

PromptOverflow

LLMTimeout

InvalidResponse

SystemError
```

---

# KnowledgeNotFound

處理：

```text
General Search

↓

Top-K=3

↓

重新 Retrieval
```

---

# PermissionDenied

處理：

```text
Permission Check

↓

回傳權限提示

↓

停止
```

---

# RetrievalFailed

處理：

```text
重新搜尋

↓

降低 Filter

↓

Top-K=3
```

最多：

3次。

---

# PromptOverflow

處理：

依序移除：

```text
Memory

↓

History

↓

Low Priority Knowledge
```

保留：

```text
System Prompt

Role Prompt

User Question
```

---

# LLMTimeout

處理：

```text
Retry

↓

等待3秒

↓

重新送出
```

最多：

2次。

---

# InvalidResponse

處理：

```text
重新 Assemble Prompt

↓

重新呼叫 LLM
```

---

# SystemError

處理：

```text
Log

↓

Error ID

↓

Admin Notice

↓

停止
```

---

# Retry Policy

Knowledge：

3次

LLM：

2次

System：

1次

---

# Recovery Order

固定：

```text
Retry

↓

Reduce Context

↓

General Search

↓

Permission Check

↓

Stop
```

---

# User Response

Permission：

```text
目前權限不足，請升級會員後使用完整功能。
```

Knowledge：

```text
目前知識庫沒有找到符合的內容。
```

Timeout：

```text
系統忙碌中，請稍後再試。
```

System：

```text
系統發生異常，請稍後重新操作。
```

---

# Error Log

固定：

```json
{
  "error_id":"",
  "engine":"Engine1007",
  "type":"",
  "step":"",
  "timestamp":"",
  "retry":0
}
```

---

# Validation

□ Error分類完成

□ Retry完成

□ Recovery完成

□ Log完成

---

# Engine Output

```json
{
  "status":"fallback",
  "type":"RetrievalFailed",
  "retry":2,
  "result":"success"
}
```

---

# 關聯

Engine1001_Retrieval

Engine1002_Permission

Engine1006_QueryRouter

Engine1008_ConversationMemory
