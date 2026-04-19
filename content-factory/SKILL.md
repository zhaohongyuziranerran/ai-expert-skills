---
name: content-factory
description: >
  多智能体内容生产系统，一份素材生成多种格式。包含5个专业Agent：Writer(写作)、
  Remixer(多平台改编)、Editor(编辑润色)、Scriptwriter(视频脚本)、
  Headline Machine(标题生成)。支持Twitter/LinkedIn/邮件/视频脚本等8种输出格式。
  Use when: 内容创作、多平台分发、品牌内容生产、社交媒体内容、内容改编、
  一键生成多种格式、content factory、multi-format content。
description_zh: "多智能体内容生产系统，一份素材生成多种格式"
description_en: "Multi-agent content production system, one source to many formats"
version: 1.0.0
license: MIT-0
metadata:
  author: ai-expert-skills
  category: content-creation
  language: zh-CN+en
---

# Content Factory — 多智能体内容生产系统

> One source → many formats. One system → consistent brand voice.

## When to Use

- 用户说"帮我生成多种格式的内容"、"一篇文章发多个平台"
- 用户需要将一份素材改编为社交媒体/邮件/视频脚本等
- 用户需要品牌内容一致性
- 用户需要标题生成和优化
- 用户需要视频脚本或短视频脚本

## Required Inputs

- source_content: 素材内容（文章/主题/研究笔记/脑暴dump）
- target_formats: 目标格式（twitter/linkedin/email/instagram/video/slides/quotes/faq，可多选）
- voice: 品牌语调（正式/随意/技术/温暖）
- audience: 目标受众（选填）

## Workflow

可运行完整流水线，或直接跳到任意Agent：

```
素材/主题/脑暴
      ↓
  [WRITER] → 长文草稿
      ↓
  [EDITOR] → 清晰+润色
      ↓
  [REMIXER] → Twitter/LinkedIn/邮件/标题/幻灯片
  [SCRIPTWRITER] → 视频脚本+动画钩子
  [HEADLINE MACHINE] → 20个标题按CTR排序
```

## The Agent Roster

| Agent | 角色 | 输入 | 输出 |
|-------|------|------|------|
| **Writer** | 长文写作 | 主题+研究+脑暴 | 文章/指南/通讯 |
| **Remixer** | 一对多改编 | 完成的内容 | Twitter/LinkedIn/邮件/标题/脚本 |
| **Editor** | 清晰+润色 | 草稿 | 出版级内容 |
| **Scriptwriter** | 视频+动画脚本 | 主题或内容 | 30秒钩子/视频脚本/Reels |
| **Headline Machine** | 标题+钩子 | 主题+受众+角度 | 20个标题按预估CTR排序 |

## Output Formats

### Twitter/X Thread
- 推文1：钩子，独立完整 — 不要以"Thread 🧵"开头
- 每条：一个观点，独立价值
- 最后一条：CTA或反思
- 无hashtag，短行，6-12条

### LinkedIn Post
- 开头用洞察，不用"我一直在想..."
- 150-300字为传播优化；真实故事可以更长
- 每1-2句换行
- 结尾提问驱动评论
- 3-5个hashtag

### Email Newsletter
- 主题行制造好奇（测试：你会打开吗？）
- 个人语调 — 像写给一个读者
- 一个CTA，清晰具体
- 200-350字

### 30-Second Video Script
- 开头钩子：3秒（什么抓住他们）
- 核心信息：20秒（回报）
- 收尾：7秒（CTA或反思）
- 每个节拍包含视觉方向注释

### 20 Headlines (by CTR)
| 公式 | 示例 |
|------|------|
| 数字+收益 | "7个方法让内容创作时间减半" |
| 提问 | "你是否把内容80%的价值留在了桌上？" |
| 反直觉 | "为什么发更少内容反而涨粉3倍" |
| 具体结果 | "一篇文章生成12种格式的精确系统" |

## Content Principles

**写这种：**
- 一条内容一个观点
- 具体胜过模糊
- 展示而非讲述
- 把有趣的放前面

**永远不写：**
- "深入探讨"、"织锦"、"利用"、"驾驭"、"运用"
- "激动地宣布"、"游戏规则改变者"、"革命性"
- 任何字面上适用于任何公司的内容

**人类测试：** 定稿前问："一个真人会这样对朋友说吗？"如果不会，重写。

## Error Handling

- 素材太短（<50字）：要求补充更多信息
- 格式不匹配受众：建议更合适的格式
- 内容过于技术：自动应用empathy-rewrite模板
