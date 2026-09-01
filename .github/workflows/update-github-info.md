---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
"on":
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
tools:
  edit:
  web-fetch:
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
network:
  allowed:
    - github.blog
    - github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use the web-fetch tool to fetch https://github.blog/latest/ and https://github.blog/changelog/ for the latest GitHub Blog and GitHub Changelog updates. Read external public guidance with web-fetch, and prefer GitHub repository API tools for repository guidance or reference files instead of terminal, CLI, or sandboxed commands.

Review the latest GitHub Blog and GitHub Changelog updates, then update `site/content/github-info.md` with concise, practical changes for readers. Keep the information accurate, include source context when content is derived from the GitHub Blog or GitHub Changelog, and preserve Mona's website voice.

Open a pull request for Mona to review using safe-outputs with create-pull-request. Do not write directly to `main`; rely on the pull request flow so Mona can approve the final update before it is merged.
