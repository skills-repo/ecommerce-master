---
name: ecommerce-master
description: "电商全链路 AI Agent 技能库：跨境扩张策略（市场评分/税务合规/物流/支付本地化）、Stripe 支付集成（订阅/发票/风控/对账）、Shopify 产品管理（GraphQL/CSV 批量）、电商前端搭建（组件/SEO/移动适配）。当用户要做跨境电商选品与落地、接入 Stripe 订阅与催款、批量管理 Shopify 商品、或搭建高转化电商前端时调用本技能，并据路由表进入对应子技能。"
metadata:
  architecture: superpower
  category: 电商
  platform: skills-repo
  version: 1.0.0
  created: 2026-08-09
  updated: 2026-08-09
tags:
  - ecommerce
  - cross-border
  - payment
  - storefront
  - shopify
  - stripe
---

# Ecommerce Master（电商大师 · 超级技能路由）

> 覆盖「市场策略 → 前端搭建 → 支付集成 → 店铺运营」的电商全链路。
> 本文件只做路由与判断，完整方法论下沉到 `references/`，重复确定性任务交给 `scripts/`。

## 何时使用

在以下任一情况触发本技能，并按路由表进入对应子技能：

- 规划跨境电商扩张：选市场、算落地成本、做税务/海关合规
- 接入或优化支付：Stripe 订阅、发票、催款（dunning）、风控、对账
- 上架 / 批量管理 Shopify 商品与变体
- 从零搭建或优化电商前端（组件、SEO、移动适配、性能）

## 能力索引（渐进式路由）

| 任务 | 进入 | 关键词（grep 线索） |
|------|------|---------------------|
| 跨境扩张策略 | `skills/cross-border-expansion` | cross-border, 跨境, 市场评分, VAT, IOSS, 物流, 关税 |
| 支付集成 | `skills/payment-integration` | stripe, 订阅, 发票, 催款, dunning, 对账, 风控, Radar |
| 店铺管理 | `skills/shopify-manager` | shopify, 产品, GraphQL, 变体, CSV 导入, 批量上架 |
| 前端搭建 | `skills/storefront-builder` | storefront, 前端, 组件, SEO, 结构化数据, 移动适配, 转化 |

## 内置脚本（确定性、可复现）

放在 `scripts/`，纯标准库、可独立运行、`--help` 可用，不改被检文件、不联网：

- `scripts/validate_product_feed.py --feed <file.csv|json>` — 按 `assets/product-feed-rules.json`
  校验商品信息流的必填字段、缺失令牌、数字/枚举约束，输出缺陷清单与计数。

用法示例：

```bash
python3 scripts/validate_product_feed.py --feed export/products.csv
python3 scripts/validate_product_feed.py            # 仅自检规则模板（应 0 错误）
```

## 参考手册（references/）

需要子技能装不下的决策增量时读取：

- `references/cross-border-compliance.md` — 按国税务/海关阈值、清关路径、落地成本建模
- `references/payment-integration-checklist.md` — Stripe 接入清单、Webhook 验签、争议退款
- `references/storefront-launch-playbook.md` — 组件优先级、SEO 结构化数据、性能预算、i18n

## 模板资源（assets/）

- `assets/product-feed-rules.json` — 商品信息流校验规则（含 `_comment`/`_note` 注释键）
- `assets/sample-product-feed.csv` — 合规样例商品流（0 缺陷，用作对照）

## 适用场景

- 独立开发者/中小卖家从零搭建跨境电商业务
- 评估目标市场并制定分阶段扩张路线图
- SaaS / 电商接入 Stripe 订阅、发票与收入分析
- 通过 Shopify API 或 CSV 批量管理产品目录
- 构建高转化率、移动友好、SEO 就绪的电商前端

## 限制

- 税率与法规变化频繁，最终决策需咨询当地持牌税务/法律顾问
- 运费、落地成本为方向性估算，实际取决于尺寸、货量与承运商报价
- Stripe 相关功能需对应账号、API Key，部分（Radar、Sigma）需额外付费
- Shopify 单个产品上限 100 变体 / 3 选项维度；CSV 导入最大 50MB
- 支付网关的安全合规实现细节以官方文档为准，不猜测 API 签名
