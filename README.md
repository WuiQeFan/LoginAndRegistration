# MemFireDB 用户认证系统

这是一个使用 MemFireDB（基于 Supabase）实现的现代用户认证系统，包含注册和登录功能，采用响应式设计，适配各种设备尺寸。

## 功能特性

- **用户注册**：创建新账户，包含用户名、邮箱和密码
- **用户登录**：通过邮箱和密码进行身份验证
- **表单验证**：客户端验证确保数据完整性
- **响应式设计**：适配桌面和移动设备
- **社交登录**：提供 Google、GitHub 和 Twitter 登录选项（占位）
- **消息反馈**：操作成功/错误提示
- **UI 动画**：平滑的过渡和交互效果

## 技术栈

- **前端**：HTML5, CSS3, JavaScript
- **数据库**：MemFireDB (Supabase)
- **图标库**：Font Awesome
- **字体**：Google Fonts (Poppins)

## 快速开始

### 1. 前置要求

- MemFireDB 账户（或 Supabase 账户）
- 基本的 Web 服务器环境（或直接通过浏览器运行）

### 2. 配置 MemFireDB

1. 登录 [MemFireDB 控制台](https://cloud.memfiredb.com)（或 [Supabase 控制台](https://supabase.com)）
2. 创建新项目
3. 在项目设置中获取 API URL 和公钥
4. 启用电子邮件认证（在 Authentication > Providers 中）

### 3. 配置代码

在 HTML 文件中找到以下代码片段（约第 177-179 行）：

```javascript
// 初始化Supabase客户端（替换为您的MemFireDB项目信息）
const supabaseUrl = 'https://your-project.supabase.co';
const supabaseKey = 'your-supabase-key';
```

替换为您的实际 MemFireDB 项目信息：

```javascript
const supabaseUrl = 'https://your-project-id.memfiredb.com';
const supabaseKey = 'your-public-api-key';
```

### 4. 运行应用

直接打开 HTML 文件或在 Web 服务器中部署：

```bash
# 使用 Python 简单 HTTP 服务器
python -m http.server
```

访问 `http://localhost:8000` 查看应用

## 文件结构

```
memfiredb-auth/
├── index.html                 # 主应用文件（包含HTML、CSS和JS）
├── README.md                  # 项目说明文件（当前文件）
└── (可选) images/              # 图片资源目录
```

## 使用说明

### 注册新账户

1. 点击"注册"标签
2. 填写用户名、邮箱和密码
3. 确认密码
4. 点击"注册"按钮
5. 检查邮箱验证邮件（MemFireDB 自动发送）

### 登录账户

1. 在登录表单中输入邮箱和密码
2. 点击"登录"按钮
3. 成功登录后显示欢迎消息

### 社交登录

点击社交图标按钮尝试登录（功能需额外配置）

## 自定义选项

### 修改样式

1. 颜色主题：修改 CSS 中的渐变背景色
   ```css
   background: linear-gradient(135deg, #667eea, #764ba2);
   ```

2. 表单样式：调整 `.input-group` 和 `.btn` 类

### 扩展功能

1. **实现社交登录**：
   - 在 MemFireDB/Supabase 启用 OAuth 提供商
   - 添加社交登录处理逻辑

2. **添加密码重置**：
   - 实现"忘记密码"功能
   - 使用 `supabase.auth.resetPasswordForEmail()`

3. **用户资料管理**：
   - 添加用户资料页面
   - 使用 `supabase.from('profiles').update()`

## 故障排除

- **注册/登录失败**：检查 MemFireDB 配置是否正确，确保电子邮件认证已启用
- **网络错误**：验证 supabaseUrl 和 supabaseKey 是否正确
- **样式问题**：确保所有外部资源（Font Awesome、Google Fonts）可访问
- **密码验证失败**：确保密码至少8位字符，且两次输入一致

## 贡献指南

欢迎提交 Pull Request 改进项目：
1. Fork 仓库
2. 创建新分支 (`git checkout -b feature/improvement`)
3. 提交更改 (`git commit -am 'Add some feature'`)
4. 推送到分支 (`git push origin feature/improvement`)
5. 创建 Pull Request

## 许可证

本项目采用 [MIT 许可证](LICENSE)

---

**提示**：实际部署前，请确保已正确配置 MemFireDB 项目的安全规则，并考虑添加额外的安全措施（如验证码、登录尝试限制等）。
