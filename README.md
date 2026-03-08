# 30x SEO

21 个 SEO 技能，覆盖技术 SEO、内容优化、关键词研究、外链分析、AI 可见性监控全链路。

## 安装

```bash
# 克隆到 skills 目录
git clone [your-repo-url] ~/.openclaw/skills/30x-seo

# 配置 DataForSEO（关键词/外链/SERP/AI 可见性）
mkdir -p ~/.config/dataforseo
echo "your-base64-credentials" > ~/.config/dataforseo/auth
chmod 600 ~/.config/dataforseo/auth
```

详细配置见 [SETUP-CN.md](SETUP-CN.md)

## 快速开始

```bash
# 全站审计
/seo audit https://example.com

# 单页分析
/seo page https://example.com/about

# Schema 检查
/seo schema https://example.com

# 关键词研究（需 DataForSEO）
/seo keywords research "目标关键词"

# AI 可见性监控（需 DataForSEO）
/seo ai-visibility domain example.com
```

## 命令列表

| 命令 | 说明 |
|------|------|
| `/seo audit <url>` | 全站 SEO 审计 |
| `/seo page <url>` | 单页深度分析 |
| `/seo technical <url>` | 技术 SEO（8 大类）|
| `/seo sitemap <url>` | Sitemap 分析 |
| `/seo sitemap generate` | Sitemap 生成 |
| `/seo schema <url>` | Schema 检测/生成 |
| `/seo images <url>` | 图片 SEO |
| `/seo hreflang <url>` | 多语言 SEO |
| `/seo internal-links <url>` | 内链分析 |
| `/seo content-audit <url>` | 内容质量（E-E-A-T + AI 可引用性）|
| `/seo content-brief <keyword>` | 内容简报生成 |
| `/seo keywords research <seed>` | 关键词研究 |
| `/seo keywords difficulty <kw>` | 关键词难度 |
| `/seo serp check <keyword>` | 实时 SERP |
| `/seo backlinks profile <domain>` | 外链分析 |
| `/seo backlinks gap <domains>` | 外链差距 |
| `/seo ai-visibility domain <d>` | AI 可见性监控 |
| `/seo plan <url>` | SEO 策略规划 |

## Skills 分类

### 技术 SEO（8 个）
- seo-technical — 8 大类审计
- seo-sitemap — Sitemap 分析/生成
- seo-hreflang — 多语言 SEO
- seo-schema — Schema 结构化数据
- seo-images — 图片 SEO
- seo-redirects — 重定向审计
- seo-internal-links — 内链分析/生成
- seo-geo-technical — AI 爬虫优化

### 内容优化（8 个）
- seo-content-audit — E-E-A-T + AI 可引用性
- seo-content-brief — 内容简报
- seo-content-writer — 写作指南
- seo-content-decay — 内容衰退检测
- seo-cannibalization — 关键词蚕食
- seo-page — 单页分析
- seo-competitor-pages — 竞品分析
- seo-programmatic — 程序化 SEO

### 关键词 & SERP（3 个，需 DataForSEO）
- seo-keywords — 关键词研究
- seo-serp — SERP 追踪
- seo-backlinks — 外链分析

### AI 可见性（2 个，需 DataForSEO）
- seo-ai-visibility — LLM 提及监控
- seo-plan — SEO 策略规划

## 依赖

| 类别 | 数量 | 依赖 |
|------|------|------|
| 技术 SEO + 内容优化 | 16 | WebFetch（内置）|
| 关键词/SERP/外链/AI | 5 | DataForSEO |

**无需 DataForSEO 即可使用 16 个 skills。**

## 配置文件

```
~/.config/dataforseo/auth       # DataForSEO Base64 凭据
~/.config/claude/mcp.json       # MCP 配置（可选）
```

## 文档

- [SETUP-CN.md](SETUP-CN.md) — 中文配置指南（详细）

## License

MIT
