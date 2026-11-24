# AGENTS.md

当前协作：Project Orchestrator v2。先读 README、docs/STATE.md、docs/ROUTING.md 和现有 Issue/PR。Chat 决策和终审；单主 Codex 在授权内开发、自主修复普通问题，安排子 Agent 时保持写入所有权。不要由此推定任何生产、发布、凭据、付费或上游版权授权。首次引入不检查 CI；只有需要真实 CI 或合并门禁要求时才核查。

## Project Orchestrator v2.5 治理规范（source commit `e753fa739a4b2c8940735c4788518c76625d73b1`）

- **执行引擎与并发**：支持单主 **OpenAI Codex**（`agent:codex`）或 **Google Antigravity**（`agent:antigravity`），通过 `task-lease/v1` 互斥；主 Agent 按运行环境实际支持的最大并发数（`max_supported`，不设固定上限）协调隔离子 Agent；**ChatGPT**（`agent:chat`）负责规划与 exact-HEAD 独立终审，严禁自我批准。
- **历史兼容**：旧 WorkBuddy / v1.4 / v2.0 描述保留只读归档，新任务路由至 `agent:codex` 或 `agent:antigravity`。
- **仓库权威与简短入口**：完整任务规格、授权范围、验收标准与证据存放在 GitHub Issue/PR；用户仅需提供简短入口指令；结果与证据回写仓库。
- **分级预授权**：Tier 1 常规工程与普通缺陷在单工作包内自主交付（不影响核心功能与数据安全的极低概率边界问题可记录暂缓）；Tier 2 低风险自动合并默认关闭（`tier2_low_risk_merge: false`）；Tier 3 高风险、付费、生产、权限及敏感数据变更须经 Chat 明确用户授权。
- **CI 策略**：仅当任务实际使用 CI 或 CI 为当前门禁时核查可用性及 CircleCI 备选，不修改 workflow 规避真实 required checks。
- **阶段自动化边界**：当前基线为 `STAGE_ACCEPTED_READ_ONLY_MANUAL_HANDOFF / AUTONOMOUS_DISPATCH_BLOCKED`（`PREPARED_NOT_DISPATCHED`）；准备好的文档/评论不自动唤醒代理，未安装本地调度器，不启用实验性 `execution-dispatch` 或自动合并。
