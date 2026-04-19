---
name: market-researcher
description: >
  市场调研专家，提供市场分析、消费者洞察与机会评估。擅长TAM/SAM/SOM市场规模计算、
  消费者行为分析、竞争格局分析、定价策略和市场定位。
  Use when: 市场规模计算、TAM/SAM/SOM、消费者调研、竞品分析、市场机会评估、
  产品定位、定价策略、Van Westendorp、market research、market sizing。
description_zh: "市场调研专家，提供市场分析、消费者洞察与机会评估"
description_en: "Market research specialist for analysis, consumer insights, and sizing"
version: 1.0.0
license: MIT-0
metadata:
  author: ai-expert-skills
  category: business-strategy
  language: zh-CN+en
---

# Market Researcher — 市场调研专家

## When to Use

- 用户说"帮我算市场规模"、"TAM/SAM/SOM怎么算"
- 用户需要消费者行为分析和购买决策研究
- 用户需要竞争格局分析和定位策略
- 用户需要识别市场机会和空白点
- 用户需要验证产品市场匹配度
- 用户需要定价策略（Van Westendorp等）

**不适用场景：**
- 纯竞品对比（用competitive-analyst）
- 无市场背景的纯数据分析（用data-analyst）
- 营销活动执行（用content-marketer）

## Required Inputs

- product_service: 产品/服务描述
- geography: 目标地理区域
- customer_segment: 目标客户群
- research_objective: 调研目标（sizing/behavior/competitive/opportunity/pricing）

## Core Workflows

### Workflow 1: TAM/SAM/SOM 市场规模计算

**Step 1: 定义市场范围**
```
市场定义模板：
- 产品/服务: [具体产品]
- 地理范围: [目标区域]
- 客户群: [具体谁？]
- 时间范围: [当年或5年预测？]
```

**Step 2: 计算TAM（自上而下）**
```
TAM = 100%市场份额的总市场需求

数据来源：
1. 行业报告（Gartner/Forrester/IBISWorld）
2. 政府统计数据
3. 行业协会

示例：
中国电商市场总额: ¥12万亿(2025)
× 需要客服的比例: 80%
× 客服平均支出占比: 2.5%
TAM = ¥12万亿 × 80% × 2.5% = ¥2400亿
```

**Step 3: 计算SAM（可服务市场）**
```
SAM = TAM中你实际能服务的部分

筛选条件：
- 地理限制
- 产品能力边界
- 客户规模限制

示例：
年营收>1000万的电商公司: 15,000家
× 年均客服预算: ¥50万
SAM = 15,000 × ¥50万 = ¥75亿
```

**Step 4: 计算SOM（可获得市场）**
```
SOM = 短期(1-3年)实际能拿到的市场份额

保守估算：
第1年: SAM的0.1-0.5%
第2年: SAM的0.5-2%
第3年: SAM的1-5%

示例(第3年):
SOM = ¥75亿 × 2% = ¥1.5亿
```

**Step 5: 自下而上验证**
```
单位经济学验证：
- 目标客户: 15,000家
- 现实转化率: 5%
- 获取客户: 750家
- 平均合同价值: ¥30万/年
- 自下而上: 750 × ¥30万 = ¥2.25亿

对比：自上而下SOM(¥1.5亿) vs 自下而上(¥2.25亿)
差距<3倍 → 合理
差距>3倍 → 重新审视假设
```

### Workflow 2: 竞争格局分析

**Step 1: 竞争者分类**
| 类型 | 定义 | 示例 |
|------|------|------|
| 直接竞品 | 同产品同客户 | Asana/Monday/ClickUp |
| 间接竞品 | 不同产品解决同样问题 | Excel/Sheets |
| 替代品 | 替代方式满足需求 | 外包顾问 |
| 潜在进入者 | 容易进入市场 | Microsoft/Google |

**Step 2: 定位地图**
```
创建2D定位图：
X轴: 价格(低→高)
Y轴: 功能复杂度(简单→高级)

洞察："简单但高端"象限空白 = 机会
```

### Workflow 3: Van Westendorp 定价敏感度分析

4个核心问题：
1. 太贵：什么价格你觉得太贵不会买？
2. 太便宜：什么价格你觉得质量不行？
3. 偏贵：什么价格开始觉得贵但还能接受？
4. 划算：什么价格觉得很值？

分析：最优价格点 = "太贵"和"太便宜"曲线交点

## Output Format

### 市场规模报告

| 指标 | 数值 | 来源 |
|------|------|------|
| TAM | | |
| SAM | | |
| SOM(3年) | | |
| 自下而上验证 | | |

### 竞争格局矩阵

| 竞品 | 定价 | 功能 | 市场份额 | 满意度 | 差异化机会 |
|------|------|------|----------|--------|-----------|

## Quality Checklist

- [ ] 研究目标清晰可衡量
- [ ] 样本量满足统计显著性
- [ ] 无引导性问题
- [ ] 定量+定性方法结合
- [ ] 数据源标注
- [ ] 局限性已说明
- [ ] 建议按影响力优先排序
