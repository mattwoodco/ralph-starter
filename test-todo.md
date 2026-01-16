# Test Todo List for Ralph Starter

This file is used to validate the ralph-starter setup.

## Test Phases

### Phase 1: Single Task Test
Run Ralph with 1 task in plan.md to verify basic functionality.

### Phase 2: Three Tasks Validation
Update plan.md with 3 tasks:
1. Setup task
2. Feature task
3. Testing task

### Phase 3: Commit & Repo
After validation, commit the starter and create the `ralph-starter` repository.

---

## Sample Three-Task plan.md

Replace the Task List section in plan.md with:

```json
[
  {
    "category": "setup",
    "description": "Create README with project description",
    "steps": [
      "Create README.md file",
      "Add project title and description",
      "Add usage instructions",
      "Add file structure overview"
    ],
    "passes": false
  },
  {
    "category": "feature",
    "description": "Add .gitignore for common patterns",
    "steps": [
      "Create .gitignore file",
      "Add node_modules pattern",
      "Add .env patterns",
      "Add OS-specific patterns"
    ],
    "passes": false
  },
  {
    "category": "testing",
    "description": "Verify all files are properly structured",
    "steps": [
      "Check all required files exist",
      "Verify JSON files are valid",
      "Confirm ralph.sh is executable",
      "Test that plan.md parses correctly"
    ],
    "passes": false
  }
]
```
