# Novelist Skills - 模块化小说创作工具集

基于三位一体·叙事空间创作系统的模块化中文网文创作助手。

## 核心工作流

### 快速启动
```
/novelist:purpose
```
一次性生成所有元信息文档（00-概述 到 06-任务列表）

### 标准创作流程
```
1. /novelist:brainstorm  # 头脑风暴
2. /novelist:outline     # 大纲规划
3. /novelist:write       # 章节写作
4. /novelist:expand-outline  # 扩展大纲（可选）
5. /novelist:memory      # 记忆管理（可选）
```

## Skills 说明

### novelist-brainstorm
生成：00-概述.md, 01-世界观设定.md, 02-人物设定.md, 03-故事结构.md

### novelist-outline
生成：04-大纲.md, 05-细纲.md, 06-任务列表.md

### novelist-write
逐章撰写（3000-5000字），自动更新 07-记忆.md

### novelist-expand-outline
扩展大纲和细纲，添加新章节任务（用于长篇网文）

### novelist-memory
显式更新或重新整理记忆，必要时拆分到 memory/ 目录

### novelist-purpose
快速启动，一次性执行 brainstorm + outline

## 项目结构

```
novels/<project-name>/
  00-概述.md
  01-世界观设定.md
  02-人物设定.md
  03-故事结构.md
  04-大纲.md
  05-细纲.md
  06-任务列表.md
  07-记忆.md
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
/novelist:purpose
```
按提示输入创意，系统将生成所有元信息文档。

开始写作：
```
/novelist:write
```
系统自动读取任务列表，撰写下一章节。
