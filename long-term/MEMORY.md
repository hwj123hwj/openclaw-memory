# MEMORY.md - 长期记忆

## 核心原则

**代码分工**：所有写代码工作交给 Codex，我负责需求分析、方案设计、编写需求文档、调用 Codex 和验证结果。

---

## 系统配置

### 代理 (Clash)
- Docker 容器：`clash-new`
- 端口：7890 (HTTP/SOCKS5)
- 使用命令：
  ```bash
  export http_proxy="http://127.0.0.1:7890"
  export https_proxy="http://127.0.0.1:7890"
  ```

---

## 技术经验

### 工具选择
- **Codex CLI** 比 acpx + ACP 协议更可靠（acpx 退出码 5 崩溃问题）
- **Tavily API** 是首选搜索方案，免费备选：必应中文 + 搜狗微信 + 今日头条

---

## 账户信息 🔐

> ⚠️ 敏感信息存储在本地 `~/.openclaw/workspace/secrets.md`，不提交到仓库

### 服务器
- dell-server / ubuntu

### PostgreSQL
- 127.0.0.1:5433 / bili

### Bilibili
- UID: 1512253857 / Cookie 已保存

### GitHub
- 用户名: hwj123hwj
- 技术经验仓库: https://github.com/hwj123hwj/tech-breakthroughs

---

## 项目状态

---

## 工具配置

### DVCode (deepv-code)
- **安装**: `npm i -g deepv-code`
- **登录**: `dvcode --login sk_live_xxx`
- **AI 生图**: `dvcode --output-format stream-json --yolo "/nanobanana auto 1k 提示词"`
- **代码生成**: `dvcode --output-format stream-json --yolo "你的需求"`
- **Token 有效期**: 15 天，自动续期
- **注意**: 需要配置代理才能使用

---

## 参考资料

### 子 Agent 使用
```javascript
sessions_spawn({
  task: "任务描述",
  mode: "run",
  runTimeoutSeconds: 180-300
})
```

### Tavily 配置
- 配置文件: `~/.claude/settings.json`
- 获取 API Key: https://tavily.com

---

## Agent 架构

| Agent | 角色 | 飞书账号 | 技能 |
|-------|------|----------|------|
| **main** | 编程助手 | main-account | codex-orchestrator, tavily, deep-research 等 |
| **life-assistant** | 生活助手 | life | xiaohongshu-skills, weather, agent-reach |

**飞书账号配置：**
- `main-account`: App ID `cli_a92db4ed7a78dcca` → 绑定 main
- `life`: App ID `cli_a92011531d385cc5` → 绑定 life-assistant

**文件位置：**
- life-assistant workspace: `/home/ubuntu/.openclaw/agents/life-assistant/workspace`
- 全局配置: `/home/ubuntu/.openclaw/openclaw.json`

---

## 更新日志

- 2026-03-21: 恢复 DVCode 工具配置（非技能，但重要工具）
- 2026-03-21: 精简长期记忆，删除动态信息（已安装技能列表、项目状态、API 详情、操作步骤）
- 2026-03-19: 添加 QQ 邮箱管理能力，同步配置给 life-assistant
- 2026-03-17: 安装 DVCode（全局 npm 包），添加代理配置，整理敏感信息到 secrets.md
- 2026-03-17: 删除 media-analyze，整理长期记忆结构，创建 GitHub 记忆仓库
- 2026-03-16: 安装 Tavily、media-analyze 技能
- 2026-03-15: 删除 bilibili-toolkit、variflight
- 2026-03-09: B站推荐系统测试通过
- 2026-03-05: 从 GitHub 恢复记忆