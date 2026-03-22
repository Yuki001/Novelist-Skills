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

**Input**: 用户提供的创意描述（可选），可以是：
- 一句话概念
- 简短故事梗概
- 核心设定

**IMPORTANT**: 如果用户未提供创意，必须先询问。

---

## 执行步骤 (Steps)

### 1. 获取创意输入

如果用户未提供创意描述，使用 **AskUserQuestion tool** 询问：

```
问题: "你想创作什么样的小说？请描述你的创意想法。"
选项:
- "玄幻修仙类" (描述: 修仙、升级、宗门等元素)
- "都市现实类" (描述: 现代都市背景的故事)
- "科幻未来类" (描述: 科技、太空、未来世界)
- "其他类型" (描述: 自定义输入)
```

从用户描述中提取项目名称（kebab-case），例如 "修仙逆袭" → `xiuxian-niji`

**IMPORTANT**: 必须明确用户想法后才能继续。

### 2. 执行头脑风暴阶段

使用 **Skill tool** 显式调用 novelist-brainstorm：

```
Skill tool:
  skill: "novelist-brainstorm"
  args: "<用户的创意描述>"
```

这将生成：
- `00-概述.md`
- `01-世界观设定.md`
- `02-人物设定.md`
- `03-故事结构.md`

等待 brainstorm 完成后再继续。

### 3. 执行大纲规划阶段

使用 **Skill tool** 显式调用 novelist-outline：

```
Skill tool:
  skill: "novelist-outline"
  args: ""
```

这将生成：
- `04-大纲.md`
- `05-细纲.md`
- `06-任务列表.md`

等待 outline 完成后再继续。

### 4. 确认完成

验证所有7个文档已生成：
- 检查 `novels/<project-name>/` 目录
- 确认 `00-概述.md` 到 `06-任务列表.md` 都存在

---

## 输出 (Output)

完成后提示：
> "快速启动完成！已生成全部7个元信息文档。接下来可以运行 `/novelist:write` 开始章节写作。"

列出生成的文档位置和简要说明。

---

## 执行规范 (Guidelines)

**Skill Invocation**
- 必须使用 **Skill tool** 显式调用 `novelist-brainstorm` 和 `novelist-outline`
- 不要尝试手动执行这些阶段的逻辑
- 等待每个 skill 完成后再继续下一步

**User Interaction**
- 如果用户输入不明确，使用 **AskUserQuestion tool** 澄清
- 提供预设选项帮助用户快速选择
- 从用户描述中提取合适的项目名称

**Error Handling**
- 如果 brainstorm 失败，不要继续执行 outline
- 如果文档生成不完整，提示用户检查并重试
- 支持中途修改并继续

---

## 注意事项

- 这是 brainstorm + outline 的组合执行器
- 适合快速启动新项目
- 如需更细致的控制，使用单独的 `/novelist:brainstorm` 和 `/novelist:outline` 命令
- 必须按顺序执行：先 brainstorm，后 outline
