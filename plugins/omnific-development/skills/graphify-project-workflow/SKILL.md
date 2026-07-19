---
name: graphify-project-workflow
description: 在分析、解释、审查或修改包含 graphify-out 产物的仓库，或者用户输入 /graphify 时，执行共享 Graphify 导航流程。调用已安装的 graphify Skill，先查询聚焦子图再大范围检查源码，并在代码修改后更新图谱。
---

# Graphify 项目工作流

1. 用户输入 `/graphify` 时，在执行其他操作前调用已安装的 `graphify` Skill。
2. 如果存在 `graphify-out/graph.json`，代码库问题先运行 `graphify query "<question>"`。
3. 使用 `graphify path "<A>" "<B>"` 查询关系，使用 `graphify explain "<concept>"` 聚焦概念。
4. 如果存在 `graphify-out/wiki/index.md`，使用它进行大范围导航。
5. 只有进行大范围架构审查，或聚焦命令没有提供足够上下文时，才读取 `graphify-out/GRAPH_REPORT.md`。
6. hook 或增量更新导致图谱文件变更属于正常状态，不能作为跳过 Graphify 的理由。
7. 只有任务本身处理过期或错误的图谱输出，或者用户明确要求时，才跳过 Graphify。
8. 修改代码后运行 `graphify update .`，刷新基于 AST 的图谱输出。
