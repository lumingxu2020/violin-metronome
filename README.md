# 弦拍 · 小提琴节拍器

无需后端的 Web/PWA 小提琴节拍器。内置 14 种实时合成音效，支持拍号、节奏细分、弓法提示、渐进提速和本地练习预设。

## 本地预览

```bash
python3 -m http.server 8780
```

访问 `http://localhost:8780`。

## NAS Docker 部署

项目已包含 `Dockerfile`、`compose.yaml` 和 Nginx 配置。在 NAS 的 Container Manager、Container Station 或 Docker Compose 中，将整个目录上传到 NAS 后执行：

```bash
docker compose up -d --build
```

默认访问地址为 `http://NAS地址:8780`。如端口冲突，可修改 `compose.yaml` 中 `8780:80` 左侧的端口。

## 更新

替换 NAS 上的项目文件后，在项目目录执行：

```bash
docker compose up -d --build
```

## HTTPS

普通节拍功能可在局域网 HTTP 下工作。如需安装到手机桌面、完整离线缓存，建议在 NAS 反向代理中配置 HTTPS 域名并转发到容器端口 `8780`。

## 数据说明

用户预设保存在浏览器本地存储中，不会上传到服务器。清除浏览器网站数据会删除自定义预设。
