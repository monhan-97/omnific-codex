---
name: changesets-package-release
description: 当用户要求发布、升级版本、publish 或验证 npm 包时，使用 Changesets 准备并发布 pnpm workspace 包。检查 npm 已有版本，只为可发布变更创建发布说明，验证构建和测试，逐个发布变更包，并确认 registry 版本。
---

# Changesets 包发布

1. 读取当前仓库的发布说明并检查发生变更的包。
2. 发布前检查每个本地包版本是否已经存在于 npm。
3. 只为存在可发布变更的包添加 Changesets。条目应聚焦功能、依赖影响和破坏性变更。
4. 运行仓库的 Changesets 版本流程，更新版本和 changelog。
5. 提交时将包内变更与共享发布或工具链变更分开。
6. 运行仓库要求的所有发布检查，包括测试和构建。
7. 使用仓库配置的命令逐个发布变更包，通常为 `pnpm publish --access public --no-git-checks`。
8. 无法使用非交互式 npm 认证时，使用经批准的交互式浏览器或二维码认证流程。
9. 使用 `pnpm view <package> version` 验证每个已发布版本。
10. 不要发布没有变更的包。
