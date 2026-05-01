# WebToAPI

将网页版 AI 封装为标准 OpenAI 兼容 API，支持 Claude、DeepSeek 等主流模型。

无需 API Key 订阅费用，通过 WebView2 自动化调用网页版服务，本地提供 `/v1/chat/completions` 接口，兼容所有 OpenAI 客户端。

## 支持的 AI

| 服务 | 状态 | 端口 |
|------|------|------|
| Claude (Sonnet / Haiku / Opus) | ✅ 已支持 | `44445` |
| DeepSeek | ✅ 已支持 | `55555` |
| 更多 AI 对接中 | 🚧 开发中 | - |

## 使用方法

### 启动

运行程序后，会自动弹出激活窗口（首次使用需要激活码）。

### 客户端配置

任何兼容 OpenAI API 的客户端，配置为：

```
Base URL: http://127.0.0.1:44445/v1
API Key: sk-any（任意值）
Model:   claude-sonnet-4-6（或其他支持的模型）
```

### 可用模型

| 模型名 | 说明 |
|--------|------|
| `claude-sonnet-4-6` | 默认模型 |
| `claude-sonnet-4-6-thinking` | Sonnet + 扩展思考 |
| `claude-sonnet-4-5` | Sonnet 4.5 |
| `claude-haiku-4-5` | 轻量快速 |
| `claude-opus-4-7` | Opus 4.7（需 Pro） |
| `claude-opus-4-6` | Opus 4.6（需 Pro） |
| `claude-opus-3` | Opus 3（需 Pro） |

## 激活购买

本软件为付费产品，需要激活码才能使用。

👉 **[点击前往闲鱼购买激活码](https://m.tb.cn/h.iEd8DKi?tk=YtiS5lshJZi)**

## 系统要求

- Windows 10 / Windows 11
- WebView2 Runtime（系统自带）
- 需要网络连接（访问 AI 网页服务）

## 隐私说明

- 所有 API 请求在本地处理，不经过第三方服务器
- 仅通过 WebView2 与 AI 官方的网页服务通信
- 不收集任何用户数据
