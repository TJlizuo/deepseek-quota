# DeepSeek 额度查询 — Android 小工具

一个简洁的 **PWA 工具**，在安卓手机（或任何浏览器）上快速查看 DeepSeek API 余额。

## 📦 文件说明

| 文件 | 说明 |
|------|------|
| `index.html` | **核心文件**，单页自包含（HTML + CSS + JS），复制到手机即可用 |
| `manifest.json` | PWA 清单，通过 HTTP 服务访问时可安装到桌面 |
| `service-worker.js` | 离线缓存，通过 HTTP 服务访问时生效 |

## 🚀 快速开始

### 方式一：直接传文件到手机（推荐）

1. 将 `index.html` 通过 **微信 / QQ / USB 数据线** 发送到安卓手机
2. 用手机上的 **Chrome 浏览器** 打开此文件
   > ⚠️ 不要用系统自带的文件管理器或默认浏览器打开
3. 在页面中输入你的 DeepSeek API Key
4. 点击「查询余额」即可查看

### 方式二：通过局域网 HTTP 服务（可安装到桌面）

**电脑端启动：**

```bash
# 在项目目录下
npx serve .
```

或使用 Node.js 自带模块：

```bash
# Windows
npx http-server . -p 3000 --cors
```

**手机端：**
1. 确保手机和电脑在**同一 Wi-Fi 网络**
2. 手机 Chrome 打开 `http://<电脑IP>:3000`
3. 可将页面「添加到主屏幕」(Chrome 菜单 → 添加到主屏幕)

## 🔑 获取 DeepSeek API Key

1. 访问 [platform.deepseek.com](https://platform.deepseek.com)
2. 登录或注册账号
3. 左侧菜单 → **API Keys** → 创建新 Key
4. 复制 `sk-...` 格式的密钥

## 🔒 安全说明

- **API Key 仅存于浏览器本地存储 (localStorage)**，不会发送到任何第三方
- 查询请求直接发往 DeepSeek 官方接口 `https://api.deepseek.com/user/balance`
- 页面无后端服务、无追踪代码、无第三方脚本
- 在 `file://` 协议下，localStorage 可能无法持久化（每次重新打开需重新输入 Key）

## 📱 功能

- 查看账户可用状态（可用 / 不可用）
- 查看总余额、充值余额、赠送余额
- 支持多币种显示（CNY / USD 等）
- 深色主题，护眼设计
- 移动端适配
- API Key 自动保存（HTTP 环境下）

## 📄 License

MIT
