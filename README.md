# 极简链接导航页（Vue + Vite 版）

一个高度可配置、响应式、支持暗色模式的单页链接导航模板，基于 **Vue 3 + Vite** 构建。所有内容（标题、链接、描述、社交图标等）均通过配置文件管理，无需修改 HTML 或组件代码即可快速定制。

---

## ✨ 特性

- 🎨 **极简美观设计**：干净排版 + 柔和交互动效  
- 🌓 **自动/手动暗色模式**：支持系统偏好 + 本地存储记忆  
- ⚙️ **全配置驱动**：所有文本、链接、图片集中管理  
- 📱 **响应式布局**：适配手机、平板、桌面  
- 🚀 **Vite 构建**：秒级热更新，极速打包  
- 🔒 **静态部署**：输出纯 HTML/CSS/JS，可托管于 GitHub Pages、Vercel、Nginx 等  

---

## 📂 项目结构
```
src
├── App.vue
├── main.js
├── siteConfig.js
├── style.css
public
├── favicon.ico
vite.config.js
```


---

## 🛠️ 快速开始

### 1. 安装依赖
```
npm install
```

### 2. 开发调试
```
npm run dev
```
访问 `http://localhost:5173`
### 3. 构建生产版本
```
npm run build
```
输出位于 `dist/` 目录，可直接部署.