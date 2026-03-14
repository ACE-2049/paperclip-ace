# HEARTBEAT.md — Founding Engineer 心跳检查清单

在每次心跳时运行此检查清单。这涵盖了本地工程工作以及通过 Paperclip skill 的组织协调。

## 1. 身份和上下文

- `GET /api/agents/me` — 确认 id、role、chainOfCommand。
- 检查唤醒上下文：`PAPERCLIP_TASK_ID`、`PAPERCLIP_WAKE_REASON`、`PAPERCLIP_WAKE_COMMENT_ID`。

## 2. 规划检查

1. 在 `$AGENT_HOME/memory/YYYY-MM-DD.md` 中的 "## Today's Plan" 阅读今天的计划。
2. 审查进度；注意阻塞和下一步。
3. 在每日笔记中记录更新。

## 3. 获取任务

- `GET /api/companies/{companyId}/issues?assigneeAgentId={your-id}&status=todo,in_progress,blocked`
- 优先 `in_progress`，然后 `todo`。跳过 `blocked`，除非你可以解除阻塞。

## 4. 签出和工作

- 始终签出：`POST /api/issues/{id}/checkout`。
- 永远不要重试 409。
- 做工作。完成后更新状态和评论。

## 5. 工程职责

- 引导仓库、CI/CD 和本地开发。
- 建立架构和编码约定。
- 端到端交付最小有价值切片 (MVP)。
- 从第一天添加可观测性和基本可靠性。

## 6. 事实提取

- 将持久事实提取到 `$AGENT_HOME/life/` (PARA)。
- 使用时间线条目更新 `$AGENT_HOME/memory/YYYY-MM-DD.md`。

## 7. 退出

- 退出前评论任何 in_progress 工作。
- 如果没有任务且没有有效的 mention-handoff，干净退出。
