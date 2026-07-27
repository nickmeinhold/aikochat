# aikochat.org

The public front door and **legal pages** for **Aiko Chat**, served as static HTML
via GitHub Pages at [aikochat.org](https://aikochat.org).

## Why this exists (and why it's a separate repo)

The App Store and Google Play require **permanent, public URLs** for the privacy
policy, terms, and account-deletion instructions. Those URLs must outlive any single
Aiko Chat server ("island"). Serving them from an island box couples a permanent
store requirement to one container's uptime — and contradicts the federated,
no-central-server design where islands come and go.

So the legal pages live here instead: **repo-authoritative source of truth**, served
from durable static hosting, fronted by a domain (`aikochat.org`) that can be
repointed to any host. The durability primitive is the domain registration, not a
server.

## Pages

| URL | File | Purpose |
|-----|------|---------|
| `/` | `index.html` | Landing + links |
| `/privacy` | `privacy.html` | Privacy Policy (App Privacy / Data Safety source) |
| `/terms` | `terms.html` | Terms of Use & Community Guidelines |
| `/delete-account` | `delete-account.html` | Account-deletion steps (store requirement) |

`CNAME` pins the custom domain for GitHub Pages.

## Relationship to the island repo

These pages describe **Aiko Chat the app**, not any one island. The gateway
(`nickmeinhold/aiko-chat-island`) may still serve copies for same-origin in-app
links, but the **store-registered URLs point here**. When editing, this repo is the
canonical copy; keep the deletion/retention wording in sync with what
`accounts_service.delete_user_account` actually does.
