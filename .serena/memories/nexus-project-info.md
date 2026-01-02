# Nexus - Project Information

## Repository
- **Name**: nexus
- **URL**: https://github.com/krisk248/nexus
- **Author**: krisk248
- **License**: MIT

## Description
A beautiful terminal-based task manager with an **Ultraviolet** theme. Built with Go and Bubbletea.

## Tech Stack
- **Language**: Go
- **TUI Framework**: Bubbletea (Elm Architecture)
- **Styling**: Lip Gloss
- **Components**: Bubbles

## Project Structure
```
nexus/
├── cmd/tasklog/main.go          # Entry point
├── internal/
│   ├── app/
│   │   ├── model.go             # Main Bubbletea model
│   │   ├── update.go            # Message handlers
│   │   ├── view.go              # Rendering logic
│   │   └── messages.go          # Custom message types
│   ├── domain/
│   │   ├── task.go              # Task struct
│   │   ├── timeline.go          # Timeline events
│   │   └── calendar.go          # Calendar utilities
│   ├── storage/storage.go       # JSON persistence
│   └── theme/theme.go           # Ultraviolet theme
├── go.mod
├── Makefile
├── .goreleaser.yml
└── README.md
```

## Data Storage Paths
- **macOS**: `~/Library/Application Support/nexus/data.json`
- **Linux**: `~/.local/share/nexus/data.json`
- **Windows**: `%APPDATA%\nexus\data.json`

## Export Path
- **All platforms**: `~/Documents/nexus-exports/`

## Key Features
- Three-pane layout: Calendar | Tasks | Timeline
- Nested tasks with infinite subtask hierarchy
- Task states: Todo, Completed, Delegated, Delayed
- Task priorities: P1 (Critical), P2 (Important), P3 (Normal)
- Time tracking with start/stop timer
- Activity timeline with automatic logging
- Search & Filter functionality
- Export to Markdown, JSON, Plain Text
- Month Overview grid
- 50-state Undo history
- Vim-style navigation (hjkl + arrows)

## Keyboard Shortcuts
### Global
- `Ctrl+C` (twice): Exit
- `Ctrl+U`: Undo
- `Ctrl+E`: Export dialog
- `?`: Help
- `:`: Month overview
- `L`: Jump to logs/timeline
- `/`: Search tasks
- `Esc`: Clear search/filter
- `1/2/3`: Switch panes
- `Tab`: Next pane

### Calendar
- `h/l` or `←/→`: Previous/next day
- `j/k` or `↑/↓`: Previous/next week
- `n/p`: Next/previous month
- `T`: Jump to today

### Tasks
- `j/k` or `↑/↓`: Navigate
- `a`: Add task
- `e`: Edit task
- `d`: Delete task
- `Space`: Toggle complete
- `D`: Delegate task
- `x`: Toggle delayed
- `s`: Start/stop timer
- `1/2/3`: Set priority P1/P2/P3
- `0`: Clear priority
- `Enter` or `→`: Expand/collapse

### Timeline
- `j/k` or `↑/↓`: Scroll
- `Shift+C`: Clear timeline

## Theme: Ultraviolet
```
Background:     #0d0d14  (deep space black)
Surface:        #1a1625  (dark purple-gray)
Border:         #2d2640  (muted violet)
Primary:        #a855f7  (electric violet)
Secondary:      #c084fc  (soft lavender)
Accent:         #e879f9  (hot pink/magenta)
Success:        #22d3ee  (cyan glow)
Warning:        #f59e0b  (amber)
Error:          #f43f5e  (rose)
```

## Build Commands
```bash
# Build
go build -o nexus ./cmd/tasklog

# Run
./nexus

# Release (with goreleaser)
goreleaser release --snapshot --clean
```

## Important Notes for Development
- **ALWAYS ask user before committing** - no auto-commits
- **No Claude Code branding** in commit messages
- Only Ultraviolet theme (no theme switching)
- Timeline logs persist even when tasks are deleted
