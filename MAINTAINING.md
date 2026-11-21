# Maintaining this skill

This workflow applies only to the owner maintaining the skill itself. App work never uses it.

Use the canonical source repository at https://github.com/imam-chowdhury/top1-vibe-system.

1. Check local and remote changes first. Reconcile any edits that exist only in an installed copy.
2. Validate skill frontmatter and local links. Check changed external references against their upstream sources. Report unreachable references separately from confirmed broken links.
3. Commit the intended files and push to the owner's main branch. Verify the remote revision.
4. Sync SKILL.md, METHODS.md, DESIGN_RULES.md, QA_CHECKLIST.md and PRD.md to the owner's installed global Codex skill. Compare all five files with the verified checkout. Check any other designated installations separately.
5. Update the owner's designated Notion project guide when usage or behavior changes.
6. Report any destination that could not be verified.

Keep SKILL.md to the core workflow. Material needed for only some tasks goes in a linked guide such as METHODS.md, which an agent reads only when that task comes up.
