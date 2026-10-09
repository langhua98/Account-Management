# Account-Management

账户管理网页：按 GitHub 仓库分组管理所有网址，并汇总各平台账号入口。

基于开源项目 [Homer](https://github.com/bastienwirtz/homer)（v26.08.3，Apache-2.0，许可证见 `licenses/HOMER-LICENSE`）直接部署，无需服务器。

## 改哪里

| 文件 | 内容 |
| --- | --- |
| `assets/config.yml` | 首页：每个仓库一组，组里放该仓库的各种网址（源码、线上地址、后台、文档…） |
| `assets/accounts.yml` | 账号页（`#accounts`）：各平台登录入口和账号名 |

在 GitHub 网页上直接编辑这两个文件并提交，`main` 分支更新后会自动重新部署。

> ⚠️ **不要在任何配置文件里写密码。** 页面内容是公开可访问的，密码请放在 Bitwarden / KeePassXC 等密码管理器中。

## 部署

1. 仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。
2. 推送到 `main` 后，`.github/workflows/pages.yml` 会自动发布，地址为 `https://langhua98.github.io/Account-Management/`。

> 私有仓库使用 GitHub Pages 需要 GitHub Pro 或更高套餐；免费账号需把仓库设为公开。

## 本地预览

```bash
python3 -m http.server 8080
# 打开 http://localhost:8080
```

## 升级 Homer

从 [Homer Releases](https://github.com/bastienwirtz/homer/releases) 下载新版 `homer.zip`，解压覆盖本仓库，保留 `assets/config.yml` 和 `assets/accounts.yml` 即可。
