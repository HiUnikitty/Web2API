# WebToAPI

还在为 AI API 的高额账单头疼？想用 DeepSeek 的百万级上下文、Grok 的无限制对话，却不想每个月花几百块买 API Key？

**WebToAPI** 将这些 AI 的网页版封装为标准 OpenAI 兼容 API，你只需要一个浏览器就能用的账号，就可以像调用 API 一样使用它们。

通过 WebView2 自动化调用网页服务，本地提供 `/v1/chat/completions` 接口，兼容 Chatbox、SillyTavern（酒馆）、OpenCat 等所有 OpenAI 客户端。

---

## ✨ 核心卖点

### 🆓 DeepSeek - 真正 1M 上下文，无限聊天
接入 DeepSeek 最新网页版，**原生支持百万级 token 上下文**。程序会自动将长对话打包上传，无需担心超出上下文窗口。

配合本仓库提供的 [regex-删除提示.json](regex-删除提示.json) 正则规则导入 SillyTavern（酒馆），可**自动删除** DeepSeek 输出的拒绝提示：
> *"你好，这个问题我暂时无法回答，让我们换个话题再聊聊吧。"*

实现真正的**无缝无限聊天**，每条消息都能正常获取，不受内容限制。

### 🆓 Grok - 无限制，酒馆首选
接入 Grok.com 网页版，**无限请求、不审查内容**。支持自动、快速、专家等多种模型，专为 SillyTavern（酒馆）深度使用优化。

### 🤖 Claude - 多模型支持
支持 Claude Sonnet、Haiku、Opus 全系列模型（需 Pro 订阅）。

### 🧪 Google AI Studio - 编程助手
接入 Gemini Pro 等模型，适合编程等任务。

---

## 支持的 AI

| 服务 | 特点 | 端口 |
|------|------|------|
| **DeepSeek** | 真 1M 上下文、无限聊天、正则去拒绝 | `55555` |
| **Grok** | 无限制、不审查、酒馆推荐 | `5559` |
| **Claude** | Sonnet / Haiku / Opus 全系列 | `44445` |
| **AI Studio (Gemini)** | 适合编程 | `55556` |

---

## 使用方法

### 启动

运行程序后，会自动弹出激活窗口（首次使用需要激活码）。

### 在 SillyTavern（酒馆）中使用

1. 启动对应的 AI 封装服务
2. 在酒馆的 API 设置中选择 **OpenAI** 兼容模式
3. 填写 API 地址：`http://127.0.0.1:对应端口/v1/chat/completions`
4. API Key 任意填写即可
5. **DeepSeek 用户**：在酒馆中导入 `regex-删除提示.json` 正则规则，自动过滤拒绝提示，实现无缝对话

### 在其他客户端中使用

任何兼容 OpenAI API 的客户端，配置为：

```
Base URL: http://127.0.0.1:对应端口/v1
API Key: sk-any（任意值）
```

### 可用端口

| 服务 | 端口 |
|------|------|
| DeepSeek | `55555` |
| Grok | `5559` |
| Claude | `44445` |
| AI Studio | `55556` |

---

## 激活购买

本软件为付费产品，需要激活码才能使用。

👉 **[点击前往闲鱼购买激活码](https://m.tb.cn/h.iEd8DKi?tk=YtiS5lshJZi)**

---

## 系统要求

- Windows 10 / Windows 11
- WebView2 Runtime（系统自带）
- 需要网络连接（访问 AI 网页服务）

## 隐私说明

- 所有 API 请求在本地处理，不经过第三方服务器
- 仅通过 WebView2 与 AI 官方的网页服务通信
- 不收集任何用户数据
