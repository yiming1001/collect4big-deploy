# 数据采集工具 - 部署版本

这是项目的生产部署版本，包含编译后的静态文件。

## 🚀 快速部署

### GitHub Pages（自动）
访问：https://yiming1001.github.io/collect4big-deploy/

### 服务器部署

#### 方式1：使用 dist 目录（推荐）

```bash
# 克隆仓库
git clone https://github.com/yiming1001/collect4big-deploy.git

# 配置 Nginx（示例）
server {
    listen 80;
    server_name your-domain.com;
    
    root /path/to/collect4big-deploy/dist;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
}

# 或直接复制文件到Web目录
cp -r collect4big-deploy/dist/* /var/www/html/
```

#### 方式2：直接使用静态文件服务器

```bash
cd collect4big-deploy
npx serve dist -p 8080
```

## 📁 目录结构

```
collect4big-deploy/
├── dist/              # 生产环境文件（使用这个）
│   ├── index.html
│   ├── assets/
│   │   ├── *.js
│   │   └── *.css
│   └── icons/
├── package.json       # 项目配置
└── README.md
```

## ⚠️ 重要说明

- 本仓库**只包含编译后的文件**，不包含源代码
- **直接使用 `dist/` 目录**进行部署
- 支持所有现代浏览器
- 需要服务器支持SPA路由（配置 `try_files`）

## 🔧 故障排除

### 问题1：页面404
检查服务器配置是否支持SPA路由：
```nginx
try_files $uri $uri/ /index.html;
```

### 问题2：资源加载失败
确认 `base` 路径配置正确（项目已配置为 `./`）

### 问题3：克隆失败
确保使用正确的仓库地址：
```bash
# ✅ 正确
https://github.com/yiming1001/collect4big-deploy.git

# ❌ 错误
http://github.com/yiming1001/collect4big-deploy
```

## 📝 技术栈

- Vue 3
- Element Plus
- Vite
- Vue Router

---

**注意**：本仓库为自动部署仓库，请勿直接编辑。如需修改功能，请在开发仓库进行。
