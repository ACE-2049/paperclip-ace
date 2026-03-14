# 2026-03-14 — Founding Engineer 计划

## 目标
- 通过 para-memory-files 保持 agent 记忆一致。
- 验证 Paperclip 控制平面连接并获取分配的 issues。
- 为第一个任务（一旦分配）准备最小 E2E 交付路径。

## 步骤
1) 运行 HEARTBEAT 检查清单并更新每日笔记。
2) 使用 paperclip skill 调用 `GET /api/agents/me` 和 issues 列表。
3) 如果任务存在：签出最高优先级 issue 并开始。
4) 如果没有任务：确保仓库引导和约定准备就绪。

## 状态
- 等待任务分配；环境已准备。

## 备注
- 计划存放在 `plans/` 下，并在适用时被较新的日期文件取代。
