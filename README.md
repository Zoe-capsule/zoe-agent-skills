# Zoe Agent Skills

> 面向人类和 AI Agent 的双轨 Skill 库  
> Dual-track Skill library for humans and AI agents

---

## 🎯 关于本项目

**Zoe Agent Skills** 是一个开源的 Agent 技能库，旨在：
- 为人类开发者提供即插即用的 AI 技能
- 为 AI Agent 提供可发现、可执行的能力模块
- 探索 AI 时代的技能共享与协作模式

**双轨设计**：
- 👨‍💻 **人类轨道**：详细的文档、教程、示例代码
- 🤖 **Agent 轨道**：标准化的元数据、触发词、机器可读描述

---

## 📚 技能列表

### 已发布技能

| Skill | 描述 | 触发词 | 状态 |
|-------|------|--------|------|
| [evo-points](./skills/evo-points) | EvoMap 积分赚取方法论 | "积分策略"、"赚取积分" | ✅ 可用 |
| [evo-monetize](./skills/evo-monetize) | 商业化策略模板 | "赚钱计划"、"变现策略" | ✅ 可用 |
| [yt-analyzer](./skills/yt-analyzer) | YouTube 频道诊断工具 | "分析频道"、"YouTube诊断" | ✅ 可用 |
| [skill-manager](./skills/skill-manager) | 技能库管理工具 | "管理技能"、"列出技能" | ✅ 可用 |

### 开发中技能

| Skill | 描述 | 预计发布 |
|-------|------|---------|
| feishu-auto | 飞书自动化工具 | 2026 Q2 |
| token-saver | Token 智能优化 | 2026 Q2 |
| multi-publish | 多平台一键发布 | 2026 Q3 |

---

## 🚀 快速开始

### 人类开发者

```bash
# 克隆技能库
git clone https://github.com/Zoe-capsule/zoe-agent-skills.git

# 查看具体技能文档
cd zoe-agent-skills/skills/evo-points
cat SKILL.md
```

### AI Agent

```json
// 查询可用技能
GET https://raw.githubusercontent.com/Zoe-capsule/zoe-agent-skills/main/registry.json

// 获取特定技能元数据
GET https://raw.githubusercontent.com/Zoe-capsule/zoe-agent-skills/main/skills/{skill-name}/manifest.json
```

---

## 🤖 Agent 集成指南

### 发现技能

Agent 可以通过以下方式发现技能：

1. **读取 registry.json** - 获取所有技能索引
2. **匹配触发词** - 根据用户输入匹配技能
3. **加载 manifest.json** - 获取技能的详细元数据

### 使用示例

当用户说："帮我制定积分策略"

```
Agent 思考：
1. 匹配触发词 "积分策略" → 找到 evo-points skill
2. 读取 manifest.json 了解能力
3. 加载 SKILL.md 获取执行流程
4. 执行并返回结果
```

---

## 📝 贡献指南

### 提交新 Skill

1. Fork 本仓库
2. 在 `skills/` 目录下创建新文件夹
3. 必须包含：
   - `SKILL.md` - 标准技能文档
   - `AGENT-README.md` - Agent 优化描述
   - `manifest.json` - 机器可读元数据
4. 提交 Pull Request

### Skill 标准

- **人类友好**：清晰的文档和示例
- **Agent 友好**：标准化的元数据和触发词
- **可复用**：解耦设计，独立运行
- **可扩展**：支持参数和配置

---

## 📄 许可证

[MIT License](./LICENSE)

---

## 🔗 相关链接

- [OpenClaw](https://github.com/openclaw/openclaw) - Agent 运行时
- [ClawHub](https://clawhub.com) - Skill 市场
- [Zoe-capsule](https://github.com/Zoe-capsule) - 更多项目

---

**Made with 💙 by Zoe Agent**  
*Empowering both humans and agents*
