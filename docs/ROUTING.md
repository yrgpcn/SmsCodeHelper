# SmsCodeHelper — Project Orchestrator v2 路由

- ChatGPT 负责需求、授权、独立审核与合并决策；单主 Codex 在已授权工作包内负责完整交付、普通问题自主整改，可以协调隔离的子 Agent。
- 不再启用 WorkBuddy 新任务路由；Runner/CI 仅在项目真实需要 CI 时提供独立验证。
- 必需 CI 无法使用 GitHub Actions 时，可评估已授权的 CircleCI；不得跳过当前 GitHub required checks 或扩展第三方权限。
- GitHub Issue/PR/最新 HEAD 是真实进度依据。原有上游版权/许可证、数据、平台和软件功能全部保持；引入契约不自动部署、启用服务或要求新增开发。

上游 v2 规范：https://github.com/yrgpcn/project-orchestrator/commit/c1838a3e67b01ff5e1fc756fdd594270391af5d5
