# OpenMausBot LazyCat 微服打包

上游项目：https://github.com/milind-soni/OpenMausBot （Apache-2.0）

自托管 AI 聊天应用：每个会话都是一个真实编码 Agent（Claude Code / Codex / Grok），容器内自带浏览器。

## 打包说明

- 镜像：`ghcr.io/milind-soni/openmausbot`（amd64/arm64），由 [ca-x/lazycat-github-action](https://github.com/ca-x/lazycat-github-action) 以镜像模式自动同步
- Web 面板走 upstreams（8799），Webhook `/hooks/` 走 8800 upstream
- 数据持久化：`/lzcapp/var/data` → 容器 `/data`（引擎登录态与状态都在此）
- 健康检查沿用上游镜像自带 healthcheck

## 发布

打 `v*` 标签或手动触发 workflow 即自动同步镜像、构建 LPK、发布 GitHub Release 并提交喵喵商店。
