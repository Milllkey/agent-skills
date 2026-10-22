# Agent Skills

English | [中文](README.zh.md)

Agent skills for content processing, web research, speech transcription, Jianying editing and local data workflows.

## Install

List available skills:

```bash
npx skills add Milllkey/agent-skills --list
```

Install the Jianying skill:

```bash
npx skills add Milllkey/agent-skills --skill agent-jianying-edit
```

The Jianying skill requires a separate [jianying-headless](https://github.com/Milllkey/jianying-headless)
checkout, a matching Jianying installation and `JIANYING_HEADLESS_ROOT`.
Each directory's `SKILL.md` and `README.md` describe its dependencies and configuration.

## Skills

| Skill directory | Purpose |
| --- | --- |
| [agent-jianying-edit](agent-jianying-edit/SKILL.md) | Jianying draft creation, editing and export |
| [agent-web-research](agent-web-research/SKILL.md) | Multi-stage research and evidence synthesis |
| [agent-unified-search](agent-unified-search/SKILL.md) | Public web and platform search |
| [agent-content-archive](agent-content-archive/SKILL.md) | Archive content from selected URLs |
| [agent-bookmarks-export](agent-bookmarks-export/SKILL.md) | Export private bookmark links |
| [agent-asr](agent-asr/SKILL.md) | Speech transcription and subtitle routing |
| [agent-volc-asr](agent-volc-asr/SKILL.md) | Volcengine transcription and rough cuts |
| [agent-x-article-draft-uploader](agent-x-article-draft-uploader/SKILL.md) | Upload Markdown to X Articles drafts |
| [agent-x-slicer](agent-x-slicer/SKILL.md) | Turn X posts into image slices and video |
| [agent-codex-chatgpt](agent-codex-chatgpt/SKILL.md) | Coordinate Codex and ChatGPT research |
| [agent-chatgpt-web-research](agent-chatgpt-web-research/SKILL.md) | Research through ChatGPT on the web |
| [agent-memory](agent-memory/SKILL.md) | Set up and maintain a shared memory vault |
| [agent-mac-wechat-dual-open](agent-mac-wechat-dual-open/SKILL.md) | Run two WeChat instances on macOS |
| [agent-wechat-local-vault](agent-wechat-local-vault/SKILL.md) | Organize local WeChat data |
| [agent-wechat-mp-batch-exporter](agent-wechat-mp-batch-exporter/SKILL.md) | Export WeChat Official Account articles |
| [agent-wechat-windows-reader](agent-wechat-windows-reader/SKILL.md) | Read supplied Windows WeChat plaintext snapshots |
| [agent-wecom-local-vault](agent-wecom-local-vault/SKILL.md) | Organize local WeCom snapshots |
| [agent-wecom-operations](agent-wecom-operations/SKILL.md) | Work with the official WeCom CLI |

## Grok plugin

```bash
codex plugin marketplace add Milllkey/agent-skills --ref main
codex plugin add agent-grok-consult@agent-skills
```

See [Grok Consult](plugins/agent-grok-consult/README.md) for configuration.

## Configuration and development

- Keep API keys, cookies, account configuration and local data outside this repository.
- Install the Python, Node.js, FFmpeg or external CLI dependencies required by the selected skill.
- Set `AGENT_MEMORY_VAULT_REPOSITORY` to the chosen template source before installing the memory system.
- Third-party notices and licenses are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and `licenses/`.
- See [version maintenance](docs/skill-maintenance.md) for source and installed-version comparisons.

Run the offline research-family checks:

```bash
python3 agent-web-research/scripts/validate_family.py
```
