---
title: 'Git Help'
category: '2022'
tags:
  - meta
created: 2022-10-29T00:17:38.177Z
updated: 2022-10-29T00:17:38.177Z
---

## To backup `wiki` dir

1. Make sure you’re inside: `/Users/MohammedRaqeeb/Desktop/wiki`
2. `git add -A`
3. `git commit -m "commit message"
4. `git push`

## Update: 

- Made a custom shell function to achieve the above.
Using the [GitHub - Taitava/obsidian-shellcommands: Execute system commands via hotkeys or command palette in Obsidian (https://obsidian.md). Some automated events are also supported, and execution via URI links.](https://github.com/Taitava/obsidian-shellcommands)

```bash
function git-backup () {
  cd /Users/MohammedRaqeeb/Desktop/wiki
  git add -A
  git commit -m "backup $(date +%F)"
  git push -f 
}
```