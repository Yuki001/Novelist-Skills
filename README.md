# Novelist Skills - 模块化小说创作工具集

基于三位一体·叙事空间创作系统的模块化中文网文创作助手。

## 工作流

### Core 核心流程

创建新小说的标准流程：

```
1. /novelist-purpose       # 快速启动（brainstorm + outline 一次完成）
   或
   /novelist-brainstorm    # 头脑风暴
   /novelist-outline       # 大纲规划

2. /novelist-write         # 章节写作
```

### Expand 扩展流程

长篇网文持续创作：

```
/novelist-expand-brainstorm   # 扩展世界观/人物/故事结构
/novelist-expand-outline      # 扩展大纲和细纲
/novelist-write               # 继续章节撰写
```

**注意**：扩展命令只添加新内容，不修改已有内容。扩展后仍需调用 `/novelist-write` 继续撰写新章节。

### Style 文风流程

设定文风并润色章节：

```
/novelist-style               # 设定文字风格
/novelist-polish              # 润色已有章节
```

**注意**：文风设定后，同样也会影响 `/novelist-write` 输出的风格。

### 其他工具

```
/novelist-memory              # 记忆管理
```

## Skills 说明

### Core 核心命令

**novelist-purpose** - 快速启动，一次性执行 brainstorm + outline

**novelist-brainstorm** - 生成：00-概述.md, 01-世界观设定.md, 02-人物设定.md, 03-故事结构.md

**novelist-outline** - 生成：04-大纲.md, 05-细纲.md, 06-任务列表.md

**novelist-write** - 逐章撰写（3000-5000字），自动更新 07-记忆.md

### Expand 扩展命令

**novelist-expand-brainstorm** - 扩展世界观、人物、故事结构（只添加，不修改已有内容）

**novelist-expand-outline** - 扩展大纲和细纲，添加新章节任务（只添加，不修改已有内容）

### Style 文风命令

**novelist-style** - 根据用户需求与参考设定文字风格，生成 08-文字风格.md

**novelist-polish** - 根据文风设定润色已有章节，保持情节不变

### 其他命令

**novelist-memory** - 显式更新或重新整理记忆，必要时拆分到 memory/ 目录

## 项目结构

```
novels/
  current-project.yaml          # 当前项目配置
  <project-name>/
    00-概述.md
    01-世界观设定.md
    02-人物设定.md
    03-故事结构.md
    04-大纲.md
    05-细纲.md
    06-任务列表.md
    07-记忆.md
    08-文字风格.md
    memory/
      角色状态.md
      悬念追踪.md
    chapters/
      第01章.md
      第02章.md
```

## 使用示例

创建新小说项目：
```
/novelist-purpose
```
按提示输入创意，系统将生成所有元信息文档。

开始写作：
```
/novelist-write
```
系统自动读取任务列表，撰写下一章节。

设定文风与润色：
```
/novelist-style
```
输入文风需求（如：简洁明快、古典优雅），系统生成文风设定文档。

```
/novelist-polish
```
对已有章节进行文风润色，可指定章节编号或润色最新章节。
