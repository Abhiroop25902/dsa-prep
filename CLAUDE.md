# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview
This is a personal DSA (Data Structures and Algorithms) + System Design interview preparation tracker. The repository contains a single living document:
- `abhiroop_faang_prep_plan.md` - The living plan containing roadmap, progress tracking, checklists, and behavioral stories

There is no build system, tests, linting, or CI - this is a markdown-only repository where the primary activity is updating the plan file.

## Development Workflow

### Core Commands (using RTK for token optimization)
All commands should be prefixed with `rtk` for 60-90% token savings:
- `rtk git status` - Check repository status
- `rtk git diff` - View changes
- `rtk read <file>` - Read file contents
- `rtk grep <pattern>` - Search for patterns
- `rtk ls <path>` - List directory contents

### Primary Workflow
1. Read/update `abhiroop_faang_prep_plan.md` to track progress
2. After edits, changes are automatically committed and pushed via PostToolUse hook
3. No manual git commands needed for plan updates (handled automatically)

### Available Commands via RTK
- File operations: `rtk read`, `rtk ls`, `rtk grep`, `rtk find`
- Git operations: `rtk git status`, `rtk git diff`, `rtk git log`, `rtk git diff`
- The `rtk proxy <cmd>` command runs raw commands without filtering (for debugging)

## Code Architecture & Structure

### Single Source of Truth
The entire repository revolves around one markdown file:
- `abhiroop_faang_prep_plan.md` contains all planning, tracking, and progress information
- Sections include: Progress Tracker, Stats Summary, Topic Checklists, Roadmap, etc.
- Updates are made in-place during each study session

### Automation Features
- **Auto-commit**: PostToolUse hook automatically commits and pushes changes to the plan file
- **RTK Integration**: All shell commands should use `rtk` prefix for token efficiency
- **Section-based Organization**: The plan is organized into clearly defined sections for different aspects of interview prep

### Key Sections in the Plan File
1. **Progress Tracker** - Log of solved problems with timestamps, time taken, confidence ratings
2. **Stats Summary** - Aggregated statistics (problems solved, streaks, strongest/weakest topics)
3. **Topic Checklists** - Tracking progress across DSA and System Design topics
4. **Roadmap** - Structured learning path organized by phases
5. **Daily Structure** - Recommended time allocation for weekday vs weekend study

## Important Guidelines

### Progress Tracking Rules
- Only trust what's logged in the Progress Tracker table
- If user mentions progress not in the log, ask for confirmation before recording
- Append new Progress Tracker rows at the top (newest first)
- Merge multiple same-day problems into one row with timestamped entries
- Keep Stats Summary in sync when logging progress

### Communication Patterns
- **Weekdays**: Report quick-stats only (time taken, approach, issues/hints)
- **Weekends**: Full interview-style walkthroughs (talk through approach out loud)
- User logs sessions with timestamped notes during problem-solving (read as real-time trace)

### Language & Tools
- Default language is Java (user's primary work language)
- LeetCode is the primary practice platform
- Java is used for all code discussions unless otherwise specified

### RTK-Specific Instructions
- Always prefix shell commands with `rtk` for token optimization
- Use `rtk proxy <cmd>` only when debugging is needed (bypasses filters)
- Predefined RTK aliases provide significant token savings on common operations