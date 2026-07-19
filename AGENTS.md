# Omnific Codex 维护规则

## 语言

- `AGENTS.md` 和所有 `SKILL.md` 使用中文。
- `README.md` 使用英文。
- 命令、包名、路径、配置键和 Skill 标识保留英文。

## Plugin 更新

- 创建或更新 Skill 时，使用 `skill-creator` 的流程。
- 修改 Plugin 后，运行 Skill 与 Plugin 的官方校验。
- 本地迭代时，使用 `plugin-creator` 更新 Plugin 的 cachebuster，然后重新安装 Plugin。
- 更新后提示用户新开 Codex 线程，以加载新的 Skill。

## Git

- 使用英文 Conventional Commits。
- 不要提交凭据、令牌或本机缓存目录。
