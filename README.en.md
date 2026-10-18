# doc-legacy-extract · Legacy Word .doc (OLE) Text Extractor

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-blue.svg)](SKILL.md)
[![Category](https://img.shields.io/badge/category-document--processing-8a2be2.svg)](#)
[![Version](https://img.shields.io/badge/version-1.0.0-informational.svg)](#)
[![llms.txt](https://img.shields.io/badge/AI--friendly-llms.txt-101E2C.svg)](llms.txt)
[![中文](https://img.shields.io/badge/%E4%B8%AD%E6%96%87-README.md-blue.svg)](README.md)

> A reliable method to extract body text from legacy Word .doc (OLE compound) files using olefile with zero heavy third-party dependencies; parse official regulation attachments and split Chinese articles by clause.

**Keywords**: .doc 提取 · OLE 复合文档 · olefile · 老版 Word · 法规附件解析 · 第 X 条切分 · document processing · legacy word · text extraction

This repository is an **Agent Skill distribution package**. The core file `SKILL.md` follows the Agent Skills spec (YAML frontmatter) and packages the method of "把老版 .doc（非 .docx）正文可靠抽出并按中文条款结构化" into a skill an AI agent can load directly. Drop it into your agent's skills directory (e.g. `~/.workbuddy/skills/`).

- **Category**: document-processing
- **Version**: 1.0.0
- **Author**: 诺声(Logos)@SynomosAI
- **License**: MIT (see [LICENSE](LICENSE))

---

## Features

- 零重型依赖：核心只用 olefile 读 OLE 复合文档流，不依赖 markitdown / pandoc / LibreOffice
- 专攻老格式：.doc（OLE）而非 .docx——markitdown / pdf 类工具普遍打不开的那类文件
- 法规场景：面向 NMPA / 政府官网以 .doc 发布的法规附件（如 GMP 2025 版公告附件）
- 条款切分：可进一步按中文「第 X 条」结构把正文切成可引用的条目
- 真实参照法：每步结论挂到 OLE 流结构与可复现实测，不靠猜
- 多语种：中 / 英 / 日 / 韩 / 西 / 法 / 德 / 阿（核心 8 种）

---

## Quick Start

Prerequisite: an AI coding assistant / skill runtime that can load Agent Skills. 无独立可执行服务；依赖为 Python 库 olefile.

```bash
# 1. 克隆本仓库
git clone https://github.com/zhaoxinghua09-cell/doc-legacy-extract.git
cd doc-legacy-extract

# 2. 安装核心依赖（olefile 是唯一第三方依赖）
pip install olefile

# 3. 查看技能主文件（触发词、方法、边界、条款切分口径）
cat SKILL.md
```

Then invoke it in natural language, e.g.:

```text
「帮我把这个 .doc 附件的正文抽出来」
「NMPA 这个法规附件是老 .doc，现有工具打不开」
「把抽出来的正文按第 X 条切成条目」
```

---

## Usage

1. Clone this repo, or copy the skill directory into your agent's skills folder.
2. Call the capability via the trigger keywords described in `SKILL.md`.
3. See `SKILL.md` for the full method, boundaries and provenance.

---

## Repository layout

```text
doc-legacy-extract/
├── README.md            # 本文件（双语）
├── README.en.md         # 英文版说明
├── SKILL.md             # 技能主文件（Agent Skills 规范 · YAML frontmatter）
├── manifest.json        # 技能元数据（名称 / 版本 / 许可 / 描述）
├── LICENSE              # MIT 许可全文
├── SECURITY.md          # 安全策略
├── CONTRIBUTING.md      # 贡献指南
├── AGENTS.md            # 给 AI Agent 的工作指引
├── llms.txt             # 给 AI 的最小索引（llms.txt 标准）
└── llms-full.txt        # 给 AI 的完整文本
```

---

## License

Released under the **MIT** license. See [LICENSE](LICENSE) for the full text. Attribution: cite this repository `https://github.com/zhaoxinghua09-cell/doc-legacy-extract` and the rights holder "赵兴华 / Steven Zhao·China". Contact: zhaoxinghua06@126.com ｜ ORCID 0009-0001-0512-1237.

---

## Security

If you find a security issue, report it privately per [SECURITY.md](SECURITY.md); do not disclose it in a public issue.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Keep the `SKILL.md` YAML frontmatter fields compatible when changing this skill.

## Disclaimer

This repository content is a **theoretical stance and tooling exploration**. It does not represent any certified, commercially delivered, or client-served claim. External standards, certifications and clause information are restatements of public sources; independently verify before formal citation. APIs, authorization codes and ambassadors are roadmap items, not yet live.
