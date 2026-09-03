# Rust Rules

## 适用场景

- 修改 Rust 源码、Cargo 配置或 Rust 编译行为

## 必须

- 遵循现有 edition、MSRV、feature 和 workspace 边界
- 用类型表达所有权和失败路径，不用 `unwrap` 或 `expect` 处理可恢复错误
- `unsafe` 必须有必要性说明、最小作用域和可验证的不变量
- 保持公开 API 和序列化格式兼容，除非任务明确要求破坏性修改

## 建议

- 优先借用而不是无必要克隆，但不要以可读性为代价追求零拷贝
- 错误类型保持有上下文且适合调用方处理
- feature 保持正交，不引入无必要的默认依赖

## 避免

- 为绕过借用检查器而滥用 `clone`、全局锁或复杂生命周期
- 宽泛使用 `Box<dyn Error>` 掩盖稳定错误边界
- 在异步代码中持锁跨越 `.await`

## 验证

- 运行 `cargo fmt --check`、相关测试和项目既有 clippy 检查
