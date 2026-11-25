> **当前有效路由：Project Orchestrator v2.5**（`e753fa739a4b2c8940735c4788518c76625d73b1`）。新任务由 `agent:chat`（ChatGPT）负责规划、边界决策与 exact-HEAD 独立终审；执行由单主 `agent:codex` 或 `agent:antigravity`（`task-lease/v1` 互斥）按 `max_supported` 并发协调隔离子 Agent 完成，并自主整改 Tier 1 普通工程问题（不得自我批准）。已停用的 WorkBuddy 仅保留历史归档；Runner/CI 仅在任务实际使用或门禁需要时验证（Actions 外部阻塞时可评估已授权 CircleCI，不绕过 required checks）。完整要求存 GitHub 仓库、用户仅用简短入口、结果回写仓库；Tier 2 自动合并默认关闭，Tier 3 高风险/生产/权限/数据变更须用户明确授权；当前阶段边界为 `STAGE_ACCEPTED_READ_ONLY_MANUAL_HANDOFF / AUTONOMOUS_DISPATCH_BLOCKED`。

# SmsCodeHelper — Project Orchestrator v2 路由

- ChatGPT 负责需求、授权、独立审核与合并决策；单主 Codex 在已授权工作包内负责完整交付、普通问题自主整改，可以协调隔离的子 Agent。
- 不再启用 WorkBuddy 新任务路由；Runner/CI 仅在项目真实需要 CI 时提供独立验证。
- 必需 CI 无法使用 GitHub Actions 时，可评估已授权的 CircleCI；不得跳过当前 GitHub required checks 或扩展第三方权限。
- GitHub Issue/PR/最新 HEAD 是真实进度依据。原有上游版权/许可证、数据、平台和软件功能全部保持；引入契约不自动部署、启用服务或要求新增开发。

上游 v2 规范：https://github.com/yrgpcn/project-orchestrator/commit/c1838a3e67b01ff5e1fc756fdd594270391af5d5
