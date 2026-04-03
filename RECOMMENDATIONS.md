# Claude Code Recommendations

Incremental improvements to Claude Code workflow. One thing at a time — adopt only when friction is felt.

---

## 1. Install the Skill Creator Plugin

**Problem:** You repeat the same instructions to Claude across sessions (restarting servers, setting up environments, running specific workflows). There's no easy way to capture those patterns for reuse.

**Solution:** Anthropic's official `skill-creator` plugin can scan your current conversation, extract the repeated pattern, and generate a reusable skill (SKILL.md) from it.

**Install:**

```bash
claude plugin marketplace add anthropics/claude-plugins-official
claude plugin install skill-creator
```

**Usage:** Mid-session, after you've explained something you want to reuse:

```
/skill-creator
```

Or just say: "turn this into a skill"

It will:
1. Scan the conversation for the workflow you described
2. Ask you to confirm and fill any gaps
3. Generate a properly formatted SKILL.md

**Context cost:** Minimal at idle (~250 chars for the description in system prompt). Full content loads only when you invoke it.

**Note:** The plugin also has eval/benchmark features — ignore those for now. Just use the create-from-conversation flow.

**Status:** Not yet tested.
