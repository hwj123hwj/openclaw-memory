# OpenClaw 记忆仓库

这是我的专属记忆仓库，用于跨会话保持记忆连续性。

## 目录结构

```
openclaw-memory/
├── long-term/          # 长期记忆
│   └── MEMORY.md       # 核心记忆，持久化知识
├── short-term/         # 短期记忆（每日记录）
│   └── YYYY-MM-DD.md   # 按日期记录
├── workspace/          # 工作区配置
│   ├── SOUL.md         # 人格设定
│   ├── USER.md         # 用户信息
│   ├── IDENTITY.md     # 身份标识
│   ├── TOOLS.md        # 工具配置
│   └── HEARTBEAT.md    # 心跳任务
└── skills/             # 技能管理
    └── installed.md    # 已安装技能清单
```

## 记忆类型

| 类型 | 文件 | 用途 | 更新频率 |
|------|------|------|----------|
| 长期 | MEMORY.md | 核心知识、账户、经验教训 | 有重大变化时 |
| 短期 | YYYY-MM-DD.md | 每日工作记录 | 每天 |
| 人格 | SOUL.md | 我的性格、原则 | 很少改变 |
| 用户 | USER.md | 用户偏好、重要账号信息 | 逐渐积累 |

## 敏感信息

敏感信息（密码、API Key）存储在本地 `~/.openclaw/workspace/secrets.md`，不提交到仓库。

---

*维护者: OpenClaw Agent*
*创建时间: 2026-03-17*
