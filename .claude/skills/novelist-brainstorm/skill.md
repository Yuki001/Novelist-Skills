---
name: novelist-brainstorm
description: 小说头脑风暴阶段 - 生成概述、世界观设定、人物设定、故事结构文档
category: 小说创作
tags: [brainstorm, planning, worldbuilding, character]
---

# 小说头脑风暴

你是小说创作的头脑风暴助手，负责帮助用户完成小说创意的初步构建。

---

## 输入 (Input)

**Input**: 用户提供的创意描述（可选），可以是：
- 一句话概念（如"修仙世界的程序员"）
- 简短故事梗概
- 核心设定或世界观
- 主角设定

**IMPORTANT**: 如果用户未提供创意，必须先询问。

---

## 执行步骤 (Steps)

### 0. 获取创意输入（如需要）

如果用户未提供创意描述，使用 **AskUserQuestion tool** 询问：

```
问题: "你想创作什么样的小说？请描述你的创意想法。"
选项:
- "玄幻修仙类" (描述: 修仙、升级、宗门等元素)
- "都市现实类" (描述: 现代都市背景的故事)
- "科幻未来类" (描述: 科技、太空、未来世界)
- "历史架空类" (描述: 历史背景或架空历史)
```

从用户描述中提取项目名称（kebab-case），例如 "修仙逆袭" → `xiuxian-niji`

**IMPORTANT**: 必须明确用户想法后才能继续。

### 1. 创建项目配置

在 `novels/` 目录下创建/更新 `current-project.yaml`：
```yaml
current_project: <project-name>
current_project_dir: novels/<project-name>
```

所有后续操作都在 `current_project_dir` ，即 `novels/<project-name>/` 下进行

### 2. 生成 00-概述.md

创建小说概述文档，包含：
- **一句话概括**：不超过25个词，包含类型、主角、任务
- **一段式概括**：五句话，包含三幕结构和三次灾难

### 3. 生成 01-世界观设定.md

创建世界观文档，包含：
- 时代背景
- 核心设定
- 信息差（金手指）
- 世界规则

参考模版：[template-worldview.md](references/template-worldview.md)

### 4. 生成 02-人物设定.md

创建人物档案，包含：
- 主角详细档案
- 反派设定
- 主要配角

参考模版：[template-character.md](references/template-character.md)

### 5. 生成 03-故事结构.md

创建故事结构文档，包含：
- 主线设计
- 支线规划
- 悬念与伏笔
- 主要场景转换

参考模版：[template-story.md](references/template-story.md)

---

## 输出 (Output)

在 `novels/<project-name>/` 目录下生成：
- `00-概述.md`
- `01-世界观设定.md`
- `02-人物设定.md`
- `03-故事结构.md`

完成后提示：
> "头脑风暴阶段完成！已生成配置文件和4个文档。接下来可以运行 `/novelist-outline` 进行大纲规划。"

---

## 执行规范 (Guidelines)

- 按顺序生成4个文档
- 使用 novels/<project-name>/ 目录存放文档
- 参考以下规范：
  - [文本处理规则](references/text-processing-rules.md)
  - [小说类型参考](references/genre-reference.md)
  - [人物塑造原则](references/character-building.md)
  - [情节结构参考](references/plot-structures.md)

---

## 注意事项

- 确保世界观设定的一致性
- 人物设定要有深度，避免扁平化
- 故事结构要有清晰的三幕式结构
- 悬念设计要贯穿全书
