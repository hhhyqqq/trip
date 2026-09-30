# 四川旅行手册

旅行网页本体只有一个运行时文件：public/index.html。页面没有外部字体、图片、地图 SDK 或 JavaScript 依赖；下载后直接双击 public/index.html 也能离线查看。

## 首次部署：必须在电脑上完成

1. 在 GitHub 创建一个公开仓库，例如 sichuan-trip-handbook。
2. 将 public/index.html、wrangler.jsonc 和本文件推送到默认分支（通常是 main）。
3. 在浏览器登录 Cloudflare，打开 Workers & Pages，创建应用，并选择从 Git 仓库导入 Worker。
4. 授权 Cloudflare 访问 GitHub，选择这个仓库；根目录保持为仓库根目录，部署时读取 wrangler.jsonc。
5. 确认部署。首次成功后会获得免费的 *.workers.dev 公开网址。
6. 今后只需 git push 到默认分支，Cloudflare 会自动重新部署。

## 可选：自定义域名

在该 Worker 的设置中添加 Custom Domain，按 Cloudflare 的提示完成域名验证即可。没有自己的域名时，直接分享 *.workers.dev 网址即可。

## 发布前检查

- 不要写入订单确认号、证件号、房间号、付款截图或私人联系方式。
- 在 iPhone 上点地点名和全天多点导航，确认 Apple 地图能正确识别位置。
- 行程变更后只修改 public/index.html；待办是静态文字，避免不同浏览器出现不同的勾选状态。
