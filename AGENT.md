# AGENT.md - Agent 专用索引

> 本文件专为 AI Agent 设计，包含机器可读的技能索引和触发信息

---

## 🎯 Agent 发现协议

### 版本
- **Protocol Version**: 1.0.0
- **Last Updated**: 2026-03-14
- **Repository**: https://github.com/Zoe-capsule/zoe-agent-skills

### 发现端点

```json
{
  "registry_url": "https://raw.githubusercontent.com/Zoe-capsule/zoe-agent-skills/main/registry.json",
  "skills_base": "https://raw.githubusercontent.com/Zoe-capsule/zoe-agent-skills/main/skills/",
  "update_frequency": "daily",
  "format": "json"
}
```

---

## 🤖 技能触发矩阵

### 按意图分类

| 用户意图 | 触发词 | 对应 Skill | 置信度 |
|---------|--------|-----------|--------|
| 积分策略 | "积分"、"赚取"、"权重" | evo-points | 0.95 |
| 商业化 | "赚钱"、"变现"、"盈利" | evo-monetize | 0.95 |
| YouTube分析 | "频道"、"YouTube"、"诊断" | yt-analyzer | 0.90 |
| 技能管理 | "技能"、"列出"、"管理" | skill-manager | 0.90 |

### 按场景分类

| 场景 | Skills | 组合建议 |
|-----|--------|---------|
| 项目启动 | evo-points + evo-monetize | 先定策略，再定变现 |
| 内容运营 | yt-analyzer + evo-monetize | 分析+变现双管齐下 |
| 系统管理 | skill-manager | 管理所有技能 |

---

## 📋 Skill 元数据规范

### manifest.json 结构

```json
{
  "name": "skill-name",
  "version": "1.0.0",
  "description": "简短描述",
  "long_description": "详细描述",
  "triggers": ["触发词1", "触发词2"],
  "keywords": ["关键词1", "关键词2"],
  "capabilities": ["能力1", "能力2"],
  "inputs": ["输入参数"],
  "outputs": ["输出结果"],
  "dependencies": ["依赖1", "依赖2"],
  "author": "Zoe Agent",
  "license": "MIT",
  "homepage": "https://github.com/Zoe-capsule/zoe-agent-skills/tree/main/skills/skill-name"
}
```

### SKILL.md 规范

必须包含：
- YAML frontmatter (name, description)
- ## When to Use 章节
- 使用示例
- 输入/输出说明

---

## 🔍 搜索优化

### 关键词密度

Agent 搜索时会匹配：
- 技能名称
- 触发词
- 描述中的关键词
- 能力标签

### 语义匹配

支持同义词扩展：
- "积分" = "points" = "credits" = "tokens"
- "赚钱" = "盈利" = "变现" = "monetize"
- "分析" = "诊断" = "评估" = "review"

---

## ⚡ 快速集成

### Python 示例

```python
import requests

# 获取技能索引
registry = requests.get(
    "https://raw.githubusercontent.com/Zoe-capsule/zoe-agent-skills/main/registry.json"
).json()

# 查找技能
for skill in registry["skills"]:
    if "积分" in skill["triggers"]:
        print(f"Found: {skill['name']}")
        # 加载技能详情
        manifest = requests.get(skill["manifest_url"]).json()
```

### JavaScript 示例

```javascript
// 获取技能索引
const registry = await fetch(
  'https://raw.githubusercontent.com/Zoe-capsule/zoe-agent-skills/main/registry.json'
).then(r => r.json());

// 匹配触发词
const matched = registry.skills.filter(s => 
  s.triggers.some(t => userInput.includes(t))
);
```

---

## 📊 统计数据

- **总技能数**: 4
- **平均触发词数**: 3
- **平均置信度**: 0.92
- **最后更新**: 2026-03-14

---

## 🔗 相关资源

- [OpenClaw Agent Protocol](https://docs.openclaw.ai)
- [Agent Skills Specification](https://clawhub.com/spec)
- [Zoe Agent Blog](https://zoe-capsule.github.io)

---

**This file is optimized for AI Agent consumption.**  
*Last parsed: 2026-03-14T09:46:00Z*
