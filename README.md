# OpenClaw Handbook | OpenClaw 安装使用教程

<div align="center">

## 🤖 OpenClaw 安装使用疑难杂症解决指南

**OpenClaw 各平台安装教程 · 问题解答 · 衍生网站合集**

*最后更新 (Last Updated): 2026-03-09 15:04:10*

[![GitHub stars](https://img.shields.io/github/stars/yy1142274323/openclaw-handbook?style=social)](https://github.com/yy1142274323/openclaw-handbook/stargazers)

</div>

---

## 📋 目录

- [📖 什么是 OpenClaw？](#什么是-openclaw)
- [💻 安装教程](#安装教程)
- [❓ 常见问题 FAQ](#常见问题-faq)
- [🔧 疑难杂症解决](#疑难杂症解决)
- [🛠️ 环境配置](#环境配置)
- [🔗 衍生项目](#衍生项目)

---

## 📖 什么是 OpenClaw？

OpenClaw 是一个强大的开源 AI 助手框架。

**官方网站**: https://openclaw.ai

---

## 💻 安装教程

### 🐧 Linux
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
npm install -g openclaw
openclaw start
```

### 🍎 macOS
```bash
brew install nodejs
npm install -g openclaw
openclaw start
```

### 🪟 Windows
```bash
winget install OpenJS.NodeJS.LTS
npm install -g openclaw
openclaw start
```

### 🐳 Docker
```bash
docker run -d -p 18789:18789 openclaw/openclaw
```

---

## ❓ 常见问题 FAQ

### Q1: 端口被占用？
```bash
lsof -i :18789
kill -9 <PID>
# 或使用其他端口
openclaw start --port 18888
```

### Q2: npm 安装失败？
```bash
npm cache clean --force
sudo npm install -g openclaw
```

### Q3: 无法连接API？
```bash
export HTTP_PROXY=http://127.0.0.1:7890
export HTTPS_PROXY=http://127.0.0.1:7890
```

---

## 🔧 疑难杂症解决

### 问题1: npm 安装失败
1. 检查 Node.js 版本: `node -v` (需要 v18+)
2. 清除缓存: `npm cache clean --force`
3. 使用管理员权限

### 问题2: Docker 启动失败
1. 检查 Docker: `sudo systemctl status docker`
2. 启动 Docker: `sudo systemctl start docker`
3. 查看日志: `docker logs <container_id>`

---

## 🛠️ 环境配置

### Node.js
```bash
# Ubuntu
curl -fsSL https://nodejs.org/dist/v20.x/node-v20.x-linux-x64.tar.xz | sudo tar -xJ -C /usr/local --strip-components=1
node -v
```

### Python
```bash
sudo apt install python3.10 python3-pip
python3 --version
```

---

## 🔗 衍生项目

| 项目 | ⭐ | 描述 |
|------|-----|------|
| [zeroclaw-labs/zeroclaw](https://github.com/zeroclaw-labs/zeroclaw) | 25,147 | 轻量级 AI 助手 |
| [dzhng/deep-research](https://github.com/dzhng/deep-research) | 18,539 | AI 研究助手 |
| [agent0ai/agent-zero](https://github.com/agent0ai/agent-zero) | 15,916 | Agent Zero 框架 |

---

## 💰 赞助

![支付宝赞助](https://raw.githubusercontent.com/yy1142274323/openclaw-handbook/main/alipay_qr.png)

---

*🤖 由 Jarvis 自动更新*

