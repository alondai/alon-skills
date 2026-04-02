# Alon Skills

[English](./README.md)

这是 Alon 面向 Claude、Codex、Gemini 和 OpenClaw 发布的公开 agent skills 仓库。

## 安装

使用 `skills` 安装某个 skill：

```bash
npx skills add alondai/alon-skills --skill <skill-name>
```

示例：

```bash
npx skills add alondai/alon-skills --skill alon-github-security-audit
```

## 当前 Skills

### `alon-github-security-audit`

对 GitHub 仓库或本地代码库做安全审计，重点检查恶意代码、后门、可疑联网行为、凭证窃取模式、混淆和供应链风险。

路径：

`skills/alon-github-security-audit`

### `alon-search-skill-plus`

跨可信技能目录、ClawHub 和 GitHub 适配候选仓库搜索 Claude Code skill，并带有明确的来源分级、排序和安全过滤。

路径：

`skills/alon-search-skill-plus`

## 兼容性

这个仓库面向支持开放 `SKILL.md` 格式的 agent host，包括：

- Claude
- Codex
- Gemini
- OpenClaw

## 维护者

由 Alon 维护。
