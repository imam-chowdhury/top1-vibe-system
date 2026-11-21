# Top 1% Vibe System

নতুন app বানানো, existing app redesign করা এবং feature বা bug fix করার জন্য একটি Agent Skill। যে app নিয়ে কাজ করবে, তার folder-এ agent খোলো। এক বাক্যে লেখো কার জন্য কী ফল চাও। Agent project দেখে PRD লিখবে, দরকারি design ও engineering পদ্ধতি বেছে নেবে এবং কীভাবে ফল যাচাই করেছে তা জানাবে।

## Install ছাড়াই শুরু

GitHub পড়তে পারে এমন agent-এর chat-এ এই prompt দাও। বন্ধনীর অংশটা নিজের কাজ দিয়ে বদলাও।

```text
https://github.com/imam-chowdhury/top1-vibe-system থেকে SKILL.md ও তার প্রাসঙ্গিক guide পড়ো। আমার বর্তমান project-এ [কার জন্য কী বানাতে বা উন্নত করতে চাই] বাস্তবায়ন করো। শেষে মূল কাজটি কীভাবে পরীক্ষা করেছ দেখাও।
```

Agent-এর web access না থাকলে নিচের চারটি file একসঙ্গে attach করো বা workspace-এ একই folder-এ রাখো। তারপর বলো, “এই folder-এর SKILL.md অনুসরণ করে আমার কাজটি করো।” [SKILL.md](SKILL.md) · [DESIGN_RULES.md](DESIGN_RULES.md) · [QA_CHECKLIST.md](QA_CHECKLIST.md) · [PRD.md](PRD.md)

## Codex, Claude Code, Antigravity ও Cursor-এ global install

Node.js 22.20 বা পরের সংস্করণ এবং npx থাকলে terminal-এ নিজের agent-এর command চালাও। Global install করলে একই user account-এর অন্য project থেকেও skill ব্যবহার করা যায়। শুধু একটি project-এ চাইলে তার root folder থেকে একই command চালিয়ে `-g` বাদ দাও। [Skills CLI](https://github.com/vercel-labs/skills) · [সমর্থিত agent ও install location](https://github.com/vercel-labs/skills/blob/main/src/agents.ts)

| Agent | একবার install | Project chat-এ প্রথম prompt |
| --- | --- | --- |
| Codex | `npx skills add imam-chowdhury/top1-vibe-system -g -a codex` | `$top1-vibe-system রোগীদের জন্য appointment booking app বানাও।` |
| Claude Code | `npx skills add imam-chowdhury/top1-vibe-system -g -a claude-code` | `/top1-vibe-system মোবাইল থেকে booking বদলানোর flow সহজ করো।` |
| Google Antigravity | `npx skills add imam-chowdhury/top1-vibe-system -g -a antigravity` | `top1-vibe-system skill ব্যবহার করে এই app redesign করো।` |
| Cursor | `npx skills add imam-chowdhury/top1-vibe-system -g -a cursor` | `top1-vibe-system skill ব্যবহার করে checkout-এ duplicate submission ঠিক করো।` |

Install শেষে target project-এ নতুন agent session খোলো। Global install যাচাই করতে terminal-এ `npx skills list -g` চালিয়ে `top1-vibe-system` খোঁজো। অন্য coding agent-এর জন্য CLI-র সমর্থিত identifier দিয়ে `-a`-এর মান বদলাও, অথবা উপরের repo prompt ব্যবহার করো। [CLI command reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)

## কোন কাজে কী বলবে

- **নতুন app** — “ছোট ক্লিনিকের রোগীরা যেন ফোন ছাড়াই খালি সময় দেখে booking করতে পারেন। PRD আর implementation তুমি বেছে নাও।”
- **Redesign** — “বর্তমান booking flow ফোনে পরীক্ষা করো। কোথায় রোগী আটকে যান দেখাও, উন্নতি করো, তারপর একই কাজ আবার পরীক্ষা করো।”
- **Feature বা fix** — “Save দুবার চাপলে দুটি booking হচ্ছে। একটি booking থাকবে এবং reload-এর পরেও সেটি দেখা যাবে, এমনভাবে ঠিক করো।”
- **শুধু সিদ্ধান্ত চাইলে** — “ভুয়া booking কমাতে বাধ্যতামূলক signup ভাবছি। সম্ভাব্য অসুবিধা আর একটি বিকল্প বলো। এখন শুধু পরামর্শ চাই।”
