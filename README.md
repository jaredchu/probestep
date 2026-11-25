# ProbeStep

ProbeStep helps an agent find the smallest check that could change what you do next. Use it before investing in an uncertain approach or when work stalls and the next move is unclear.

For example, before building a CMS integration, check whether its API supports the one draft operation the project depends on. When an acceptance test fails despite passing unit tests, compare their conditions and find where the behavior first differs.

## Try it in Codex

From the repository root, link the skill into your user skills directory:

```sh
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD/skills/probestep" "$HOME/.agents/skills/probestep"
```

Invoke `$probestep` when a material uncertainty could change the next step. The skill can also be selected automatically for matching tasks. When the requested outcome is already verified, it directs the agent to stop.

See the [skill source](skills/probestep/SKILL.md) for the workflow and [project context](docs/context.md) for its current status.

## Credits and license

Created and maintained by [Jared Chu](https://github.com/jaredchu), with [OpenAI Codex](https://github.com/codex) assisting initial development and validation. See the [commit attribution policy](AGENTS.md#commit-attribution).

Licensed under the [MIT License](LICENSE).
