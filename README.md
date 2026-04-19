# AI Expert Skills

99个专业AI技能包，覆盖电商、内容创作、职场、健康、法律等10大品类。每个技能遵循 [Agent Skills Standard](https://agentskills.io) 规范，兼容 OpenClaw/ClawHub/SkillHub/Coze 等平台。

## 已发布技能 (3/99)

| 技能 | 品类 | 版本 | 描述 |
|------|------|------|------|
| [ai-skill-collector](./skills/ai-skill-collector/) | 数据采集 | 1.0.0 | AI技能数据采集器，三层爬虫策略自动采集各大平台技能数据 |
| [content-factory](./skills/content-factory/) | 内容创作 | 1.0.0 | 多智能体内容生产系统，5个Agent一份素材生成8种格式 |
| [market-researcher](./skills/market-researcher/) | 商业策略 | 1.0.0 | 市场调研专家，TAM/SAM/SOM计算+竞争分析+定价策略 |

## 安装

### ClawHub/SkillHub
```bash
npx clawhub@latest install ai-skill-collector
npx clawhub@latest install content-factory
npx clawhub@latest install market-researcher
```

### 手动安装
```bash
# 克隆仓库
git clone https://github.com/zhaohongyuziranerran/ai-expert-skills.git

# 复制到OpenClaw技能目录
cp -r ai-expert-skills/skills/ai-skill-collector ~/.openclaw/workspace/skills/
cp -r ai-expert-skills/skills/content-factory ~/.openclaw/workspace/skills/
cp -r ai-expert-skills/skills/market-researcher ~/.openclaw/workspace/skills/
```

### Coze 使用
将 `SKILL.md` 的内容作为 Coze Bot 的 System Prompt 使用即可。

## 技能品类规划 (99个)

| 品类 | 数量 | 代表技能 |
|------|------|----------|
| 电商运营 | 10 | 淘宝运营军师/小红书爆款军师/闲鱼赚钱军师 |
| 职场发展 | 10 | 面试教练/简历优化/职业规划/薪资谈判 |
| 内容创作 | 10 | 文案大师/短视频脚本/标题生成器/SEO优化 |
| 金融理财 | 8 | 股票入门/税务申报/理财规划/投资分析 |
| 法律咨询 | 5 | 律师助手/合同审查/劳动维权 |
| 健康生活 | 8 | 减肥塑形/养生理疗/健身计划/心理倾诉 |
| 编程开发 | 8 | 编程助手/浏览器自动化/数据分析/SEO |
| 教育学习 | 8 | 考研军师/托福雅思/留学申请/驾照考试 |
| 商业策略 | 7 | 创业融资/商业计划书/副业赚钱/品牌命名 |
| 设计创意 | 5 | Logo设计/室内设计/美妆/菜谱 |

## 贡献

欢迎贡献新技能！请遵循 [Agent Skills Standard](https://agentskills.io/specification) 规范。

## 许可证

MIT-0 — 自由使用、修改和分发。

---

*由 AI Expert Skills 团队维护 | 基于Coze 99个顶级Bot Prompt深度优化*
