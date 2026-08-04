---
id: Engine1008
title: Conversation Memory Engine（對話記憶引擎）
category: AIEngine
version: 3.0
priority: 10007
layer: System
tags:
  - Memory
  - Conversation
  - Context
  - AIEngine
  - n8n
related:
  - Engine1001
  - Engine1002
  - Engine1004
  - Engine1007
  - Engine1009
---

# 建立目的

統一管理所有 AI 對話記憶。

---

# Engine流程

```text
User Message

↓

Memory Extract

↓

Memory Classify

↓

Memory Store

↓

Memory Retrieve

↓

Prompt Assemble

↓

LLM
```

---

# Memory Type

固定：

```text
Session

Profile

Preference

Project

Knowledge

Temporary
```

---

# Session

保存：

本次對話。

結束後：

自動清除。

---

# Profile

保存：

使用者固定資料。

例如：

- 姓名
- 出生日期
- 生命密碼
- 主性格

---

# Preference

保存：

使用者偏好。

例如：

- 老師版
- 繁體中文
- Markdown
- JSON

---

# Project

保存：

長期專案。

例如：

- ShuYi-RAG
- LINE AI
- n8n
- Supabase

---

# Knowledge

保存：

本次引用：

Knowledge ID。

例如：

```text
KB0812

KB0903

Engine1004
```

---

# Temporary

保存：

暫時資料。

TTL：

24小時。

自動刪除。

---

# Retrieval

Prompt組裝前：

固定：

```text
Profile

↓

Preference

↓

Project

↓

Session

↓

Temporary
```

---

# Session Limit

Guest：

5

Free：

10

Member：

20

Teacher：

50

Admin：

Unlimited

---

# Project Memory

每個 Project

固定：

```json
{
  "project_id":"",
  "project_name":"",
  "status":"",
  "last_update":""
}
```

---

# Profile JSON

```json
{
  "user_id":"",
  "name":"",
  "birthday":"",
  "personality":"",
  "dream":""
}
```

---

# Preference JSON

```json
{
  "language":"zh-TW",
  "output":"markdown",
  "mode":"Teacher"
}
```

---

# Memory Priority

固定：

```text
Profile

↓

Preference

↓

Project

↓

Session

↓

Temporary
```

---

# Expire Policy

Session：

聊天結束

Temporary：

24hr

Knowledge：

7天

Project：

永久

Profile：

永久

Preference：

永久

---

# Validation

□ Memory分類

□ Priority完成

□ Retrieval完成

□ Expire完成

---

# Engine Output

```json
{
  "profile":{},
  "preference":{},
  "project":{},
  "session":[],
  "temporary":[]
}
```

---

# 關聯

Engine1001_Retrieval

Engine1004_PromptAssembler

Engine1007_Fallback

Engine1009_VersionManager
