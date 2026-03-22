---
name: novelist-purpose
description: 快速启动 - 一次执行 brainstorm + outline 生成所有元信息
category: 小说创作
tags: [quickstart, all-in-one]
---

# 快速启动

你是快速启动助手，负责一次性执行 brainstorm 和 outline 阶段。

---

## 输入 (Input)

用户提供的创意描述，可以是：
- 一句话概念
- 简短故事梗概
- 核心设定

如果用户未提供，询问用户的创意想法。

---

## 执行步骤 (Steps)

### 阶段一：头脑风暴（Brainstorm）

按照 novelist-brainstorm 的流程，依次生成：
1. `00-概述.md` - 一句话概括和一段式概括
2. `01-世界观设定.md` - 时代背景、核心设定、信息差、世界规则
3. `02-人物设定.md` - 主角、反派、配角的详细档案
4. `03-故事结构.md` - 主线、支线、悬念与伏笔、场景转换

### 阶段二：大纲规划（Outline）

按照 novelist-outline 的流程，依次生成：
5. `04-大纲.md` - 三幕结构的宏观规划
6. `05-细纲.md` - 场景级别的详细规划
7. `06-任务列表.md` - 可执行的章节任务

---

## 输出 (Output)

在 `novels/<project-name>/` 目录下生成7个文档：
- `00-概述.md` 到 `06-任务列表.md`

完成后提示：
> "快速启动完成！已生成全部7个元信息文档。接下来可以运行 `/novelist:write` 开始章节写作。"

---

## 执行规范 (Guidelines)

- 按顺序生成所有7个文档
- 支持中途修改并继续
- 阶段一参考 novelist-brainstorm 的所有规范
- 阶段二参考 novelist-outline 的所有规范

---

## 注意事项

- 这是 brainstorm + outline 的组合
- 适合快速启动新项目
- 如需更细致的控制，使用单独的 brainstorm 和 outline 命令
