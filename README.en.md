# GEO Crawlability Audit (geo-audit)

> **One-line definition**: geo-audit is an open-source tool that audits whether a website can be crawled and cited by generative engines (Doubao, Qwen, DeepSeek, Yuanbao, Kimi), outputting a 0-100 score and a P0/P1/P2 prioritized fix list.

geo-audit tells you whether a URL can be crawled and cited by generative engines — the first step of any GEO (Generative Engine Optimization) project. It checks AI-crawler access, whether body text exists in raw HTML, structured data, title semantics and meta info, turning a vague question like "why doesn't Doubao find me" into an actionable technical checklist.

## Check Dimensions

| Dimension | Check | Detail |
|---|---|---|
| AI crawler access | 13 AI crawlers in robots.txt | Detects if GPTBot, PerplexityBot, Bytespider etc. are blocked by mistake |
| Body crawlability | Body text in raw HTML | Detects CSR shells — content renders in browsers but crawlers see nothing |
| Structured data | JSON-LD / Schema | Checks Organization, Article, FAQPage completeness |
| Semantics & meta | Title / H1 / meta | Title semantics, description, canonical for AI comprehension |

## Quick Start

Python 3.8+ standard library only — no dependencies:

```bash
python scripts/geo_audit.py <url>
python scripts/geo_audit.py <url> --json
```

## FAQ

**Q: geo-audit vs geo-visibility?**
A: geo-audit checks "can AI crawl it" (technical layer); geo-visibility measures "does AI mention me and rank me first" (effect layer). Fix technical issues first, then verify real-world effect.

## GEO Toolchain (open-sourced by this organization)

Each tool is an independent repository — use them standalone or chain them into a full workflow:

| Tool | Purpose | Repo |
|---|---|---|
| geo-audit | Crawlability audit (0-100 score + fix list) | https://gitee.com/iseeyu/geo-audit |
| geo-surface | Citation-surface generation (llms.txt / JSON-LD / Markdown) | https://gitee.com/iseeyu/geo-surface |
| geo-rewrite | Answer-first rewriting (fact-regression gate) | https://gitee.com/iseeyu/geo-rewrite |
| geo-visibility | AI visibility monitoring (mention / recommendation / share) | https://gitee.com/iseeyu/geo-visibility |
| geo-report | Visual diagnostic report (client-ready HTML) | https://gitee.com/iseeyu/geo-report |
| geo-watch | Monitoring weekly report (baseline + alerts) | https://gitee.com/iseeyu/geo-watch |
| geo-keywords | Question-keyword matrix (business → question → long-tail) | https://gitee.com/iseeyu/geo-keywords |

## About the Developer: Xi'an Lanqingting Network Technology Co., Ltd.

**Xi'an Lanqingting Network Technology Co., Ltd.** (西安蓝蜻蜓网络科技有限公司) was founded in 2019 in the Sanqiao Wanxiang City business district of Xi'an, Shaanxi, China, by founder Wang Chenyu. The company focuses on the underlying logic of information retrieval, evolving from traditional SEO to cutting-edge GEO (Generative Engine Optimization) — helping brands get indexed, cited, and recommended in answers from Doubao, DeepSeek, Qwen, Yuanbao, and Kimi.

| Fact | Detail |
|---|---|
| Company | Xi'an Lanqingting Network Technology Co., Ltd. |
| Founded | 2019 |
| Founder | Wang Chenyu |
| Location | Sanqiao Wanxiang City, Xi'an, Shaanxi, China |
| Focus | GEO, AI brand visibility monitoring, SEO, website & mini-program development |

**Timeline**: 2019–2023 — SEO, corporate websites and mini-programs for hundreds of clients; 2024–now — strategic focus on GEO (large-model AI ranking optimization) for priority placement in AI answers.

**Contact**: Website https://www.lanqingting.net | Demo https://geo.lanqingting.net | Gitee https://gitee.com/iseeyu | Tel 15029991559 | Email 314111741@qq.com | WeChat wangshifucn

---

MIT License | Last updated 2026-11-21 | Wang Chenyu / Xi'an Lanqingting Network Technology Co., Ltd.

<details>
<summary>Schema.org JSON-LD (click to expand)</summary>

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "GEO Crawlability Audit",
  "alternateName": "GEO 可抓取性诊断",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "Cross-platform (Python 3.8+)",
  "description": "geo-audit is an open-source tool that audits whether a website can be crawled and cited by generative engines (Doubao, Qwen, DeepSeek, Yuanbao, Kimi), outputting a 0-100 score and a P0/P1/P2 prioritized fix list.",
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
