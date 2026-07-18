# handsbnbu Privacy Policy

这个仓库托管非官方应用“掌上BNBU”的公开隐私政策页面。

- 页面入口：[`index.html`](index.html)
- 预期 GitHub Pages 地址（完成远端配置后）：<https://rainchen537.github.io/handsbnbu/>
- 应用仓库：<https://github.com/Rainchen537/ispace_timeline>

## 本地预览

可以直接打开 `index.html`，或将静态服务器只绑定到本机回环地址：

```bash
python3 -m http.server --bind 127.0.0.1 8000
```

然后访问 <http://127.0.0.1:8000/>。

## 发布

`.github/workflows/pages.yml` 包含相互分离的校验和部署任务。推送到 `main` 或手动运行工作流时，校验任务会解析页面的可见 DOM 结构，并只把允许公开的 `index.html` 放入待发布目录。部署任务只会在工作流运行于 `refs/heads/main` 时执行。

GitHub 不会仅因仓库中存在该工作流就自动完成 Pages 的首次配置。仓库管理员需要先完成一次远端设置：

1. 打开仓库 `Settings` → `Pages`；
2. 将 `Build and deployment` 的 Source 设为 **GitHub Actions**；
3. 推送 `main`，或在 `main` 分支上手动运行 `Deploy privacy policy`；
4. 等待校验和部署任务完成，再访问上方 Pages 地址。

在其他分支手动运行工作流只会执行校验，不会更新公开页面。

## 维护要求

只要应用的数据处理行为发生变化，就必须同步更新隐私政策，尤其包括：

- 登录凭据、会话和本地偏好数据的存储方式；
- 学校平台、可配置端点和邮件服务的交互；
- 邮件、草稿、课程、课表、作业、附件、下载和通知数据；
- 新增权限、第三方 SDK、分析、广告或开发者服务器；
- 数据保留、退出清理、删除方式和联系信息。

修改时更新页面中的“最后更新”日期，并确认内容与应用 README、登录页和实际代码一致。新增公开静态文件时，还必须显式加入工作流中的发布允许列表。

## App Store Connect

将 GitHub Pages HTTPS 地址填写到：

- `Privacy Policy URL`
- 如有需要，也可以用于 `Support URL`
