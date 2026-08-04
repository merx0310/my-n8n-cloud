---
id: Engine1004
title: Prompt Assembler Engine（Prompt 組裝引擎）
category: AIEngine
version: 3.0
priority: 10003
layer: System
tags:
  - Prompt
  - Assembler
  - AIEngine
  - n8n
  - OpenAI
related:
  - Engine1001
  - Engine1002
  - Engine1003
  - Engine1005
---

# 建立目的

統一組裝所有 AI Prompt。

---

# Engine流程

```text
User Input

↓

Intent Detection

↓

Permission Check

↓

Retrieval Engine

↓

Knowledge Merge

↓

Prompt Assemble

↓

Master Prompt

↓

LLM
```

---

# Prompt 結構

固定：

```text
System Prompt

+

Role Prompt

+

Knowledge Context

+

Conversation Memory

+

User Question
```

---

# System Prompt

固定載入：

```text
Engine1010_MasterEngine
```

---

# Role Prompt

Guest：

```text
GuestPrompt
```

Free：

```text
FreePrompt
```

Member：

```text
MemberPrompt
```

Teacher：

```text
TeacherPrompt
```

Admin：

```text
AdminPrompt
```

---

# Knowledge Context

來源：

```text
Engine1001
```

載入：

Top-K Knowledge。

---

# Conversation Memory

固定：

最近

5

輪對話。

Teacher：

20

輪。

---

# User Question

保留：

原始問題。

不得修改。

---

# Assemble 順序

固定：

```text
System

↓

Role

↓

Knowledge

↓

Memory

↓

Question
```

不得改變。

---

# Prompt Template

```text
<System>

<Role>

<Knowledge>

<Memory>

<User>
```

---

# Token Control

Guest：

2K

Free：

4K

Member：

8K

Teacher：

16K

Admin：

Dynamic

---

# Overflow

超過 Token：

依序移除：

```text
Memory

↓

Knowledge

↓

History
```

不得移除：

System Prompt。

---

# Teacher Mode

固定加入：

```text
KB0910

Master Prompt Engine
```

---

# Free Mode

不得加入：

900

1000

知識。

---

# Output

傳送：

完整 Prompt。

不得修改：

User Input。

---

# Validation

□ System 已載入

□ Role 已載入

□ Knowledge 已載入

□ Memory 已載入

□ User 已載入

□ Token 合法

---

# Engine Output

```json
{
  "system": "...",
  "role": "...",
  "knowledge": [],
  "memory": [],
  "user": "...",
  "token": 0
}
```

---

# 關聯

Engine1001_Retrieval

Engine1002_Permission

Engine1003_JSONSchema

Engine1005_Metadata
