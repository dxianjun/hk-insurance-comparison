---
name: hk-insurance-comparison
description: 香港保险新产品对比分析技能。当用户提及香港保险、港险对比、储蓄险/分红险产品对比、医疗险、危疾险/重疾险、香港保险公司排名、分红实现率、港险投保建议、保费测算、IRR、单利、FNA、财务需求分析、计划书对比、保险优惠、保费折扣、预缴利率、周大福、万通、忠意、安达、太保、太寿、立桥、苏黎世、保泰、恒安标准等话题时触发。提供香港全部经营人寿保险的公司热门储蓄/分红险、医疗险、危疾险产品的结构化对比分析，包括产品参数、IRR、单利、分红实现率、保费测算、FNA需求分析、计划书对比、优惠信息和市场趋势。包含交互式Web应用(hk-insurance-web.vercel.app)和GitHub仓库(github.com/dxianjun/hk-insurance-web)。This skill should be used when users ask about Hong Kong insurance product comparisons, savings/endowment insurance plans, medical insurance, critical illness insurance, dividend fulfillment rates, premium calculations, IRR, simple interest, FNA, financial needs analysis, proposal comparison, insurance promotions, or insurance company rankings in Hong Kong. Includes interactive web app and GitHub repo.
agent_created: true
---

# 香港保险新产品对比分析

## Overview

提供香港全部经营人寿保险的公司（23家）热门保险产品的**全流程**对比分析，覆盖六大功能模块：
1. **储蓄/分红险对比** — 产品核心参数、IRR、单利、现金价值模拟、分红实现率
2. **医疗险对比** — 高端医疗险、自愿医保（VHIS）对比及保费测算
3. **危疾险对比** — 重疾险保障范围、多次赔付、保费对比
4. **FNA财务需求分析** — 客户需求诊断、保障缺口量化、产品方案匹配
5. **计划书对比** — 多家公司计划书并排对比、关键指标解读
6. **产品优惠信息** — 预缴利率、保费折扣、保费回赠、组合优惠实时汇总

帮助用户（投保人、经纪人、财富规划师）完成从"需求诊断 → 产品筛选 → 计划书对比 → 优惠叠加"的全流程投保决策。

## 🖥️ Interactive Web App

**线上应用**: https://hk-insurance-web.vercel.app
**GitHub仓库**: https://github.com/dxianjun/hk-insurance-web

交互式单页Web应用，覆盖全部23家保险公司，包含9个Tab：

| Tab | 功能 | 数据来源 |
|-----|------|---------|
| 1. 储蓄/分红险 | 22款产品对比，IRR+单利双指标，多维筛选 | `/data/savings.json` |
| 2. 保险公司 | 23家档案、评级、官网链接 | `/data/companies.json` |
| 3. 医疗/危疾险 | 高端医疗+VHIS+危疾三组独立筛选 | `/data/medical.json` `/vhis.json` `/ci.json` |
| 4. 分红实现率 | 23家公司历史趋势+多选筛选 | `/data/dividend.json` |
| 5. 优惠信息 | 预缴利率+保费折扣实时汇总 | `/data/promotions.json` |
| 6. 保费测算 | 16款产品年缴现金价值模拟 | `/data/premium.json` |
| 7. 市场趋势 | IA统计+监管政策+产品发布时间线 | `/data/market-trends.json` |
| 8. FNA录入 | 客户信息录入+保障目的+保费占比 | 前端计算 |
| 9. FNA推荐 | 需求分析报告+方案推荐 | 前端计算 |

**技术特性**：
- 数据动态加载（fetch /data/*.json，内嵌 fallback）
- 用户手动刷新按钮 + 每5分钟自动检测版本更新
- Service Worker 离线缓存
- 骨架屏加载动画 + 更新日志 Modal
- 定时爬虫自动更新数据（GitHub Actions 每天 HKT 06:00）

## When to Use

在以下场景触发本技能：

- 用户提及"香港保险"、"港险"、"港险对比"等关键词
- 用户想对比具体保险公司的储蓄险/分红险产品
- 用户询问香港保险公司排名、市场份额
- 用户询问分红实现率、分红历史表现
- 用户询问香港保险市场趋势、政策变化
- 用户需要香港保险投保建议或推荐
- 用户询问医疗险、高端医疗险、自愿医保（VHIS）
- 用户询问危疾险、重疾险、严重疾病保障
- 用户需要保费测算、保费估算、现金价值模拟
- 用户询问IRR、单利、内部收益率、收益率对比
- 用户提及具体公司名（友邦/保诚/宏利/安盛/永明/富卫/汇丰/中银/恒生/国寿海外/安达/周大福/太寿/万通/太保/忠意/立桥/富邦/香港人寿/香港年金等）+ 保险相关话题
- 用户需要FNA财务需求分析、保障缺口评估
- 用户想对比多家公司计划书、了解计划书怎么看
- 用户询问保险优惠、保费折扣、预缴利率、保费回赠
- 用户需要投保建议或推荐方案

## Quick Reference — 23家保险公司速查

| # | 公司 | 英文名 | 官网 | 核心标签 |
|---|------|--------|------|---------|
| 1 | 汇丰人寿 | HSBC Life | https://life.hsbc.com.hk/ | 银行系巨头，高净值客户 |
| 2 | 中银人寿 | BOC Group Life | https://www.bocgroup.com.hk/ | 中资银行系，月悦出息5%派息 |
| 3 | 友邦保险 | AIA | https://www.aia.com.hk/ | 品牌第一，分红最稳，30年IRR 6.5% |
| 4 | 中国人寿（海外） | China Life (Overseas) | https://www.chinalife.com.hk/zh-hk | 央企，人民币保单最优 |
| 5 | 宏利 | Manulife | https://www.manulife.com.hk/zh-hk/individual.html | 10年IRR最高(4.29%)，6年回本 |
| 6 | 保诚保险 | Prudential | https://www.prudential.com.hk/tc/ | 产品线丰富，28年达6.5%，波动大 |
| 7 | 富卫人寿 | FWD | https://www.fwd.com.hk/zh/ | 数字化，增速最快，25年达6.5% |
| 8 | 恒生保险 | Hang Seng Insurance | https://www.hangseng.com/insurance/ | 银行系，本地渠道 |
| 9 | 香港永明金融 | Sun Life | https://www.sunlife.com.hk/ | 评级最高(AA)，保证IRR 1%最高 |
| 10 | 安盛保险 | AXA | https://www.axa.com.hk/zh | 实现率最高，12种货币，提领后IRR反升 |
| 11 | 周大福人寿 | CTF Life | https://corpweb.ctflife.com.hk/sc | 连续9年分红100%，财富跃进选项 |
| 12 | 太寿香港 | China Taiping Life HK | https://tplhk.cntaiping.com/sc/ | 央企，跨境养老生态 |
| 13 | 安达人寿 | Chubb Life | https://www.chubblifehk.com/zh/ | 四大全优评级(AA/Aa3/A++)，保证7年回本 |
| 14 | 万通保险 | YF Life | https://www.yflife.com/sc/ | 年金转换权，分红实现率105% |
| 15 | 太保寿险香港 | CPIC Life HK | https://www.cpiclifehk.com.hk/sc/homePage | 央企，20年IRR 6.1% |
| 16 | 香港年金公司 | HKMC Annuity | https://www.hkmc.com.hk/ | 政府背景，终身固定年金 |
| 17 | 忠意人寿 | Generali Life | https://www.generali.com.hk/ZH_CN/ | 中期收益天花板(20年IRR 6.15%) |
| 18 | 香港富邦人寿 | Fubon Life HK | https://www.fubonlife.com.hk/life_hk/html/tc/ | 台资金融集团 |
| 19 | 香港人寿 | Hong Kong Life | https://www.hklife.com.hk/sc/home/index.html | 本地经营25年 |
| 20 | 立桥人寿 | Well Link Life | https://www.wli.com.hk/ | 保证单利4.75%，类定期存款 |
| 21 | 苏黎世人寿 | Zurich Life HK | https://life.zurich.com.hk/sc/ | 瑞士巨头，瑞盈15年IRR破6%，IUL保底3% |
| 22 | 保泰人寿 | Bowtie Life | https://www.bowtie.com.hk/ | 香港首家虚拟保险公司，零佣金纯保障 |
| 23 | 恒安标准人寿(亚洲) | Heng An Standard Life Asia | https://www.hengansl.com.hk/tc | 投资相连保险为主，300+基金选择 |

## Workflow

### Step 1: 识别用户需求类型

根据用户提问判断需求类型：

| 需求类型 | 典型提问 | 加载参考文件 |
|---------|---------|------------|
| 储蓄/分红险对比 | "友邦和保诚的储蓄险哪个好？" | `product-comparison.md` + `company-profiles.md` |
| IRR/单利对比 | "哪款储蓄险IRR最高？""20年单利多少？" | `product-comparison.md` + `premium-calculator.md` |
| 医疗险对比 | "哪家高端医疗险好？" | `health-critical-illness.md` + `company-profiles.md` |
| 危疾险对比 | "友邦和保诚的重疾险怎么选？" | `health-critical-illness.md` + `company-profiles.md` |
| 分红分析 | "哪家分红实现率最高？" | `dividend-fulfillment.md` + `company-profiles.md` |
| 保费测算 | "30岁买储蓄险大概多少保费？" | `premium-calculator.md` + `product-comparison.md` |
| 市场趋势 | "2025年港险有什么变化？" | `market-trends.md` |
| 综合推荐 | "我该买哪家港险？" | 全部参考文件 |
| 公司信息 | "介绍一下宏利"或"周大福人寿怎么样？" | `company-profiles.md` |
| VHIS自愿医保 | "香港自愿医保哪间好？" | `health-critical-illness.md` |
| **FNA需求分析** | "我需要什么保险？""帮我分析保障缺口" | `fna-guide.md` + `company-profiles.md` |
| **计划书对比** | "计划书怎么看？""帮我对比这几份计划书" | `proposal-guide.md` + `product-comparison.md` + `premium-calculator.md` |
| **产品优惠** | "哪家保险优惠最大？""预缴利率多少？" | `promotions.md` + `premium-calculator.md` |
| **投保全流程** | "我想买港险，该怎么做？" | `fna-guide.md` → `product-comparison.md` → `proposal-guide.md` → `promotions.md` |

### Step 2: 加载参考文件作为基线

使用 Read 工具加载技能目录下 `references/` 中对应的参考文件，作为**基线知识**（baseline），而非最终答案：

- `references/company-profiles.md` — 23家保险公司基础信息、官网、信用评级、市场份额
- `references/product-comparison.md` — 热门储蓄/分红险产品详细对比（含IRR和单利）、按需求推荐
- `references/health-critical-illness.md` — 高端医疗险、VHIS自愿医保、危疾险产品详细对比
- `references/dividend-fulfillment.md` — 分红实现率历史数据、投资组合风格、选购建议
- `references/market-trends.md` — 市场数据、监管政策、行业趋势、新产品发布时间线
- `references/premium-calculator.md` — 保费测算模拟、现金价值增长表、各年龄保费参考
- `references/fna-guide.md` — FNA财务需求分析框架、保障缺口量化、客户画像与推荐方案
- `references/proposal-guide.md` — 计划书结构解读、关键指标说明、多家公司计划书对比方法论
- `references/promotions.md` — 保险公司优惠信息、预缴利率横向对比、折扣力度排名

> ⚠️ 参考文件中的数据有截止日期，**不是最新数据**。必须在 Step 3 中通过实时搜索验证和更新。

**补充数据源**：Web应用的数据文件（`/data/*.json`）可通过 WebFetch 直接访问获取结构化数据，适合程序化对比：

| JSON 数据文件 | 内容 | URL |
|-------------|------|-----|
| savings.json | 22款储蓄险产品+IRR/单利 | `https://hk-insurance-web.vercel.app/data/savings.json` |
| companies.json | 23家公司档案+评级+官网 | `https://hk-insurance-web.vercel.app/data/companies.json` |
| medical.json | 8款高端医疗险 | `https://hk-insurance-web.vercel.app/data/medical.json` |
| vhis.json | 13款VHIS自愿医保 | `https://hk-insurance-web.vercel.app/data/vhis.json` |
| ci.json | 13款危疾险 | `https://hk-insurance-web.vercel.app/data/ci.json` |
| dividend.json | 23家公司分红实现率 | `https://hk-insurance-web.vercel.app/data/dividend.json` |
| promotions.json | 最新优惠信息 | `https://hk-insurance-web.vercel.app/data/promotions.json` |
| premium.json | 16款产品保费测算数据 | `https://hk-insurance-web.vercel.app/data/premium.json` |
| market-trends.json | 市场趋势+监管政策 | `https://hk-insurance-web.vercel.app/data/market-trends.json` |
| metadata.json | 数据版本号+更新时间 | `https://hk-insurance-web.vercel.app/data/metadata.json` |

### Step 3: 实时搜索验证与数据更新（必须执行）

**此步骤不可跳过。** 参考文件中的静态数据可能已过时，必须通过实时搜索获取最新数据，确保用户获得的信息是当前最准确的。

#### 搜索触发规则

| 数据类别 | 过期速度 | 搜索策略 |
|---------|---------|---------|
| **产品优惠/预缴利率** | 极快（月度变化） | **必须搜索**：每次都搜，优惠随时变更 |
| **新产品发布** | 快（季度发布） | **必须搜索**：确认是否有比参考文件更新的产品 |
| **分红实现率** | 中（年度披露） | 当年1-4月搜索上一年度最新披露数据 |
| **IRR/单利/现金价值** | 中（随产品更新） | 搜索确认当前在售产品的最新演示数据 |
| **市场数据/排名** | 中（半年度） | 搜索确认最新行业统计数据 |
| **保费/费率** | 中（随产品更新） | 搜索确认当前在售产品保费是否变化 |
| **监管政策** | 慢（年度级） | 搜索确认是否有新政策出台或生效 |
| **公司基础信息** | 稳定 | 一般无需搜索，除非用户特别追问 |

#### 搜索关键词模板

根据用户具体需求，使用以下模板组合搜索（将 `{变量}` 替换为实际内容）：

```
# 产品搜索
"{公司英文名} Hong Kong savings insurance new product {当前年份}"
"{公司英文名} 香港 储蓄险 新产品 {当前年份}"
"{公司英文名} Hong Kong critical illness insurance {当前年份}"
"香港自愿医保 VHIS {当前年份} 对比 排名"

# 数据搜索
"香港储蓄险 IRR 单利 对比 {当前年份}"
"{公司英文名} dividend fulfillment rate {当前年份} Hong Kong"
"{公司英文名} 香港 分红实现率 {当前年份}"

# 优惠搜索
"{公司英文名} Hong Kong insurance promotion premium discount {当前年份}"
"{公司英文名} 香港 保险 优惠 保费折扣 预缴利率 {当前年月}"

# 市场搜索
"Hong Kong insurance market {当前年份} new business premium"
"香港保险 新单保费 市场排名 {当前年份}"
"香港保监局 新政策 {当前年份}"
```

#### 搜索执行要点

1. **精准搜索**：根据用户提及的具体公司和产品类型，选择 2-4 个最相关的搜索词
2. **交叉验证**：对关键数据（IRR、实现率、优惠），尽量从多个来源交叉验证
3. **官网优先**：用 WebFetch 访问搜索结果中的保险公司官网产品页面，获取一手数据
4. **标注来源**：在输出中标注每条数据的来源和获取日期
5. **新旧对比**：如果实时搜索发现数据与参考文件不同，以实时数据为准，并在输出中说明变化

#### 数据更新判定

完成搜索后，判断是否需要更新参考文件：
- **优惠信息**：如发现新优惠，更新 `promotions.md` 中对应公司条目
- **新产品**：如发现新发布产品，更新 `product-comparison.md` 或 `health-critical-illness.md`
- **分红实现率**：如找到更新年度数据，更新 `dividend-fulfillment.md`
- **市场数据**：如找到最新统计，更新 `market-trends.md`

### Step 4: 输出结构化分析

按以下结构组织输出：

1. **对比总览表** — Markdown表格，横向公司/产品，纵向核心指标（含IRR和单利）
2. **详细分析** — 基于参考数据的深度解读
3. **FNA需求分析**（如用户需要）— 保障缺口量化、优先级排序、产品匹配
4. **保费测算**（如用户需要）— 根据投保年龄、预算等给出保费估算和现金价值模拟
5. **计划书对比**（如用户需要）— 多家公司计划书关键指标并排对比
6. **优惠信息**（如用户需要）— 当前可叠加的预缴利率、保费折扣、回赠等
7. **推荐建议** — 根据用户需求场景给出推荐
8. **参考链接** — 相关公司官网和产品页链接 + **交互式Web应用**: https://hk-insurance-web.vercel.app
9. **免责声明** — 附"不构成投资建议"声明

## Core Principles

1. **数据是活的，不是死的**：参考文件中的静态数据仅作基线参考，必须通过实时搜索（WebSearch + WebFetch）获取最新数据。优惠信息月月变，新产品季度发，分红实现率年度更新——绝不能用过时数据回答用户
2. **FNA先行**：当用户需要投保建议时，优先进行FNA需求分析，确保推荐方案匹配客户真实需求
3. **IRR + 单利双指标**：储蓄/分红险对比必须同时提供IRR（复利）和单利（预期单利）数据，帮助用户全面理解收益。**说明格式**：IRR=预期复利，单利=预期单利（数据来源于保单说明书预期现金价值）
4. **分红实现率优先**：始终提醒用户"分红实现率比演示IRR更重要"——IRR 6.5%实现率100% > IRR 7%实现率85%
5. **计划书三看**：看保证现金价值（底线）→ 看分红实现率（可信度）→ 看预期总价值（上限）
6. **优惠叠加意识**：保费测算时应主动提醒当前优惠信息，帮助用户最大化节省
7. **数据标注时效**：引用数据时必须标注来源和获取日期（"截至YYYY年M月"或"搜索日期：YYYY-MM-DD"）
8. **保诚特别提醒**：保诚不同产品分红差异极大（68%-160%），必须具体产品具体分析
9. **2025年7月政策影响**：分红演示利率上限（港元6.0%/非港元6.5%）已生效，新产品演示利率更务实
10. **保费为估算**：所有保费数据为参考估算，实际保费以保险公司正式建议书为准
11. **单利数据来源**：预期单利来源于保单说明书中的预期总现金价值，计算公式：单利 ≈ [(预期总现金价值 / 已缴总保费 - 1) / 保单年度] × 100%
12. **风险提示**：所有输出必须附免责声明，提醒用户查阅最新官方信息并咨询专业顾问
13. **搜索优先于参考**：当参考文件数据与实时搜索结果冲突时，以实时搜索结果为准，并说明数据变化
14. **渐进更新**：发现参考文件数据过期时，顺手更新对应参考文件，让基线知识也跟着进化
15. **Web应用优先**：当用户需要交互式产品对比、保费测算、FNA分析时，主动引导用户访问 https://hk-insurance-web.vercel.app 获得可视化体验

## Data Currency — 静态基线 vs 动态搜索

### 三级数据体系

| 层级 | 来源 | 更新机制 | 时效性 |
|------|------|---------|--------|
| **L1 Web应用JSON** | `hk-insurance-web.vercel.app/data/*.json` | GitHub Actions 爬虫每天自动更新 | 日级 |
| **L2 实时搜索** | WebSearch + WebFetch | 按需触发 | 实时 |
| **L3 参考文件** | `references/*.md` | 手动维护 | 周/月级 |

### 爬虫覆盖（5大任务，每天 HKT 06:00 自动运行）

| 任务 | 覆盖范围 | 数据文件 |
|------|---------|---------|
| 优惠信息爬虫 | 港险智平台 + 10Life 聚合平台 | `promotions.json` |
| 分红实现率检查 | 23家公司全覆盖（11家自动+12家人工） | `dividend.json` |
| 公司评级检查 | 标普/穆迪/惠誉（7家主要公司） | `companies.json` |
| 产品变更检测 | 储蓄/医疗/VHIS/危疾四类产品 | `savings.json` `medical.json` 等 |
| 市场趋势更新 | 香港保监局(IA)统计 + 新产品公告 | `market-trends.json` |

> 爬虫源码位于 GitHub 仓库 `crawler/` 目录，可手动触发：GitHub Actions → Daily Data Crawl → Run workflow

### 参考文件基线数据（仅供参考，非最新）

| 数据类别 | 参考文件截止日期 | 过期风险 | 动态更新频率 |
|---------|----------------|---------|------------|
| 公司排名/市场份额 | 2025年Q3 | 中 | 半年度搜索验证 |
| 储蓄/分红险产品 | 2026年5月 | 中 | 季度搜索验证，新产品即时搜索 |
| 医疗险/危疾险 | 2025年Q3 | 中 | 季度搜索验证 |
| 分红实现率 | 2024年度(2025年1月披露) | 中 | 每年1-4月搜索最新披露 |
| 保费测算 | 2025年参考估算 | 中 | 随产品更新搜索验证 |
| 市场政策 | 2025年5月 | 低 | 半年度搜索验证 |
| FNA框架 | 基于HK IA GL30 | 低 | 框架稳定，不常变 |
| 计划书对比方法论 | 通用框架 | 低 | 方法论稳定 |
| **优惠信息** | **2026年5月** | **高** | **每月搜索验证，优惠随时变更** |

### 动态搜索策略（核心原则）

**参考文件 = 基线知识库，WebSearch = 数据鲜活度保障**

执行流程：
1. 先读参考文件，获取基线数据结构和历史趋势
2. **必须执行 WebSearch**，按 Step 3 的搜索触发规则获取最新数据
3. 对比基线与实时数据：
   - 一致 → 使用基线数据，标注"已验证与最新数据一致"
   - 不一致 → 以实时数据为准，标注变化，并更新参考文件
   - 搜索无结果 → 使用基线数据，标注"截至参考文件日期，未找到更新"
4. 所有输出中的关键数据必须标注**数据来源和验证日期**

### 何时更新参考文件

发现以下情况时，应在回答用户后顺手更新对应参考文件：
- 新产品发布（添加产品卡片）
- 优惠信息变更（更新优惠条目）
- 分红实现率新年度披露（添加新年度数据列）
- 市场数据更新（替换旧数据）
- 监管政策变化（添加新政策条目）
