# Ralph Starter

A starter template for running autonomous Claude Code agents using the Ralph Wiggum loop pattern.

## What is Ralph?

Ralph Wiggum enables long-running autonomous tasks by forcing agents to iterate until completion. It solves the problem of agents finishing prematurely by using a bash loop that starts a fresh context window for each iteration.

## Quick Start

1. **Define your PRD** - Edit `PRD.md` with your project requirements
2. **Create tasks** - Update `plan.md` with specific tasks derived from your PRD
3. **Run Ralph** - Execute the loop:
   ```bash
   chmod +x ralph.sh
   ./ralph.sh 20  # Run up to 20 iterations
   ```

## File Structure

```
ralph-starter/
├── .claude/
│   └── settings.json    # Sandbox and permissions config
├── .mcp.json            # Playwright MCP configuration
├── .env.local           # Environment variables (AI_GATEWAY_API_KEY)
├── .gitignore           # Git ignore patterns
├── PRD.md               # Product Requirements Document template
├── PROMPT.md            # Agent instructions for each iteration
├── plan.md              # Task list with pass/fail tracking
├── activity.md          # Progress log maintained by agent
├── ralph.sh             # Bash script for looping iterations
├── screenshots/         # Visual verification screenshots
└── README.md            # This file
```

## How It Works

1. **PROMPT.md** contains instructions that tell Claude what to do each iteration
2. **plan.md** holds tasks in JSON format with `"passes": false/true`
3. **activity.md** logs progress across iterations
4. **ralph.sh** loops through iterations until all tasks pass

### Each Iteration:
1. Agent reads `activity.md` for current state
2. Finds next task with `"passes": false`
3. Implements that single task
4. Verifies via Playwright screenshot
5. Updates `activity.md` with progress
6. Marks task as `"passes": true`
7. Commits changes
8. Repeats until all tasks pass or max iterations reached

## Task Format

Tasks in `plan.md` follow this JSON structure:

```json
{
  "category": "setup|feature|testing",
  "description": "Brief task description",
  "steps": [
    "Step 1",
    "Step 2"
  ],
  "passes": false
}
```

## Configuration

### .claude/settings.json
Controls sandbox permissions and allowed operations.

### .mcp.json
Configures Playwright for headless browser screenshots.

### .env.local
Contains sensitive environment variables like `AI_GATEWAY_API_KEY`.

## Tips

- **One task at a time** - Each iteration works on exactly ONE task
- **Don't modify task descriptions** - Only change `passes` field
- **Set max iterations** - Control costs with the iteration limit
- **Fresh context** - Each iteration starts with clean state

## Based On

[Ralph Wiggum Guide](https://github.com/JeredBlu/guides/blob/main/Ralph_Wiggum_Guide.md)
