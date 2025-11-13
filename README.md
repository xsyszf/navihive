<div align="center">

<svg width="120" height="120" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M60 10L105 35V85L60 110L15 85V35L60 10Z" fill="url(#paint0_linear)" stroke="#2D6CDF" stroke-width="2"/>
  <path d="M60 30L80 40V75L60 85L40 75V40L60 30Z" fill="white" stroke="#2D6CDF" stroke-width="2"/>
  <circle cx="60" cy="57" r="10" fill="#2D6CDF"/>
  <path d="M60 43V57L68 65" stroke="white" stroke-width="3" stroke-linecap="round"/>
  <defs>
    <linearGradient id="paint0_linear" x1="15" y1="60" x2="105" y2="60" gradientUnits="userSpaceOnUse">
      <stop stop-color="#61DAFB"/>
      <stop offset="1" stop-color="#2D6CDF"/>
    </linearGradient>
  </defs>
</svg>

# NaviHive - 现代化个人导航站

![NaviHive 导航站](https://img.shields.io/badge/NaviHive-导航站-blue)
![React](https://img.shields.io/badge/React-19.0.0-61dafb)
![TypeScript](https://img.shields.io/badge/TypeScript-5.7-3178c6)
![Material UI](https://img.shields.io/badge/Material_UI-7.0-0081cb)
![Cloudflare](https://img.shields.io/badge/Cloudflare-Workers-f38020)
![License](https://img.shields.io/badge/License-MIT-green)

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/xsyszf/Cloudflare-Navihive)

**一个优雅、现代化的网站导航管理系统**
基于 Cloudflare Workers 构建 • 零成本部署 • 全球 CDN 加速 • 企业级安全

[📖 完整文档](https://zqq-nuli.github.io/Cloudflare-Navihive/) • [🎮 在线演示](https://navihive.chatbot.cab/) • [🚀 快速开始](https://zqq-nuli.github.io/Cloudflare-Navihive/deployment/) • [💬 问题反馈](https://github.com/zqq-nuli/Cloudflare-Navihive/issues)

</div>

---

## ✨ 核心亮点

### 💰 零成本运行
基于 Cloudflare Workers 免费套餐，每月 100,000 次免费请求，永久免费使用

### ⚡ 极致性能
全球 300+ CDN 节点，毫秒级响应时间，自动边缘缓存

### 🔐 企业级安全
经过 14 个安全修复提交 • JWT + bcrypt 认证加密 • HttpOnly Cookie 防 XSS • SQL 注入防护 • SSRF 防护

### 🌍 访客模式
支持公开/私密内容分离 • 未登录用户可浏览公开内容 • 管理员查看全部数据

### 🔄 拖拽排序
可视化调整分组和网站顺序 • 所见即所得的交互体验 • 自动保存排序结果

### 🎨 高度自定义
自定义 CSS 样式 • 自定义背景图 • 自定义主题色 • 暗色模式支持

---

## 🎯 快速开始

### 在线演示

访问演示站点体验所有功能：[navihive.chatbot.cab](https://navihive.chatbot.cab/)

```
👤 演示账号：admin
🔑 演示密码：NaviHive2025!
```

### 立即部署

**5 分钟完成部署，零成本永久使用：**

1. **Fork 项目** → 点击右上角 Fork 按钮
2. **新建 wrangler.jsonc 文件** 从 wrangler.template.jsonc 复制然后修改
3. **一键部署** → [![Deploy](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/你的用户名/Cloudflare-Navihive)
4. **配置数据库** → 按照[部署指南](https://zqq-nuli.github.io/Cloudflare-Navihive/deployment/)创建 D1 数据库

> 详细步骤见[完整部署指南](https://zqq-nuli.github.io/Cloudflare-Navihive/deployment/)

## 🚀 部署指南

### 一、准备工作

在开始部署之前，您需要：

1. 一个 [Cloudflare 账号](https://dash.cloudflare.com/sign-up)（免费）
2. 一个 GitHub 账号（如果您想 fork 此项目或使用一键部署功能）
3. 基本的网络和浏览器操作知识

### 二、一键部署方法（推荐小白用户）

最简单的部署方式是使用一键部署功能：
1. fork本仓库，修改`wrangler.template.jsonc`为`wrangler.jsonc`
2. 点击上方的"Deploy to Cloudflare Workers"按钮
3. 登录您的 Cloudflare 账号
4. 在部署界面上，您需要配置以下内容：
    - **项目名称**：为您的导航站项目取个名字
    - **D1 数据库**：点击"创建新数据库"，命名为`navigation-db`
    - **环境变量**：
        - `AUTH_ENABLED`：设置为`true`启用登录认证
        - `AUTH_USERNAME`：管理员用户名
        - `AUTH_PASSWORD`：管理员密码
        - `AUTH_SECRET`：JWT 密钥（使用随机字符串）
5. 点击"部署"按钮

部署完成后，您将获得一个类似`https://your-project-name.username.workers.dev`的网址，这就是您的导航站地址。

6. 初始化项目数据库  
   - 登录您的 [Cloudflare 控制台](https://dash.cloudflare.com/)
   - 进入"Workers & Pages"部分
   - 选择您刚刚部署的项目
   - 在左侧菜单中点击"设置" > "数据库"，您将看到已绑定的数据库（名为"navigation-db"）
   - 点击数据库名称以进入数据库管理界面：

   ![数据库管理界面](https://img.zhengmi.org/file/1743843332374_image.png)

   - 在数据库管理界面，点击"控制台"选项卡进入SQL编辑器
   - 在SQL编辑器中，逐个复制并粘贴以下SQL命令：

   ```sql
   -- 创建分组表
   CREATE TABLE IF NOT EXISTS groups (
       id INTEGER PRIMARY KEY AUTOINCREMENT, 
       name TEXT NOT NULL, 
       order_num INTEGER NOT NULL, 
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP, 
       updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );

   -- 创建站点表
   CREATE TABLE IF NOT EXISTS sites (
       id INTEGER PRIMARY KEY AUTOINCREMENT, 
       group_id INTEGER NOT NULL, 
       name TEXT NOT NULL, 
       url TEXT NOT NULL, 
       icon TEXT, 
       description TEXT, 
       notes TEXT, 
       order_num INTEGER NOT NULL, 
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP, 
       updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP, 
       FOREIGN KEY (group_id) REFERENCES groups(id) ON DELETE CASCADE
   );

   -- 创建配置表
   CREATE TABLE IF NOT EXISTS configs (
       key TEXT PRIMARY KEY,
       value TEXT NOT NULL,
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
       updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );

   -- 设置初始化标志
   INSERT INTO configs (key, value) VALUES ('DB_INITIALIZED', 'true');
   ```

   - 点击"运行"按钮执行SQL命令：

   ![SQL编辑器界面](https://img.zhengmi.org/file/1743843528319_image.png)

   - 如果SQL命令执行成功，您将看到"查询成功"的提示信息
   - 至此，数据库初始化完成，您可以访问您的导航站首页并使用配置的管理员账号登录

---

## 📖 完整文档

### 📚 用户指南
- [**项目介绍**](https://zqq-nuli.github.io/Cloudflare-Navihive/introduction) - 了解 NaviHive 的特点和优势
- [**为什么选择 NaviHive**](https://zqq-nuli.github.io/Cloudflare-Navihive/guide/why-navihive) - 与其他方案的对比
- [**功能截图**](https://zqq-nuli.github.io/Cloudflare-Navihive/guide/screenshots) - 11 张精美功能截图展示
- [**常见问题**](https://zqq-nuli.github.io/Cloudflare-Navihive/guide/faq) - FAQ 和故障排除
- [**更新日志**](https://zqq-nuli.github.io/Cloudflare-Navihive/guide/changelog) - 版本历史和变更记录

### 🔧 开发者文档
- [**部署指南**](https://zqq-nuli.github.io/Cloudflare-Navihive/deployment/) - 详细的部署步骤
- [**架构设计**](https://zqq-nuli.github.io/Cloudflare-Navihive/architecture/) - 技术栈和系统架构
- [**API 文档**](https://zqq-nuli.github.io/Cloudflare-Navihive/api/) - RESTful API 参考
- [**安全指南**](https://zqq-nuli.github.io/Cloudflare-Navihive/security/) - 14+ 安全加固说明
- [**贡献指南**](https://zqq-nuli.github.io/Cloudflare-Navihive/contributing/) - 如何参与项目

### 🎯 功能特性
- [**功能概览**](https://zqq-nuli.github.io/Cloudflare-Navihive/features/) - 完整功能列表和说明

> 📝 访问 [NaviHive 文档站点](https://zqq-nuli.github.io/Cloudflare-Navihive/) 查看完整文档

---

## 🛠️ 技术栈

**前端**: React 19 • TypeScript 5.7 • Material UI 7.0 • Tailwind CSS 4.1 • DND Kit • Vite 6

**后端**: Cloudflare Workers • Cloudflare D1 (SQLite) • JWT + bcrypt • TypeScript Strict Mode

**开发**: pnpm • Wrangler CLI • ESLint + Prettier

## 🤝 贡献

欢迎所有形式的贡献！查看 [贡献指南](https://zqq-nuli.github.io/Cloudflare-Navihive/contributing/) 了解如何参与项目。

---

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源协议发布。

---

## 🙏 致谢

感谢以下开源项目和服务：

- [React](https://reactjs.org/) • [TypeScript](https://www.typescriptlang.org/) • [Vite](https://vitejs.dev/)
- [Material UI](https://mui.com/) • [DND Kit](https://dndkit.com/) • [Tailwind CSS](https://tailwindcss.com/)
- [Cloudflare Workers](https://workers.cloudflare.com/) • [Cloudflare D1](https://developers.cloudflare.com/d1/)
- [Claude Code](https://claude.ai/code) • [Cursor](https://www.cursor.com)

感谢所有提交 Issue、PR 和 Star 的开发者们！🌟

---

## ⭐ 支持项目

如果 NaviHive 对你有帮助，欢迎通过以下方式支持：

### 💝 给项目点赞
- 点击右上角的 ⭐ **Star** 按钮，这是对开发者最大的鼓励
- **Fork** 项目，参与改进和定制
- 分享给你的朋友和同事

### 💰 赞赏支持
你的赞赏将用于项目的持续开发和维护：

<div align="center">
  <img src="https://img.zhengmi.org/file/1743956440128_4b965550184c06d8164f8077fa42b5d.jpg" alt="微信赞赏码" width="300">
  <p><em>微信扫码赞赏</em></p>
</div>

### 🤝 其他支持方式
- 💬 提交有价值的 Issue 和 Feature Request
- 📝 改进文档和教程
- 🐛 报告 Bug 并提供复现步骤
- 💻 贡献代码（欢迎提交 PR）

---

## 📈 Star History

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=zqq-nuli/Cloudflare-Navihive&type=Date&theme=dark" />
  <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=zqq-nuli/Cloudflare-Navihive&type=Date" />
  <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=zqq-nuli/Cloudflare-Navihive&type=Date" />
</picture>

---

<div align="center">

## 🎉 让导航管理更简单

**NaviHive** - 你的专属网络导航中心

[立即部署](https://deploy.workers.cloudflare.com/?url=https://github.com/zqq-nuli/Cloudflare-Navihive) • [在线演示](https://navihive.chatbot.cab/) • [完整文档](https://zqq-nuli.github.io/Cloudflare-Navihive/) • [提交问题](https://github.com/zqq-nuli/Cloudflare-Navihive/issues)

Made with ❤️ by [zqq-nuli](https://github.com/zqq-nuli)

⭐ 如果觉得有用，别忘了点个 Star 哦 ⭐

</div>
