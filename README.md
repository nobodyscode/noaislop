Claude Code (terminal)

Run these three lines:

mkdir -p ~/.claude/skills/no-ai-slop
curl -sL https://raw.githubusercontent.com/nobodyscode/noaislop/main/SKILL.md -o ~/.claude/skills/no-ai-slop/SKILL.md

That's it. It auto-triggers on any write/edit request. For one project only, use .claude/skills/ instead of ~/.claude/skills/.

Claude.ai / Claude Desktop (Cowork)

Download the .skill file from the repo, then in Claude go to Settings → Capabilities → Skills → Upload, and select it. Or if you have the .skill card in chat, click Save skill.

Cursor

Cursor uses rule files. Run:

mkdir -p .cursor/rules
curl -sL https://raw.githubusercontent.com/nobodyscode/noaislop/main/SKILL.md -o .cursor/rules/no-ai-slop.mdc

Then open .cursor/rules/no-ai-slop.mdc and add this at the very top so it always applies:

---
alwaysApply: true
---

ChatGPT / Custom GPT

Open the raw link, copy everything below the --- frontmatter block, and paste it into either your Custom Instructions ("How would you like ChatGPT to respond?") or, for a Custom GPT, the Instructions field in the GPT builder. Add one line before it: "Follow these writing rules whenever you write or edit prose:"

Any other AI agent (Gemini, Perplexity, API, etc.)

Copy the body of the file and paste it into the agent's system prompt or custom-instructions field, prefixed with "Apply these writing rules to everything you write." For API use, put it in the system parameter.

Universal fallback (works in any chat)

Paste this one line into the chat:

Read https://raw.githubusercontent.com/nobodyscode/noaislop/main/SKILL.md and follow it for all writing in this conversation.

This only works if the tool can browse the web. If it can't, paste the file contents directly.
