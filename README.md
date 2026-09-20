# SyncTV 群晖 DSM 7.2 构建

[![编译并发布 DSM 7.2 二进制](https://github.com/tbc0309/synctv-dsm/actions/workflows/build.yml/badge.svg)](https://github.com/tbc0309/synctv-dsm/actions/workflows/build.yml)

使用群晖官方 DSM 7.2 交叉工具链，自动构建并发布 SyncTV 服务端二进制文件。

## 兼容性

- Synology DSM 7.2+
- amd64 / x86_64
- armv8 / aarch64

## 下载

请从 Releases 下载对应架构的未压缩二进制文件：

- amd64：`synctv-dsm72-amd64`
- armv8：`synctv-dsm72-armv8`

同时提供 SHA-256 校验文件。下载后执行 `chmod +x synctv-dsm72-*` 添加执行权限。

## 自动构建

GitHub Actions 每天检查 `synctv-org/synctv` 的最新正式 Release。发现尚未发布的新版本时，会自动使用 DSM 7.2 工具链构建两个架构，并创建同版本 Release。草稿版和预发布版不会触发自动构建。

也可在 Actions 页面手动指定上游 `v*` 标签进行构建。工作流会校验 Synology 官方工具链的 MD5，分别使用 Avoton x86_64 和 RTD1296 armv8 工具链，构建完成后检查两个二进制及其 SHA-256 文件齐全再发布。

## 说明

- 本仓库只提供构建工作流，不修改 SyncTV 源码。
- 生成物为未压缩服务端二进制，不是 DSM SPK 套件。
- 本项目与 SyncTV 官方及 Synology 无隶属关系。

## 许可证

本仓库的构建脚本采用 [MIT License](LICENSE) 发布。SyncTV 源码及生成物继续遵循[上游项目](https://github.com/synctv-org/synctv)声明的许可证，第三方依赖保留各自许可证。
