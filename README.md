# boomerang-notify

OpenCode plugin that sends macOS desktop notifications when child sessions complete.

## Installation

```bash
cd ~/.config/opencode/plugin/
git clone https://github.com/edmundmiller/boomerang-notify.git
```

## Usage

The plugin automatically:
1. Tracks when child sessions are spawned (sessions with a parentID)
2. Sends a macOS notification when a child session completes
3. Cleans up tracking when parent sessions end

No configuration required - just install and it works.

## Requirements

- macOS (uses `osascript` for notifications)
- OpenCode with plugin support
