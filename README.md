# Ai by Mai

This is the repo for the blog: [AI by Mai](https://www.aibymai.dev/). This blog is made using [Hugo](https://github.com/gohugoio/hugo) and [cactus](https://github.com/monkeyWzr/hugo-theme-cactus).

# SetUp

```
git clone git@github.com:13Mai13/aibymai.git

hugo serve
```

# Working with Drafts

Articles tagged with `Draft` will not appear in the main writings list or homepage. They are only visible on the drafts page.

**To create a draft article:**
1. Add `Draft` to the tags in the article's front matter:
```yaml
---
title: "My Draft Article"
date: 2026-03-26
tags:
    - Draft
    - Other Tag
---
```

**To view all drafts:**
- Locally: http://localhost:1313/drafts
- Production: https://www.aibymai.dev/drafts

This page is not linked in the navigation menu but is accessible directly via URL.

