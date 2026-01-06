微信：ayoeyn

# GEO 搜索结果优化排名系统

基于 PHP 7.3 + MySQL 的 AI 内容生成与 SEO 优化 SaaS 平台。

## 功能模块

### 用户端
- 主关键词管理 - 添加、编辑、删除关键词
- 拓展问题生成 - AI 自动生成相关问题
- 企业知识库 - 上传企业资料供 AI 参考
- 企业图库 - 分类管理图片素材
- AI 创作指令 - 自定义文章生成风格
- AI 创作计划 - 批量生成文章
- 文章管理 - 查看、编辑、删除生成的文章

### 管理端 (超级管理员)
- 数据统计 - 用户数、文章数、API 调用统计
- 用户管理 - 用户列表、状态管理、套餐分配
- 套餐管理 - 创建和编辑会员套餐
- 邀请码管理 - 生成和管理邀请码
- 系统公告 - 发布系统公告
- 系统配置 - 火山方舟 API Key 配置
- 官媒代发管理 - 处理代发订单

## 技术栈

- PHP 7.3 (无类型属性，使用 array() 语法)
- MySQL 5.7+
- Tailwind CSS (暗色主题)
- 火山方舟 AI API (OpenAI 兼容格式)

## 目录结构

```
geo-system/
├── app/
│   ├── Controllers/      # 控制器
│   │   ├── ApiController.php
│   │   ├── AdminController.php
│   │   └── AuthController.php
│   ├── Database.php      # 数据库连接
│   └── VolcengineAI.php  # AI 接口封装
├── config/
│   ├── database.php      # 数据库配置
│   └── volcengine.php    # 火山方舟配置
├── database/
│   └── add_ai_index_fields.sql  # 数据库迁移
├── public/
│   ├── api.php           # API 入口
│   ├── index.html        # 前端页面
│   ├── js/app.js         # 前端逻辑
│   └── uploads/          # 上传文件目录
├── install.php           # 数据库安装脚本
├── migrate.php           # 数据库迁移脚本
└── README.md
```

## 安装部署

1. 配置数据库连接 `config/database.php`
2. 访问 `install.php` 初始化数据库
3. 访问 `migrate.php` 执行数据库迁移
4. 配置 Web 服务器指向 `public/` 目录

## 默认账号

- 超级管理员: admin / admin123

## API 接口

API 基础路径: `/api.php?r=`

### 认证
- POST `/api/auth/login` - 登录
- POST `/api/auth/register` - 注册
- GET `/api/auth/me` - 获取当前用户

### 内容管理
- GET/POST `/api/keywords` - 关键词管理
- GET `/api/questions` - 拓展问题
- GET/POST `/api/articles` - 文章管理
- GET/POST `/api/knowledge` - 知识库
- GET/POST `/api/gallery` - 图库
- GET/POST `/api/instructions` - 创作指令
- GET/POST `/api/creation-plans` - 创作计划

### AI 功能
- GET `/api/ai-config` - 获取 AI 配置 (加密)
- GET `/api/ai-index/stats` - AI 收录统计

### 官媒代发
- GET/POST `/api/media-proxy/orders` - 代发订单

### 管理接口
- GET `/api/admin/stats` - 统计数据
- GET `/api/admin/users` - 用户列表
- GET/POST `/api/admin/config` - 系统配置
- GET `/api/admin/media-proxy` - 代发订单管理

