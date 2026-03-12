---
tags:
  - type/project
  - topic/project
---

# Linkflow

A link management and short URL platform similar to Bitly or Linktree.

## Goals

- Create branded short links with a simple management interface.
- Track clicks and engagement for each link.
- Support personal use first, with room to expand later.
- Make it useful for both single links and curated profile pages.

## Features

- Short links
- Redirect service
- Link analytics
- QR codes
- Custom slugs
- Click tracking

## Architecture

- Frontend: Next.js
- Backend: Node.js API
- Storage: PostgreSQL or SQLite
- Optional background jobs for analytics aggregation

## Future Ideas

- Team workspaces and shared link collections.
- Expiring links and password-protected links.
- UTM builder and campaign tracking.
- Public profile pages similar to Linktree.

## Tasks

- [ ] Define the first version of the link data model.
- [ ] Build the redirect endpoint and slug resolution flow.
- [ ] Create the dashboard for creating and editing links.
- [ ] Add click tracking and basic analytics views.
- [ ] Generate QR codes for each public short link.

## Related

- [[projects-moc]]
- [[menezes-to]]
