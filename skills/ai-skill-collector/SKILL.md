---
name: ai-skill-collector
version: 1.0.0
description: >
  AI技能数据采集器 - 自动采集SkillHub/Coze/ClawHub等平台的技能数据，
  支持URL转Markdown、Crawl4AI智能提取、Scrapling自适应爬取三层策略。
  Use when: 采集技能、抓取技能包、扫描技能商店、采集Coze/SkillHub/ClawHub、
  技能数据采集、爬取AI技能、skill collector、crawl skills。
license: MIT-0
metadata:
  author: ai-expert-skills
  category: data-collection
  language: zh-CN
---

# AI技能数据采集器

三层爬虫策略，自动采集各大AI平台的技能/插件/Bot数据。

## When to Use

- 用户说"采集技能"、"扫描技能商店"、"抓取技能包"
- 用户需要采集Coze/SkillHub/ClawHub等平台数据
- 用户想比较不同平台的技能数据
- 用户需要搭建技能监控或价格追踪系统

## Required Inputs

- target_platform: 目标平台（coze/skillhub/clawhub/github/npm/gitee/all）
- category: 分类筛选（选填，如"代码助手"/"内容创作"）
- depth: 采集深度（quick快速/all全量，默认quick）

## Workflow

1. **确定目标**：根据用户指定的平台和分类确定采集范围
2. **选择策略**：
   - 第1层：URL转Markdown（最快，无需浏览器）
     - `markdown.new/{url}` — Cloudflare服务，适合新闻/博客/CMS站点
     - `defuddle.md/{url}` — Obsidian服务，支持社交媒体
     - `r.jina.ai/{url}` — Jina AI Reader，通用备选
   - 第2层：Crawl4AI（智能提取，支持LLM结构化）
     - 异步Playwright驱动
     - 自动去噪、Markdown输出
     - 支持CSS选择器和LLM提取策略
     - 支持JS渲染的动态页面
   - 第3层：Scrapling（自适应反爬，兜底方案）
     - 自适应网站结构变化
     - 智能元素定位
     - 反指纹检测
3. **执行采集**：按选定策略采集目标平台
4. **去重整理**：按name+source去重，合并多源数据
5. **输出结果**：保存为JSON文件

## 采集目标

| 平台 | 类型 | 推荐策略 |
|------|------|----------|
| Coze商店 | SPA | 第2层 |
| 腾讯SkillHub | SPA | 第2层 |
| ClawHub | API | 直接请求 |
| GitHub | API | 直接请求 |
| npm | API | 直接请求 |
| Gitee | API | 直接请求 |

## Output Format

```json
{
  "timestamp": "2026-04-19T09:00:00",
  "source": "skillhub",
  "total": 150,
  "skills": [
    {
      "name": "技能名",
      "description": "描述",
      "url": "链接",
      "category": "分类",
      "stars": 100,
      "downloads": 5000,
      "price": "free",
      "source": "skillhub"
    }
  ]
}
```

## Error Handling

- 目标站点返回403/429：自动降级到下一层策略
- API rate limit：3秒退避重试，最多3次
- 网络超时：跳过当前目标，继续下一个
- 数据解析失败：记录原始响应，继续采集

## 技术栈

- Python 3.12 + Crawl4AI + Scrapling
- Playwright (Chromium headless)
- markdownify + readability-lxml
- requests + PySocks (代理支持)
