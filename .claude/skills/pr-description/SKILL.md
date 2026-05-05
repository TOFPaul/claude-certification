---
name: pr-description
description: Writes descriptions for pull requests. Use when creating a PR, writing a PR, or when the users asks to summarize changes for a pull request
model: sonnet
allowed-tools: Read, Grep, Glob, Bash
---

When writing a PR description:

1. Run `git diff main...HEAD` to see all changes on this branch
2. Write a description following this format:

## What
One sentence explaining what this PR does.

## Why
Brief context on why this change is needed

## Changes
- Bullet points of specific changes made
- Group related changes together
- Mention any files deleted or renamed