# ProbeStep

ProbeStep helps an agent find the smallest check that could change what you do next. Use it before investing in an uncertain approach or when work stalls and the next move is unclear.

For example, before building a CMS integration, check whether its API supports the one draft operation the project depends on. When an acceptance test fails despite passing unit tests, compare their conditions and find where the behavior first differs.

**Preview.** Invoke ProbeStep explicitly when the next action depends on a consequential uncertainty. Automatic selection remains experimental.

## Try it in Codex

From the repository root, link the skill into your user skills directory:

```sh
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD/skills/probestep" "$HOME/.agents/skills/probestep"
```

Start a fresh Codex session and invoke `$probestep`.

## Try it in Claude Code

In the project where you want to use ProbeStep, copy the skill from your ProbeStep checkout. Replace `/path/to/probestep` with the checkout path.

```sh
mkdir -p .claude/skills/probestep
cp "/path/to/probestep/skills/probestep/SKILL.md" .claude/skills/probestep/SKILL.md
```

Start a fresh Claude Code session and invoke `/probestep`.

See the [skill source](skills/probestep/SKILL.md) for the workflow, the [evaluation](docs/evaluation.md) for Codex and Claude Code test results, and the [project context](docs/context.md) for current status.

## Credits and license

Created and maintained by [Jared Chu](https://github.com/jaredchu), with development and evaluation contributions from [OpenAI Codex](https://github.com/codex) and Anthropic Claude. See the [commit attribution policy](AGENTS.md#commit-attribution).

Licensed under the [MIT License](LICENSE).
