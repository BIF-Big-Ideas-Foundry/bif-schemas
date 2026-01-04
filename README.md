# BIF Schemas

**Maintained by:** Hui Newnham (hui@bif.llc)  
**Organization:** Big Ideas Foundry LLC

## ⚠️ Important

**Contact Hui before adding or modifying any schemas** to ensure consistency across the BIF ecosystem.

## Overview

This repository contains canonical data schemas for all BIF integrations. These schemas define field mappings, naming conventions, and validation rules used across the BIF tech stack.

## BID (BIF Primary Key)

All BIF records are identified by a **BID** — the primary key across all systems.

Format: `[NAMESPACE][4-digit serial]`

| Namespace | Description | Example |
|-----------|-------------|---------|
| BWO | BIF Work Order (internal) | BWO1368 |
| BIF | BIF Client Job (external) | BIF0042 |
| PER | Person (HubSpot Contact) | PER0789 |
| ANT | AutoNumber Test | ANT0001 |

## Schemas

| System | Schema | Status |
|--------|--------|--------|
| [ClickUp](./clickup/) | `bif-cu-task-v1.json` | ✅ Active |
| [HubSpot](./hubspot/) | — | 🔜 Planned |
| [Gmail](./gmail/) | — | 🔜 Planned |
| [GitHub](./github/) | — | 🔜 Planned |
| [Google Drive](./gdrive/) | — | 🔜 Planned |

## Usage in Pipedream

```javascript
// Fetch schema from GitHub
const schema = await fetch('https://raw.githubusercontent.com/BIF-Big-Ideas-Foundry/bif-schemas/main/clickup/bif-cu-task-v1.json')
  .then(r => r.json());

// Access field mappings
const bidFieldId = schema._field_mapping.primary_identifiers.bid.clickup_field_id;
```

## License

MIT — See [LICENSE](./LICENSE) for details.

