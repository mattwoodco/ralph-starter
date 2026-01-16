# Project Plan

## Overview
Brief description of what you're building.

**Reference:** `PRD.md`

---

## Task List

```json
[
  {
    "category": "setup",
    "description": "Verify ralph-starter structure is complete",
    "steps": [
      "Confirm all required files exist (PROMPT.md, plan.md, activity.md, ralph.sh)",
      "Verify .claude/settings.json has correct sandbox config",
      "Check .mcp.json has Playwright configuration",
      "Ensure ralph.sh is executable"
    ],
    "passes": true
  },
  {
    "category": "feature",
    "description": "Validate PRD template is comprehensive",
    "steps": [
      "Review PRD.md has all required sections",
      "Confirm user stories section exists",
      "Verify technical requirements section is present",
      "Check instructions for Ralph are included"
    ],
    "passes": false
  },
  {
    "category": "testing",
    "description": "Test that all JSON files parse correctly",
    "steps": [
      "Validate .claude/settings.json is valid JSON",
      "Validate .mcp.json is valid JSON",
      "Confirm plan.md task list is valid JSON",
      "Verify no syntax errors in configuration files"
    ],
    "passes": false
  }
]
```

---

## Agent Instructions

1. Read `activity.md` first to understand current state
2. Find next task with `"passes": false`
3. Complete all steps for that task
4. Verify in browser (if applicable)
5. Update task to `"passes": true`
6. Log completion in `activity.md`
7. Repeat until all tasks pass

**Important:** Only modify the `passes` field. Do not remove or rewrite tasks.

---

## Completion Criteria
All tasks marked with `"passes": true`
