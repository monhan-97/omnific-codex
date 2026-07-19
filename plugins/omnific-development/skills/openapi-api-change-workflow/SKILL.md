---
name: openapi-api-change-workflow
description: 在新增、修改、重构或审查端点、路由、DTO、schema、服务、认证、响应和错误时，保持 REST API 实现与 OpenAPI 3.1 契约同步。适用于 Koa API 工作，并应先调用仓库要求的 OpenAPI 专项 Skill。
---

# OpenAPI API 变更工作流

1. 读取当前仓库和对应目录中的 `AGENTS.md`。
2. 生成或修改代码前，调用仓库要求的 OpenAPI Skill。
3. 定位端点对应的路由注册、handler、请求和响应 DTO、校验 schema、服务行为、认证、错误映射以及 OpenAPI 文档。
4. 编辑前明确目标契约，并确保所有实现层面保持一致。
5. 保持仓库既有的路由架构。在 Koa 项目中，将全局前缀、路由模块注册和本地子路由前缀保留在各自职责层中。
6. 当架构使用子路由时，不要在业务路由模块中修改父路由器的 prefix。
7. 验证成功响应、状态码、header、校验失败、认证失败、领域错误和文档 schema。
8. 运行仓库验证命令以及 OpenAPI 校验或生成命令。
