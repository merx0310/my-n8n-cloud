---
id: Engine1002
title: Permission Engine（權限控制引擎）
category: AIEngine
version: 3.0
priority: 10001
layer: System
tags:
  - Permission
  - Membership
  - Teacher
  - Free
  - AIEngine
related:
  - Engine1001
  - Engine1003
---

# 建立目的

統一管理所有會員權限。

---

# 支援身份

```text
Guest

↓

Free

↓

Member

↓

Teacher

↓

Admin
```

---

# Engine流程

```text
User

↓

Identify Role

↓

Permission Check

↓

Knowledge Scope

↓

Response Scope

↓

Output
```

---

# Guest

允許：

- 基本介紹
- 系統說明
- 操作教學

禁止：

- 人格解析
- 流年
- 老師版

---

# Free

允許：

- 基本人格摘要
- 單一知識說明
- 一項建議

限制：

- 不融合模組
- 不查900
- 不查Teacher內容

---

# Member

允許：

- 主性格
- 本源夢想
- 五行
- 缺數
- 五福
- 流年

限制：

- 不啟動Master Engine

---

# Teacher

允許：

- 全知識庫
- Master Integration
- 全模組融合
- 完整人格報告
- 年度解析
- AI老師模式

---

# Admin

允許：

- 全部權限
- Engine設定
- Prompt設定
- Metadata
- Version
- Debug

---

# Knowledge Scope

## Guest

```text
000
100
```

---

## Free

```text
100

200

300
```

---

## Member

```text
100

200

300

400

500

600

700

800
```

---

## Teacher

```text
000

100

200

300

400

500

600

700

800

900

1000
```

---

# Prompt控制

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

# Retrieval限制

Guest：

TopK = 2

Free：

TopK = 5

Member：

TopK = 10

Teacher：

TopK = 20

Admin：

Dynamic

---

# Master Engine

Guest：

禁止

Free：

禁止

Member：

禁止

Teacher：

允許

Admin：

允許

---

# JSON

```json
{
  "role":"Teacher",
  "permission":"full",
  "master_engine":true,
  "top_k":20
}
```

---

# Output Policy

Guest：

摘要

Free：

簡易解析

Member：

完整模組

Teacher：

老師版完整融合

Admin：

Debug模式

---

# Validation

□ Role

□ Permission

□ Prompt

□ Retrieval

□ Master Engine

全部通過才允許回答。

---

# 關聯

Engine1001_Retrieval

Engine1003_JSONSchema

Engine1010_MasterEngine
