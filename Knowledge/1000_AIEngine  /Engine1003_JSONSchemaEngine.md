---
id: Engine1003
title: JSON Schema Engine（標準輸出引擎）
category: AIEngine
version: 3.0
priority: 10002
layer: System
tags:
  - JSON
  - Schema
  - API
  - n8n
  - AIEngine
related:
  - Engine1001
  - Engine1002
  - Engine1004
---

# 建立目的

統一所有 AI 回傳 JSON 格式。

---

# Engine流程

```text
Master Engine

↓

Response

↓

JSON Builder

↓

Validation

↓

Output
```

---

# Output Format

固定：

```json
{
  "status": "",
  "role": "",
  "intent": "",
  "module": [],
  "knowledge": [],
  "response": {},
  "metadata": {},
  "timestamp": ""
}
```

---

# status

允許：

```text
success

warning

error
```

---

# role

允許：

```text
Guest

Free

Member

Teacher

Admin
```

---

# intent

例如：

```text
Personality

Dream

LifeCycle

FiveBlessings

Knowledge

TeacherReport
```

---

# module

例如：

```json
[
  "500_Star",
  "600_Prompt",
  "800_LifeCycleAnalysis"
]
```

---

# knowledge

例如：

```json
[
  "KB0508",
  "KB0605",
  "KB0812"
]
```

---

# response

固定：

```json
{
  "title":"",
  "summary":"",
  "content":"",
  "suggestions":[]
}
```

---

# suggestions

例如：

```json
[
  "每天閱讀10分鐘",
  "每週回顧一次目標",
  "每月整理一次學習成果"
]
```

---

# metadata

固定：

```json
{
  "version":"3.0",
  "engine":"MasterEngine",
  "permission":"Teacher",
  "top_k":20
}
```

---

# timestamp

ISO8601

例如：

```text
2026-08-04T20:30:00+08:00
```

---

# Teacher Output

```json
{
  "status":"success",
  "role":"Teacher",
  "intent":"TeacherReport",
  "module":[
    "500_Star",
    "600_Prompt",
    "700_FiveBlessings",
    "800_LifeCycleAnalysis",
    "900_MasterIntegration"
  ],
  "knowledge":[
    "KB0508",
    "KB0605",
    "KB0707",
    "KB0815",
    "KB0910"
  ],
  "response":{
    "title":"老師版完整人格解析",
    "summary":"人格整合完成",
    "content":"...",
    "suggestions":[]
  },
  "metadata":{
    "version":"3.0",
    "engine":"MasterEngine",
    "permission":"Teacher",
    "top_k":20
  },
  "timestamp":"AUTO"
}
```

---

# Validation

□ JSON格式正確

□ 必填欄位完整

□ role合法

□ intent合法

□ module存在

□ knowledge存在

□ metadata完整

---

# Engine Output

僅輸出合法 JSON。

不得輸出非法格式。

---

# 關聯

Engine1001_Retrieval

Engine1002_Permission

Engine1004_PromptAssembler
