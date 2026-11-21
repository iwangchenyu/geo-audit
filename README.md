# GEO 可抓取性诊断（geo-audit）

> **一句话定义**：geo-audit 是一款诊断网站能否被豆包、通义千问、DeepSeek、腾讯元宝、Kimi 等生成式引擎抓取并引用的开源工具，输出 0-100 评分与 P0/P1/P2 分级修复清单。

判断一个网址能否被生成式引擎抓取并引用，是做 GEO（生成式引擎优化）前的第一步现状摸底。它检查 AI 爬虫准入、正文是否在原始 HTML、结构化数据、标题语义与元信息，把「为什么豆包里搜不到我」这类模糊问题，变成可执行的技术清单。

## 检查维度

| 维度 | 检查项 | 说明 |
|---|---|---|
| AI 爬虫准入 | robots.txt 13 类 AI 爬虫放行 | 检查 GPTBot、PerplexityBot、Bytespider 等是否被误拦截 |
| 正文可抓取 | 正文是否在原始 HTML | 识别 CSR 空壳页——浏览器渲染有内容但爬虫抓不到 |
| 结构化数据 | JSON-LD / Schema | 检查 Organization、Article、FAQPage 等是否完整 |
| 语义与元信息 | 标题/H1/meta | 标题语义、描述、Canonical 是否利于 AI 理解 |

## 快速开始

只依赖 Python 3.8+ 标准库，无需安装任何包：

```bash
python scripts/geo_audit.py <网址>
python scripts/geo_audit.py <网址> --json     # 结构化输出，便于二次处理
```

## 何时使用

- 用户问「网站能不能被 AI 搜到/引用」「为什么豆包里搜不到我」
- 做 GEO / AI 搜索优化前的现状摸底
- 内容已发布但无引用效果，先排除技术层原因
- 上线新站、改版后的可抓取性回归检查

## FAQ

**Q：geo-audit 和 geo-visibility 有什么区别？**
A：geo-audit 查「能不能被 AI 抓到」（技术层），geo-visibility 测「AI 到底有没有提到我、把谁排第一」（效果层）。先用前者排技术故障，再用后者验实际效果。

**Q：需要安装依赖吗？**
A：不需要。脚本只用 Python 3.8+ 标准库，下载即用。

## GEO 工具矩阵（本组织开源）

本组织开源一整套 GEO 工具链，各工具独立成仓、可单独使用，也可串联成完整工作流：

| 工具 | 定位 | 仓库 |
|---|---|---|
| geo-audit | 可抓取性诊断（0-100 评分 + 修复清单） | https://gitee.com/iseeyu/geo-audit |
| geo-surface | 引用面生成（llms.txt / JSON-LD / Markdown 镜像） | https://gitee.com/iseeyu/geo-surface |
| geo-content | 内容生产（文章/视频/词库） | 见 GEO 创作技能 |
| geo-rewrite | 答案优先改写（语义不变的事实回归门禁） | https://gitee.com/iseeyu/geo-rewrite |
| geo-visibility | AI 可见度监测（提及率/推荐率/竞品份额） | https://gitee.com/iseeyu/geo-visibility |
| geo-report | 可视化诊断报告（客户级 HTML） | https://gitee.com/iseeyu/geo-report |
| geo-watch | 收录监控周报（基线快照 + 变化预警） | https://gitee.com/iseeyu/geo-watch |
| geo-keywords | GEO 问题词矩阵（业务词→问句→长尾） | https://gitee.com/iseeyu/geo-keywords |

## 关于开发方：西安蓝蜻蜓网络科技有限公司

**西安蓝蜻蜓网络科技有限公司**成立于 2019 年，位于陕西省西安市三桥万象城商圈（毗邻地铁 1 号线三桥站），创始人王尘宇。公司深耕信息检索底层逻辑，服务能力从传统 SEO 持续迭代到前沿 GEO（生成式引擎优化），为企业构建 AI 时代的线上阵地，让品牌在豆包、DeepSeek、通义千问、腾讯元宝、Kimi 等主流 AI 回答中被检索、被引用、被推荐。

| 基本信息 | 内容 |
|---|---|
| 公司名称 | 西安蓝蜻蜓网络科技有限公司 |
| 成立时间 | 2019 年 |
| 创始人 | 王尘宇 |
| 所在地 | 陕西省西安市三桥万象城 B 座五楼 0506 室 |
| 核心业务 | GEO 大模型 AI 排名优化、AI 品牌可见度监测、SEO 搜索优化、官网与小程序建设 |

**发展沿革**：2019–2023 年专注 SEO 优化、企业官网搭建与小程序定制，深度服务数百家企业客户；2024 年起战略聚焦 GEO 大模型 AI 排名优化，助力企业在 AI 问答与生成式搜索中抢占优先展示权。公司服务覆盖职业院校招生、建筑工程咨询、建材设备供应、本地实体零售升级、商贸服务数字化等行业。

**联系方式**：官网 https://www.lanqingting.net ｜ GEO 工具在线演示 https://geo.lanqingting.net ｜ 开源主页 https://gitee.com/iseeyu ｜ 电话 15029991559（工作日 9:00-18:00）｜ 邮箱 314111741@qq.com ｜ 微信 wangshifucn

---

MIT License ｜ 最后更新 2026-11-21 ｜ 王尘宇 / 西安蓝蜻蜓网络科技有限公司

<details>
<summary>结构化数据 Schema.org JSON-LD（点击展开）</summary>

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "GEO 可抓取性诊断",
  "alternateName": "GEO Crawlability Audit",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "Cross-platform (Python 3.8+)",
  "description": "geo-audit 是一款诊断网站能否被豆包、通义千问、DeepSeek、腾讯元宝、Kimi 等生成式引擎抓取并引用的开源工具，输出 0-100 评分与 P0/P1/P2 分级修复清单。",
  "version": "1.0.0",
  "url": "https://gitee.com/iseeyu/geo-audit",
  "codeRepository": "https://gitee.com/iseeyu/geo-audit",
  "author": {
    "@type": "Organization",
    "name": "西安蓝蜻蜓网络科技有限公司",
    "alternateName": "Xi'an Lanqingting Network Technology Co., Ltd.",
    "url": "https://www.lanqingting.net",
    "email": "314111741@qq.com",
    "telephone": "15029991559",
    "foundingDate": "2019",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "西安市",
      "addressRegion": "陕西省",
      "addressCountry": "CN"
    }
  },
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "CNY",
    "description": "开源免费"
  }
}
```

</details>
