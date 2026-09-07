# No-Slop 101

Shared agent skills for coding and communication:

- [general](.agents/skills/general/SKILL.md): factual, concise responses, and interaction rules.
- [coding](.agents/skills/coding/SKILL.md): simple implementations, code reuse, style, and Python conventions.

## Installation

Install the skills through your harness. No manual clone or file copying is needed. Review the skill files before installing.

The commands below require an installed harness and Git. CLI syntax was checked with Claude Code 2.1.251, Codex CLI 0.153.4, and Pi 0.85.1. Older releases may not support these commands.

### Claude Code

Run in your terminal:

```sh
claude plugin marketplace add SteveImmanuel/no-slop-101
claude plugin install no-slop-101@steveimm-no-slop
```

The identifier is `plugin-name@marketplace-name`: plugin `no-slop-101` in marketplace `steveimm-no-slop`.

Start a new Claude Code session and invoke each skill separately:

```text
/no-slop-101:general
/no-slop-101:coding
```

To update:

```sh
claude plugin marketplace update steveimm-no-slop
claude plugin update no-slop-101@steveimm-no-slop
```

Restart Claude Code after updating. For a project-scoped installation, add `--scope project` to the install command and run it from that project.

References: [marketplaces](https://code.claude.com/docs/en/plugin-marketplaces), [plugin commands](https://code.claude.com/docs/en/plugins-reference).

### Codex

Run in your terminal:

```sh
codex plugin marketplace add SteveImmanuel/no-slop-101
codex plugin add no-slop-101@steveimm-no-slop
```

Start a new Codex session. Use `/plugins` to inspect the installed plugin and `/skills` to select its `general` and `coding` skills.

To update, refresh the marketplace, then install the current plugin version:

```sh
codex plugin marketplace upgrade steveimm-no-slop
codex plugin add no-slop-101@steveimm-no-slop
```

Start a new session after updating. This uses Codex's plugin manager, not `$skill-installer`.

References: [Codex plugins](https://developers.openai.com/codex/plugins), [plugin packaging](https://developers.openai.com/plugins/build/plugins). Shell command details are available in `codex plugin add --help` and `codex plugin marketplace --help`.

### Pi

Run in your terminal:

```sh
pi install git:github.com/SteveImmanuel/no-slop-101
```

Start a new Pi session and invoke each skill separately:

```text
/skill:general
/skill:coding
```

To update:

```sh
pi update git:github.com/SteveImmanuel/no-slop-101
```

Start a new session after updating. For a project-scoped installation, add `-l` to the install command and run it from that project.

References: [Pi packages](https://github.com/badlogic/pi-mono/blob/main/packages/coding-agent/docs/packages.md), [Pi skills](https://github.com/badlogic/pi-mono/blob/main/packages/coding-agent/docs/skills.md).

### Migrating from manual installation

If you previously copied this repository's `general` and `coding` directories into `~/.claude/skills/`, `~/.agents/skills/`, `~/.codex/skills/`, `~/.pi/agent/skills/`, or project skill directories, back up any edits and remove those copies before installing the package. Remove only copies from this repository, not unrelated skills with the same names.

## Activation

Installation makes skills discoverable, not permanently active. Explicitly load the skills at the start of a session using the commands or selectors above. The `general` skill's instruction to remain active does not itself force a harness to load it.

References: [Claude Code skills](https://code.claude.com/docs/en/skills), [Codex skills](https://developers.openai.com/codex/skills), [Pi skills](https://github.com/badlogic/pi-mono/blob/main/packages/coding-agent/docs/skills.md).

## Package maintenance

All three harnesses load the same files under [`.agents/skills/`](.agents/skills/). Packaging is defined in:

- Claude Code: [plugin manifest](.claude-plugin/plugin.json) and [marketplace](.claude-plugin/marketplace.json).
- Codex: [plugin manifest](.codex-plugin/plugin.json) and [marketplace](.agents/plugins/marketplace.json).
- Pi: [`package.json`](package.json).

For each release, bump the version in both plugin manifests and `package.json`, then publish the changes to GitHub. The remote installation commands require these packaging files to be present on GitHub. No npm publication is required for Pi's Git installation.

References: [Claude Code version management](https://code.claude.com/docs/en/plugins-reference#version-management), [Codex plugin metadata](https://developers.openai.com/plugins/build/plugins), [Pi Git packages](https://github.com/badlogic/pi-mono/blob/main/packages/coding-agent/docs/packages.md#git).
