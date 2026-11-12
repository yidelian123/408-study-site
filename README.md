# 408 学习站

一个简洁的 408 考研复习入口页，包含四门课复习面板和政治时间轴。

## 页面

- `index.html`：首页，四门课复习总览与考纲弹窗
- `timeline.html`：政治理论发展时间轴

## 部署

把两个 HTML 文件放到 Nginx 的站点根目录，例如：

```bash
/var/www/nexus/
```

Nginx 参考：

```nginx
server {
    listen 80;
    server_name example.com www.example.com;
    root /var/www/nexus;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

生产环境建议使用 Certbot 配置 HTTPS，并开启 80 → 443 跳转。

## 备案

页面底部保留 ICP 备案号与工信部查询链接。上线前请替换为实际备案信息，并在取得公安备案号后补充公安备案链接。

## 说明

页面为纯静态 HTML/CSS/JS，无构建步骤，无外部依赖。