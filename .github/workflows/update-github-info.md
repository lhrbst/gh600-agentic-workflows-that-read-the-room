---
name: Update GitHub Info
on:
  workflow_dispatch:
permissions:
  contents: read
  pull-requests: read
tools:
  edit:
  web-fetch:
safe-outputs:
  create-pull-request:
    title-prefix: "[mona-site] "
    labels:
      - content-update
network:
  allowed:
    - github.blog
    - github.com
---

# Update Mona's GitHub Info website

Research recent official GitHub updates, make only relevant and well-sourced edits to the website content, and open a pull request for Mona to review.

## Research

1. Read `notes/mona-notes.md` and `site/content/github-info.md` before researching. Treat Mona's notes as editorial requirements and the existing content as the website's current coverage.
2. Review the latest posts at [GitHub Blog](https://github.blog/latest/) and the latest entries at [GitHub Changelog](https://github.blog/changelog/).
3. Use the official post or changelog entry as the source for each candidate update. Prefer items published in the last 30 days; if the latest relevant item is older, do not present it as a recent update.
4. Select only updates that help developers learn GitHub faster and fit the site's existing themes: collaboration, Copilot, or Actions. Ignore announcements that do not meaningfully improve the site.

## Draft the website update

- Update `site/content/github-info.md` only. Keep additions short, practical, and consistent with Mona's editorial angle.
- Include a direct link to the official GitHub Blog or Changelog source beside every update derived from it. Do not add unsupported claims or duplicate existing coverage.
- Preserve useful existing content. If no recent item is relevant, make no website changes and do not open a pull request.
- Review the final diff to confirm every change is focused, accurate, and traceable to the cited sources.

## Pull request

When there are relevant updates, use the `create-pull-request` safe output to open a pull request for Mona's review. The pull request description must clearly summarize:

- The website changes proposed and why they are relevant.
- Each GitHub Blog or GitHub Changelog source reviewed and used, with its title, publication date when available, and direct URL.
- Any sources reviewed but not used, with a brief reason for exclusion.

Do not merge the pull request or publish the changes. Mona must review the proposal before it goes live.