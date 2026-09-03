# Next.js Rules

## 适用场景

- 修改 Next.js App Router、Pages Router、route handler、middleware 或框架配置

## 必须

- 先确认项目使用的 router、Next.js 版本和部署 runtime
- 保持 Server Component 与 Client Component 边界明确，仅在需要浏览器能力或交互状态时使用 `use client`
- 缓存、动态渲染和 revalidation 行为必须显式符合数据新鲜度需求
- server-only 数据、密钥和内部模块不得进入客户端 bundle

## 建议

- 优先在服务端获取数据，减少不必要的客户端瀑布请求
- 使用框架已有 metadata、image、font、navigation 和 error boundary 能力
- route handler 只处理协议边界，业务逻辑按真实复杂度组织

## 避免

- 为消除报错而扩大 `use client` 边界
- 无依据关闭缓存或强制动态渲染
- 在 middleware 中放置重型业务逻辑或不受支持的 runtime 依赖

## 验证

- 执行项目构建，并检查服务端渲染、客户端 hydration、路由和部署 runtime
