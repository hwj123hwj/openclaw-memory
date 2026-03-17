# 已安装技能清单

## 当前安装

| 技能 | 用途 | 安装日期 | 来源 |
|------|------|----------|------|
| codex-orchestrator | 编排 Codex CLI 执行编程任务 | 早期 | 内置 |
| self-improving-agent | 自我改进学习技能 | 早期 | 内置 |
| find-skills | 帮助发现和安装其他技能 | 早期 | 内置 |
| Tavily (search/research/extract) | 专业搜索 API | 2026-03-16 | ClawHub |
| deep-research | 企业级深度研究 | 2026-03-17 | cmcm.bot |
| xiaohongshu-skills | 小红书自动化 | 早期 | 本地 |
| bilibili-video-helper | B站视频搜索分析 | 早期 | 本地 |

## 已删除

| 技能 | 删除日期 | 原因 |
|------|----------|------|
| bilibili-toolkit | 2026-03-15 | 整合到其他技能 |
| variflight | 2026-03-15 | 不再使用 |
| media-analyze | 2026-03-17 | 与 Tavily/deep-research 功能重叠 |

## 配置要求

### Tavily
- 配置文件: `~/.claude/settings.json`
- 需要 API Key: https://tavily.com

### deep-research
- 安装位置: `~/.openclaw/workspace/skills/deep-research/`
- 依赖: Python 3, requests

---

*最后更新: 2026-03-17*