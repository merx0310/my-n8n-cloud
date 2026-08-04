---
id: Engine1006
title: Query Router Engine（查詢路由引擎）
category: AIEngine
version: 3.0
priority: 10005
layer: System
tags:
  - QueryRouter
  - Intent
  - Routing
  - AIEngine
  - n8n
related:
  - Engine1001
  - Engine1002
  - Engine1005
  - Engine1007
---

# 建立目的

統一所有使用者查詢路由。

---

# Engine流程

```text
User Question

↓

Normalize

↓

Intent Detection

↓

Permission Check

↓

Knowledge Route

↓

Retrieval Engine

↓

Master Engine
```

---

# Intent 類型

固定：

```text
Personality

Dream

LifeCycle

FiveBlessings

Knowledge

TeacherReport

System

General
```

---

# Route Table

## Personality

Route：

```text
500_Star
```

---

## Dream

Route：

```text
600_Prompt
```

---

## LifeCycle

Route：

```text
800_LifeCycleAnalysis
```

---

## FiveBlessings

Route：

```text
700_FiveBlessings
```

---

## TeacherReport

Route：

```text
900_MasterIntegration
```

---

## Knowledge

Route：

```text
100_Algorithm

200_Number

300_MissingNumber

400_FiveElements
```

---

## System

Route：

```text
1000_AIEngine
```

---

## General

Route：

```text
Master Search
```

---

# Query Normalize

處理：

- 全形／半形
- 大小寫
- 空白
- 換行
- 特殊符號

---

# Intent Detection

依據：

- 關鍵字
- 對話上下文
- Memory
- AI分類

共同判定。

---

# Multi Intent

若同時包含多個意圖：

例如：

```text
人格

+

流年
```

Route：

```text
500

+

800

↓

900
```

---

# Unknown Intent

找不到分類：

Route：

```text
General

↓

Master Search
```

---

# Permission Filter

Route前：

必須先執行：

```text
Engine1002
```

---

# Metadata Filter

Route後：

執行：

```text
Engine1005
```

---

# Retrieval

最後：

交由：

```text
Engine1001
```

完成搜尋。

---

# Teacher Mode

若：

TeacherReport

固定：

加入：

```text
900_MasterIntegration

+

Engine1010
```

---

# Output

```json
{
  "intent":"LifeCycle",
  "route":[
    "800_LifeCycleAnalysis"
  ],
  "permission":"Teacher",
  "engine":"Engine1001"
}
```

---

# Validation

□ Query Normalize

□ Intent完成

□ Route完成

□ Permission完成

□ Metadata完成

□ Retrieval完成

---

# Engine Output

Route Result

↓

Retrieval Engine

↓

Prompt Engine

---

# 關聯

Engine1001_Retrieval

Engine1002_Permission

Engine1005_Metadata

Engine1007_Fallback
