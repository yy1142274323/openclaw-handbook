# OpenClaw Handbook | OpenClaw 安装使用教程

<div align="center">

## 🤖 OpenClaw 安装使用疑难杂症解决指南

**OpenClaw 各平台安装教程 · 问题解答 · 衍生网站合集**

*最后更新 (Last Updated): 2026-03-09 14:23:46*

[![GitHub stars](https://img.shields.io/github/stars/yy1142274323/openclaw-handbook?style=social)](https://github.com/yy1142274323/openclaw-handbook/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/yy1142274323/openclaw-handbook?style=social)](https://github.com/yy1142274323/openclaw-handbook/network/members)

</div>

---

## 📋 目录 | Table of Contents

- [📖 什么是 OpenClaw？](#什么是-openclaw)
- [💻 安装教程](#安装教程)
- [❓ 常见问题 FAQ](#常见问题-faq)
- [🔧 疑难杂症解决](#疑难杂症解决)
- [🛠️ 环境配置](#环境配置)
- [🔗 衍生项目](#衍生项目)
- [📚 学习资源](#学习资源)

---

## 📖 什么是 OpenClaw？

OpenClaw 是一个强大的开源 AI 助手框架，可以帮助你自动化各种任务。它支持多种平台，包括 Linux、macOS、Windows 等。

**官方网站**: https://openclaw.ai
**GitHub**: https://github.com/openclaw/openclaw

---

## 💻 安装教程 | Installation

### 🐧 Linux / Ubuntu / Debian

```bash
# 安装 Node.js (如果未安装)
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs

# 安装 OpenClaw
npm install -g openclaw
openclaw start

# 或者使用 Docker
docker run -d -p 18789:18789 openclaw/openclaw
```

### 🍎 macOS

```bash
# 使用 Homebrew 安装
brew install nodejs
npm install -g openclaw
openclaw start
```

### 🪟 Windows

```bash
# 使用 PowerShell (管理员)
winget install OpenJS.NodeJS.LTS
npm install -g openclaw
openclaw start
```

### 🐳 Docker

```bash
# 安装 Docker (如果没有)
sudo apt install docker.io
sudo systemctl start docker

# 运行 OpenClaw
docker run -d -p 18789:18789 \
  -v openclaw-data:/home/node/.openclaw \
  openclaw/openclaw
```

---

## ❓ 常见问题 FAQ

### Q1: OpenClaw 是什么？
A: OpenClaw 是一个开源的 AI 助手框架，可以部署在各种平台上。

### Q2: 需要什么配置？
A: 建议 2GB+ 内存，10GB+ 硬盘空间。

### Q3: 支持哪些模型？
A: 支持 OpenAI、Claude、DeepSeek、Kimi、Moonshot 等主流模型。

### Q4: 如何配置 API Key？
A: 运行 `openclaw configure` 或编辑配置文件。

---

## 🔧 疑难杂症解决 | Troubleshooting

### ❌ 问题1: npm 安装失败

**解决方案**:
```bash
# 1. 检查 Node.js 版本 (需要 v18+)
node -v

# 2. 清除 npm 缓存
npm cache clean --force

# 3. 使用管理员权限
sudo npm install -g openclaw

# 4. 如果还是失败，尝试:
npm install -g openclaw --verbose
```

### ❌ 问题2: 端口被占用 (Error: Port 18789 is already in use)

**解决方案**:
```bash
# 1. 查看占用进程
lsof -i :18789

# 2. 杀掉占用进程
kill -9 <PID>

# 3. 或者使用其他端口
openclaw start --port 18888
```

### ❌ 问题3: 无法连接模型 API

**解决方案**:
```bash
# 1. 检查网络
curl -I https://api.openai.com

# 2. 配置代理
export HTTP_PROXY=http://127.0.0.1:7890
export HTTPS_PROXY=http://127.0.0.1:7890

# 3. 更换模型服务商
openclaw configure
```

### ❌ 问题4: Docker 启动失败

**解决方案**:
```bash
# 1. 检查 Docker 状态
sudo systemctl status docker

# 2. 启动 Docker
sudo systemctl start docker

# 3. 给权限
sudo chmod 666 /var/run/docker.sock

# 4. 查看日志
docker logs <container_id>
```

---

## 🛠️ 环境配置 | Environment Setup

### Node.js 安装问题

```bash
# Ubuntu/Debian
curl -fsSL https://nodejs.org/dist/v20.x/node-v20.x-linux-x64.tar.xz | sudo tar -xJ -C /usr/local --strip-components=1

# macOS
brew install node@20

# 验证
node -v  # 应该显示 v20.x.x
npm -v
```

### Python 环境 (可选)

```bash
# 安装 Python 3.10+
sudo apt install python3.10 python3-pip

# 验证
python3 --version
```

### Git 配置

```bash
# 配置 Git
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# 生成 SSH Key
ssh-keygen -t ed25519 -C "your@email.com"
```

---

## 🔗 衍生项目 | Related Projects

| 项目 | ⭐ Stars | 描述 |
|------|---------|------|
| [zeroclaw-labs/zeroclay](https://github.com/zeroclaw-labs/zeroclaw) | 25,147 | 轻量级 AI 助手基础设施 |
| [dzhng/deep-research](https://github.com/dzhng/deep-research) | 18,539 | AI 研究助手 |
| [agent0ai/agent-zero](https://github.com/agent0ai/agent-zero) | 15,916 | Agent Zero AI 框架 |
| [memovai/mimiclaw](https://github.com/memovai/mimiclaw) | 4,139 | 在  芯片上运行 OpenClaw |
| [DearVa/Everywhere](https://github.com/DearVa/Everywhere) | 5,638 | 桌面端 AI 助手 |

---

## 📚 学习资源

- [官方文档](https://docs.openclaw.ai)
- [GitHub 仓库](https://github.com/openclaw/openclaw)
- [Discord 社区](https://discord.com/invite/clawd)

---

## 🤝 贡献指南 | Contributing

欢迎提交 PR 完善这个手册！

1. Fork 本仓库
2. 添加新的问题解答
3. 提交 Pull Request

---

## 💰 赞助支持 | Sponsor

如果你觉得这个项目对你有帮助，欢迎请我喝杯咖啡 ☕

![支付宝赞助](https://raw.githubusercontent.com/yy1142274323/openclaw-handbook/main/alipay_qr.png)

---

*🤖 由 Jarvis 自动更新 | Automatically updated by Jarvis*

