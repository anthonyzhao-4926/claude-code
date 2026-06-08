## Claude Code组件

学习使用claude code，有必要先从宏观角度认识一下 claude 有哪些组件。后续的学习也是学习每个组件如何使用，如何用好。

![claude-code-components.drawio](assets/claude-code-components.drawio.png)

### 核心指令层

| 组件 | 说明 | 特点 |
|-----|------|------|
| **System Prompt** | 内置基础行为指令 | Anthropic 定义，不可直接修改，提供默认行为 |
| **CLAUDE.md** | 项目级 / 用户级自定义指令 | 优先级高于 System Prompt，可用于覆盖默认行为 |
| **Memory** | 跨会话持久记忆 | 存于 ~/.claude/.../memory/，支持用户、项目、反馈等多种类型 |

### 工具与能力层

| 组件 | 说明 | 包含内容 |
|-----|------|---------|
| **System Tools** | 内置工具系统 | Read · Write · Edit · Bash · Glob · Grep 等 |
| **MCP Servers** | 通过 MCP 接入外部工具 | 数据库 · API · 飞书 · 等第三方服务 |
| **Skills** | 可复用能力模块 | drawio · lark-doc · deep-research 等，按需加载 |
| **Custom Agents** | 专用子代理 | doc-updater · Explore · Plan · code-reviewer 等 |

### 自动化与配置层

| 组件 | 说明 | 配置文件 |
|-----|------|---------|
| **Hooks** | 事件触发时执行特定动作 | pre/post-tool · session-start 等生命周期钩子 |
| **Settings** | 系统全局配置 | settings.json / settings.local.json |
| **Keybindings** | 自定义快捷键 | ~/.claude/keybindings.json |

### 上下文层

| 组件 | 说明 | 用途 |
|-----|------|------|
| **Messages** | 当前对话消息历史 | 记录对话中所有输入与输出 |
| **Tasks** | 会话内任务跟踪 | TaskCreate / Update，追踪工作进度 |
| **Plans** | 实现计划与方案 | EnterPlanMode 生成，用于复杂任务设计 |
| **Scheduled Tasks** | 定时任务配置 | scheduled_tasks.json，支持 cron 定时执行 |
| **Workflows** | 多 Agent 编排脚本 | 复杂多步骤任务的并行编排 |

