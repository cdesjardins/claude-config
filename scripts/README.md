# Claude Code Scripts

Custom scripts for Claude Code, configured in `~/.claude/settings.json`.

## context-bar.sh

Statusline hook that displays model, working directory, git status, and rate limit usage.

**Output:**
```
Sonnet 4.6 | 📁sw | 🔀main (0 files uncommitted, synced 5m ago) | █░░░░ session 10% resets 2h30m | █░░░░ weekly 16% resets 3d
```

**Fields:**
- Model name
- Current directory (basename)
- Git branch, uncommitted file count, and upstream sync status
- 5-hour session rate limit bar + reset countdown
- 7-day weekly rate limit bar + reset countdown

Rate limit percentages match what is shown in Settings → Usage.

**Configuration (`~/.claude/settings.json`):**
```json
{
  "statusLine": {
    "type": "command",
    "command": "~/.claude/scripts/context-bar.sh"
  }
}
```
