# 电商大师技能库

> AI Agent Skills for Ecommerce —— 跨境扩张、支付集成、前端搭建、店铺管理

## 定位

为独立开发者和中小卖家提供一套可安装的 AI Agent 电商技能，覆盖从市场策略到店铺运营的全链路。

## 核心理念

> 不建站则已，建站则专业。让 AI 帮你做电商决策，你只需专注产品和客户。

- **策略先行**——先评估市场再行动，数据驱动跨境扩张
- **支付闭环**——Stripe 集成覆盖订阅、发票、风控全流程
- **前端专业**——遵循 ecommerce 最佳实践，不做低转化率的页面
- **店铺提效**——Shopify API 自动化产品管理

## 技能清单

| 环节 | 技能 | 描述 | 来源 |
|------|------|------|------|
| 🌍 跨境策略 | `cross-border-expansion` | 跨境电商扩张：市场评分、物流方案、税务合规、支付本地化 | [衍生](https://skills.sh/nexscope-ai/ecommerce-skills/cross-border-ecommerce) |
| 💳 支付集成 | `payment-integration` | Stripe 支付集成：订阅管理、发票自动化、收入分析、风控 | [衍生](https://skills.sh/claude-office-skills/skills/stripe-payments) |
| 🏪 前端搭建 | `storefront-builder` | 电商前端最佳实践：组件模式、SEO、移动适配、后端集成 | [衍生](https://skills.sh/medusajs/medusa-agent-skills/storefront-best-practices) |
| 🛒 店铺管理 | `shopify-manager` | Shopify 产品管理：GraphQL API 创建/更新/批量导入 | [衍生](https://skills.sh/jezweb/claude-skills/shopify-products) |

## 安装

整库安装（推荐）：

```bash
npx skills add skills-repo/ecommerce-master -g -y
```

单技能安装（将 `<skill>` 替换为子技能目录名，例如 `cross-border-expansion`）：

```bash
npx skills add skills-repo/ecommerce-master@cross-border-expansion -g -y
```

## 子技能目录

本仓库每个子技能可单独安装，路径长期稳定、不会改名：

| 子技能 | 安装命令 | 适用 |
|--------|----------|------|
| cross-border-expansion | `npx skills add skills-repo/ecommerce-master@cross-border-expansion -g -y` | 跨境电商扩张：市场评分、物流、税务合规、支付本地化 |
| payment-integration | `npx skills add skills-repo/ecommerce-master@payment-integration -g -y` | Stripe 支付集成：订阅、发票、催款、收入分析、风控 |
| storefront-builder | `npx skills add skills-repo/ecommerce-master@storefront-builder -g -y` | 电商前端最佳实践：组件、SEO、移动适配、后端集成 |
| shopify-manager | `npx skills add skills-repo/ecommerce-master@shopify-manager -g -y` | Shopify 产品管理：GraphQL API、变体、CSV 批量导入 |

## 快速开始

```bash
npx skills add skills-repo/ecommerce-master@cross-border-expansion -g -y
npx skills add skills-repo/ecommerce-master@payment-integration -g -y
npx skills add skills-repo/ecommerce-master@storefront-builder -g -y
npx skills add skills-repo/ecommerce-master@shopify-manager -g -y
```

## 推荐工作流

```
市场评估 → 前端搭建 → 支付集成 → 店铺运营
cross-      storefront-   payment-     shopify-
border      builder       integration  manager
```

## 许可

MIT