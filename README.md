# scope-in-tokens

An agent skill that scopes work in **tokens needed** instead of engineering hours, and picks the cheapest model that does each part well.

When agents can run in parallel, hours stop being the limit. Tokens set both speed and cost. This skill splits work into parallel lanes, gives each lane a worker (a script, a small model, a coding agent, a mid model or a top model), estimates tokens per lane, and names the real critical path. The critical path is often people, outside reviews or shared hardware, not tokens.

A real example: an iOS app release with an AI video host, five build lanes plus review, scoped at about 26.5M coding-agent tokens and 8M chat-model tokens, about 2% of a weekly coding-agent limit. Tokens weren't the bottleneck. Keys, human picks and app store review were.

## Use it

**Claude Code:** copy `skills/scope` into `~/.claude/skills/` (or your project's `.claude/skills/`), then ask "scope this".

**Any chat model:** paste the body of `skills/scope/SKILL.md` at the top of your prompt, then describe the work.

## License

MIT

## Related

[tokencast](https://github.com/krulewis/tokencast) also estimates token cost for planned agent work and learns from logged usage.
