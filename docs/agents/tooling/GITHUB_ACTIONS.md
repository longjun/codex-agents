# GitHub Actions Rules

## 适用场景

- 修改 `.github/workflows/`、复用 workflow 或 action 配置

## 必须

- `permissions` 使用最小权限，并优先在 job 级缩小范围
- 第三方 action 固定到项目认可的不可变版本策略
- secret 不输出到日志，不传递给不可信 fork、脚本或 action
- 来自 issue、PR、branch 或 matrix 的内容视为不可信输入，不直接拼接进 shell
- `pull_request_target` 必须避免执行 PR 中的不可信代码

## 建议

- 复用项目现有 setup、cache 和构建命令
- job 保持职责清晰，失败应能直接定位到具体检查
- 对昂贵 workflow 使用合理的 path、branch 或 concurrency 限制

## 避免

- 无必要授予 `write-all`
- 复制粘贴大量相似 workflow 而不使用已有复用机制
- 用 `continue-on-error` 或宽泛条件掩盖必要检查失败

## 验证

- 检查 YAML、权限、触发条件、fork 行为和所有 shell 插值边界
