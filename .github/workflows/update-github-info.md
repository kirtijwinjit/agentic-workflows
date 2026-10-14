---
name: update-github-info
on:
  workflow_dispatch:
  schedule:
    - cron: "17 9 * * *"
permissions:
  contents: read
  pull-requests: read
engine: copilot
network:
  allowed:
    - defaults
    - github.blog
    - awesome-copilot.github.com
    - github.com
tools:
  edit:
  web-fetch:
  github:
    toolsets: [default]
safe-outputs:
  create-pull-request:
    max: 1
    draft: true
    title-prefix: "[mona] "
---

# Update GitHub Info for Mona

You are updating Mona's GitHub info page from trusted sources.

## Required process

1. Read notes/mona-notes.md first to capture Mona's tone and priorities.
2. Read repository guidance and reference files using GitHub repository API tools, not terminal/CLI/sandbox shell commands.
3. Read external public guidance using web-fetch:
  - https://github.blog/latest/
  - https://github.blog/changelog/
  - web fetch https://awesome-copilot.github.com/workflows/
  - https://awesome-copilot.github.com/workflows/
4. Synthesize key updates that are relevant for Mona and avoid copy-pasting long sections.
5. Update site/content/github-info.md with a concise, useful summary.
6. Verify the markdown is well-structured and easy to skim.
7. Propose the change via safe outputs by creating a pull request for Mona to review.

## Pull request requirements

- Make the PR title clear and specific to the content refresh.
- In the PR body, include:
  - Sources consulted
  - What changed in site/content/github-info.md
  - Any assumptions or uncertainties
- Keep the PR focused only on this update.
