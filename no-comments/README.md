# no-comments

`no-comments` sweeps comments out of a diff or a set of files. A fresh subagent deletes every comment that the code could say for itself and flags the code each comment was apologizing for. The lead agent then audits the sweep, fixes the flagged code at its root cause, and offers to turn real constraints into types, runtime checks, tests, or lint rules instead of prose.

The skill sets `disable-model-invocation: true`, so it runs only when you invoke it (`$no-comments` or `/no-comments`).

## Credits

Adapted from the [`no-comments`](https://github.com/cursor/plugins/tree/ab1f702ce8e8b6557edb56b09f52cde8bfb83f17/pstack/skills/no-comments) skill and the [`comment-sicko`](https://github.com/cursor/plugins/blob/ab1f702ce8e8b6557edb56b09f52cde8bfb83f17/pstack/agents/comment-sicko.md) agent in Lauren Tan's pstack plugin, [cursor/plugins](https://github.com/cursor/plugins) at commit `ab1f702ce8e8b6557edb56b09f52cde8bfb83f17`. Copyright (c) 2026 Lauren Tan, MIT License; the full notice is in [LICENSE](LICENSE).

Changes from upstream: the `comment-sicko` agent's rules are inlined as the sweep brief, so the skill works without the pstack agent, and steps that called other pstack skills (`/how`, `/why`, `/architect`, poteto-mode) are written out as plain instructions.
