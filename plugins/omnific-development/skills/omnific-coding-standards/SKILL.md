---
name: omnific-coding-standards
description: 在编写、修改、重构或审查项目代码时应用 Omnific 通用 TypeScript 代码规范，包括运行时类型谓词、空值判断、正向条件、导出 API 文档、重命名以及移除兼容导出。更严格的项目专属规则以当前仓库的 AGENTS.md 为准。
---

# Omnific 代码规范

1. 编辑前读取当前仓库以及对应目录中的 `AGENTS.md`。
2. 优先复用 `@omnific/utils` 已有的类型谓词和工具方法，不要重复实现运行时判断。
3. 使用 `isNil`、`hasValue` 或更具体的谓词进行空值判断。
4. 普通业务分支优先使用语义与分支意图一致的正向条件。除非仓库完全禁止，否则仅在立即退出当前路径的守卫分支中使用逻辑非。
5. 不要通过与 `true` 或 `false` 比较来规避逻辑非。
6. 按仓库要求为导出的函数、方法、组件、Hook、类型和接口添加 JSDoc 或 TSDoc。
7. 重命名时同步修改声明、导出、路径和所有调用方。删除旧入口，不要仅为兼容添加别名、wrapper、barrel 或 deprecated re-export。
8. 运行当前仓库规定的验证命令。
9. 当前 `AGENTS.md` 中更严格或更具体的规则具有更高优先级。
