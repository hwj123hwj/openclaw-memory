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

## 已安装技能

| 技能 | 用途 | 安装日期 |
|------|------|----------|
| codex-orchestrator | 编排 Codex CLI 执行编程任务 | 早期 |
| self-improving-agent | 自我改进学习技能 | 早期 |
| find-skills | 帮助发现和安装其他技能 | 早期 |
| Tavily (search/research/extract) | 专业搜索 API，带引用来源 | 2026-03-16 |
| deep-research | 企业级深度研究，生成万字报告 | 2026-03-17 |
| xiaohongshu-skills | 小红书自动化（发布、搜索、互动）| 早期 |
| bilibili-video-helper | B站视频搜索分析 | 早期 |
| DVCode (deepv-code) | AI 生图、代码生成、多模型切换 | 2026-03-17 |

**已删除**：bilibili-toolkit (2026-03-15)、variflight (2026-03-15)、media-analyze (2026-03-17)

---

## 技术经验

### 工具选择
- **Codex CLI** 比 acpx + ACP 协议更可靠（acpx 退出码 5 崩溃问题）
- **Tavily API** 是首选搜索方案，免费备选：必应中文 + 搜狗微信 + 今日头条

### API 限流应对
- 分批次、低频率请求
- B站：每次检查 30 个 UP 主，每个只取 1 个视频

### OpenClaw Cron
- 必须指定 `--to` 参数，否则飞书推送失败
- 时区转换：北京时间 = UTC+8

### 飞书发送视频
- `msg_type` 必须是 `media`，不是 `file`
- 需要先上传封面图和视频获取 key，再发送

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

### weijian.online Skills 展示网站
- bilibili-toolkit、bjtuo-classroom-query、idea-incubator、skill-browser-crawl

### Deep Research 技能
- 安装位置：`~/.openclaw/workspace/skills/deep-research/`
- 验证脚本：`python3 scripts/validate_report.py --report [path]`
- 模式：quick (2-5min) / standard (5-10min) / deep (10-20min) / ultradeep (20-45min)

### DVCode 技能
- 安装：`npm i -g deepv-code`
- 登录：`dvcode --login sk_live_xxx`
- AI 生图：`dvcode --output-format stream-json --yolo "/nanobanana auto 1k 提示词"`
- 代码生成：`dvcode --output-format stream-json --yolo "你的需求"`
- Token 有效期：15 天，自动续期
- 注意：需要配置代理才能使用

---

## 参考资料

### 热榜 JSON API
- 百度热搜：`https://top.baidu.com/api/board?platform=wise&tab=realtime`
- 今日头条：`https://www.toutiao.com/hot-event/hot-board/?origin=toutiao_pc`
- B站排行榜：`https://api.bilibili.com/x/web-interface/ranking/v2?rid=0&type=all`

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

## 更新日志

- 2026-03-17: 安装 DVCode 技能，添加代理配置，整理敏感信息到 secrets.md
- 2026-03-17: 删除 media-analyze，整理长期记忆结构，创建 GitHub 记忆仓库
- 2026-03-16: 安装 Tavily、media-analyze 技能
- 2026-03-15: 删除 bilibili-toolkit、variflight
- 2026-03-09: B站推荐系统测试通过
- 2026-03-05: 从 GitHub 恢复记忆