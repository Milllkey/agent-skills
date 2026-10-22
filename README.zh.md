# Agent Skills

[English](README.md) | 中文

用于内容处理、网页研究、语音转写、剪映编辑和本地资料整理的 Agent 技能集合。

## 安装

查看可安装技能：

```bash
npx skills add Milllkey/agent-skills --list
```

安装剪映技能：

```bash
npx skills add Milllkey/agent-skills --skill agent-jianying-edit
```

剪映技能需要单独检出 [jianying-headless](https://github.com/Milllkey/jianying-headless)，
安装匹配版本的剪映，并配置 `JIANYING_HEADLESS_ROOT`。
其他技能的依赖、配置和操作入口见各目录的 `SKILL.md` 与 `README.md`。

## 技能

| 技能目录 | 用途 |
| --- | --- |
| [agent-jianying-edit](agent-jianying-edit/SKILL.md) | 剪映草稿生成、编辑与导出 |
| [agent-web-research](agent-web-research/SKILL.md) | 跨平台研究与证据整理 |
| [agent-unified-search](agent-unified-search/SKILL.md) | 公开网页和平台搜索 |
| [agent-content-archive](agent-content-archive/SKILL.md) | 已知链接的正文与媒体归档 |
| [agent-bookmarks-export](agent-bookmarks-export/SKILL.md) | 私人收藏链接导出 |
| [agent-asr](agent-asr/SKILL.md) | 语音转写与字幕路由 |
| [agent-volc-asr](agent-volc-asr/SKILL.md) | 火山引擎转写与口播粗剪 |
| [agent-x-article-draft-uploader](agent-x-article-draft-uploader/SKILL.md) | Markdown 上传为 X Articles 草稿 |
| [agent-x-slicer](agent-x-slicer/SKILL.md) | X 帖子切片与视频制作 |
| [agent-codex-chatgpt](agent-codex-chatgpt/SKILL.md) | Codex 与 ChatGPT 研究协作 |
| [agent-chatgpt-web-research](agent-chatgpt-web-research/SKILL.md) | ChatGPT 网页研究 |
| [agent-memory](agent-memory/SKILL.md) | 共享记忆系统安装与维护 |
| [agent-mac-wechat-dual-open](agent-mac-wechat-dual-open/SKILL.md) | Mac 微信双开 |
| [agent-wechat-local-vault](agent-wechat-local-vault/SKILL.md) | 微信本地资料整理 |
| [agent-wechat-mp-batch-exporter](agent-wechat-mp-batch-exporter/SKILL.md) | 公众号文章批量导出 |
| [agent-wechat-windows-reader](agent-wechat-windows-reader/SKILL.md) | Windows 微信明文快照读取 |
| [agent-wecom-local-vault](agent-wecom-local-vault/SKILL.md) | 企业微信本地快照整理 |
| [agent-wecom-operations](agent-wecom-operations/SKILL.md) | 企业微信官方 CLI 操作 |

## Grok 插件

```bash
codex plugin marketplace add Milllkey/agent-skills --ref main
codex plugin add agent-grok-consult@agent-skills
```

插件配置见 [Grok Consult](plugins/agent-grok-consult/README.zh.md)。

## 配置与开发

- API 密钥、Cookie、账号配置和本地数据存放在仓库之外。
- 运行特定技能前，按其文档准备 Python、Node.js、FFmpeg 或外部 CLI。
- 记忆系统安装前，用 `AGENT_MEMORY_VAULT_REPOSITORY` 指定模板源码仓库。
- 第三方来源与许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) 和 `licenses/`。
- 版本核对方式见 [维护文档](docs/skill-maintenance.md)。

研究技能的本地检查：

```bash
python3 agent-web-research/scripts/validate_family.py
```
