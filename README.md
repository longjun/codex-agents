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

将仓库克隆到任意目录，然后通过符号链接接入 Codex 配置目录：

```bash
git clone git@github.com:longjun/codex-agents.git
cd codex-agents
repo_dir="$(pwd -P)"

mkdir -p "$HOME/.codex/docs"
ln -s "$repo_dir/AGENTS.md" "$HOME/.codex/AGENTS.md"
ln -s "$repo_dir/docs/agents" "$HOME/.codex/docs/agents"
```

创建链接前应先备份或移除目标位置已有的同名文件和目录。

## 维护

在仓库目录中直接修改规则，并保持一次提交只包含一个明确变更：

```bash
git add AGENTS.md README.md docs/agents
git commit -m "docs: update agent rules"
git push
```

技术规则的组织方式和维护约束见 [`docs/agents/README.md`](docs/agents/README.md)。
