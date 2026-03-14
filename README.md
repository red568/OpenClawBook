# OpenClaw 深度学习笔记

> 系统性剖析 [OpenClaw](https://github.com/openclaw/openclaw) 的架构设计与实现原理，从底层协议到 Agent 运行时的全栈技术解读。

## 这是什么

这是一份基于 OpenClaw 源码（`src/`）和中文文档（`docs/zh-CN/`，约 310 篇）整理的深度学习笔记集，面向希望理解 **AI Agent 框架设计与实现** 的开发者。

笔记从工程实现角度出发，包含大量架构图、时序图、类型签名和源码索引，适合作为：

- 学习 Agent 框架设计模式的参考资料
- 阅读 OpenClaw 源码的导航地图
- AI Agent 工程化实践的技术备忘

## 笔记目录

| 文件 | 内容 | 关键主题 |
|------|------|----------|
| [STUDY_NOTES.md](STUDY_NOTES.md) | **总览笔记** | 项目架构、消息生命周期、Agent 循环、上下文引擎、多 Agent 路由、渠道集成 |
| [CLI原理.md](CLI原理.md) | **CLI 实现原理** | Node.js 启动链路、Commander.js 懒加载、快速路由、Profile 隔离、preAction Hook、插件 CLI 注册 |
| [Gateway原理与协议.md](Gateway原理与协议.md) | **Gateway 原理与协议** | WebSocket 协议、TypeBox Schema、RPC 方法、认证体系、设备配对、配置热重载、健康探针 |
| [Agent运行时原理.md](Agent运行时原理.md) | **Agent 运行时原理** | Agent 生命周期、System Prompt 装配、上下文引擎、会话隔离、Memory 系统、工具管线、Compaction 策略、Hook 系统 |

## 阅读路线

```
STUDY_NOTES.md          ← 从这里开始，建立全局认知
       ↓
CLI原理.md              ← 理解入口与命令系统
       ↓
Gateway原理与协议.md     ← 理解核心守护进程与通信协议
       ↓
Agent运行时原理.md       ← 深入 Agent 核心运行机制
```

## 核心技术栈

- **语言**: TypeScript (ESM)
- **运行时**: Node.js 22+
- **CLI 框架**: Commander.js + 懒加载命令注册
- **协议定义**: TypeBox Schema + AJV 运行时校验
- **通信**: WebSocket (JSON 帧)
- **AI 推理**: pi-agent-core (嵌入式调用)
- **记忆检索**: SQLite + vec 扩展 (BM25 + 向量余弦混合检索)
- **会话存储**: JSONL

## 许可证

[MIT](LICENSE)
