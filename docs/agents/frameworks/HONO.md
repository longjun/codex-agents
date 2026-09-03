# Hono Rules

## 适用场景

- 修改 Hono 应用、middleware、route、binding 或 handler

## 必须

- 先确认目标 runtime 及其可用 API、绑定和限制
- handler 负责 HTTP 边界，复杂业务逻辑不直接堆积在路由定义中
- middleware 的执行顺序、短路行为和错误传播必须明确
- 环境变量和 runtime binding 使用项目已有类型定义

## 建议

- 使用 Hono 提供的轻量能力，避免为简单 API 引入大型框架层
- 复用共享 validator、错误处理和响应约定，但不制造机械透传
- 将 runtime 特定实现限制在边界模块

## 避免

- 假设所有 Web 标准 API 在所有 runtime 中行为一致
- 在模块全局保存请求级状态
- 在 middleware 中吞掉异常或返回语义不一致的错误

## 验证

- 使用目标 runtime 运行相关测试，并检查 middleware 顺序和错误响应
