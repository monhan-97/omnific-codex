---
name: conventional-commit-workflow
description: 当用户输入 /cm、cm、commit msg，或要求提交暂存变更时，准备并创建 Conventional Commits。检查暂存区，按 package 或功能边界分组，保留未暂存工作，并按照用户或仓库规则决定是否推送；允许推送时最多尝试 5 次。
---

# Conventional Commit 工作流

1. 运行 `git diff --cached` 和 `git diff --cached --stat`。
2. 如果没有暂存变更，检查 `git status --short`，询问用户要先暂存文件还是基于未暂存变更处理。不要隐式暂存。
3. 按仓库策略对暂存文件分组。monorepo 优先使用 `packages/<name>/` 边界，应用项目优先使用功能边界。
4. 根配置、锁文件、Changesets、仓库说明以及跨包工具链应放入 shared 或 tooling 提交，除非它们明显只属于某一个包。
5. 提交前按执行顺序给出建议的英文 Conventional Commit 消息。
6. 每组只提交暂存区中属于该组的文件，保留所有未暂存变更。
7. 使用目录名或包名作为 scope，例如 `feat(request): ...`；共享根目录变更使用 `chore(repo): ...`。
8. 按以下优先级决定是否执行 `git push`：用户当前请求、当前仓库 `AGENTS.md`、默认行为。用户或仓库要求不推送时不得推送；两者均未说明时默认推送。
9. 允许推送时，失败后可以重试，但总尝试次数最多为 5 次（首次执行计入 5 次）。
10. 第 5 次推送仍失败时，停止自动重试，明确报告最终失败及最后一次错误；不要改用其他远端、分支或推送参数。
