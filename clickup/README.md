# ClickUp Schemas

Schemas for BIF ClickUp integrations.

## Available Schemas

| Schema | Version | Description |
|--------|---------|-------------|
| [bif-cu-task-v1.json](./bif-cu-task-v1.json) | 1.0.0 | ClickUp task custom fields |

## bif-cu-task-v1.json

**Created:** 2026-01-04  
**Author:** Hui Newnham

Defines the canonical field mapping for ClickUp tasks used across all BIF integrations including Pipedream, Zapier, Google Drive, Gmail, HubSpot, and GitHub.

### Field Categories

- **Primary Identifiers** — BID, Namespace
- **Job Metadata** — Task Title, Job Type, Date Bucket, Date Promised
- **Storage Links** — G Drive, SharePoint, Job Dashboard
- **Gmail** — Label Name, Label ID
- **GitHub** — Repo URL, Active flag, Admin/Contributor/Reviewer users
- **HubSpot** — Email, First Name, Last Name, Record ID, Sync Status, Lifecycle
- **Workflow Control** — Record Lock, Error Flag, Error Message
- **AuthoredUp** — ID, URL

### Validation Rules

Before processing, tasks must pass these sanity checks:

1. **Namespace** — Must be non-empty 3-character code
2. **BID** — Must be empty (prevents duplicate processing)
3. **PER namespace** — Requires HubSpot email

### Usage

```javascript
const schema = await fetch('https://raw.githubusercontent.com/BIF-Big-Ideas-Foundry/bif-schemas/main/clickup/bif-cu-task-v1.json')
  .then(r => r.json());

// Get field ID
const bidFieldId = schema._field_mapping.primary_identifiers.bid.clickup_field_id;
// Returns: "63eef2c4-4bf4-4f95-9714-0cd97808be91"
```

## Changelog

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0.0 | 2026-01-04 | Hui Newnham | Initial schema creation |
