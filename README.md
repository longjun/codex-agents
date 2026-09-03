# Codex Agent Rules

Codex 全局开发规范与按任务路由加载的技术规则集合。

## 内容

- `AGENTS.md`：全局工程原则、执行规范和任务路由协议
- `docs/agents/languages/`：语言规则
- `docs/agents/frameworks/`：框架规则
- `docs/agents/platforms/`：平台规则
- `docs/agents/domains/`：业务与系统领域规则
- `docs/agents/tooling/`：测试、容器和 CI 等工具规则

## 本地接入

仓库默认放在 `~/Workspace/codex-agents`，并通过符号链接接入 Codex 配置目录：

```bash
ln -s ~/Workspace/codex-agents/AGENTS.md ~/.codex/AGENTS.md
mkdir -p ~/.codex/docs
ln -s ~/Workspace/codex-agents/docs/agents ~/.codex/docs/agents
```

创建链接前应先备份或移除目标位置已有的同名文件和目录。

## 维护

直接在本仓库中修改规则，并保持一次提交只包含一个明确变更：

```bash
cd ~/Workspace/codex-agents
git add AGENTS.md README.md docs/agents
git commit -m "docs: update agent rules"
git push
```

技术规则的组织方式和维护约束见 [`docs/agents/README.md`](docs/agents/README.md)。
