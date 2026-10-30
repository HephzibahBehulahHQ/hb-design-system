# Instructions for AI coding agents

This repository is the canonical Hephzibah Behulah design system for all five divisions. Read `README.md`, `tokens/corporate.json`, `tokens/brands.json`, `docs/brand-and-product-naming.md` and `templates/universal-product/README.md` before modifying a product.

**Repository boundary:** Each product's complete application code, tests, deployment workflows and documentation belong in its own dedicated product repository. Corporate website, division and design-system repositories are authoritative references, not destinations for product application code. Inspect local unpushed work before relying on a remote repository. Preserve working history and uncommitted files. Never reset, re-clone over, force-push or silently rename/transfer a product.

**Brand:** Use Hephzibah Behulah → HB Division → Adigun Product; one verified official corporate logo in the header, product wordmark and subtle division label; approved tokens, responsive header/footer, verified links, accessible light/dark themes and full en/de/yo/pcm localization. No fabricated assets, placeholder controls or incomplete translations presented as working.

**Accounts and persistence:** When enabled for a product, implement real email/password auth, profile and avatar, guest-access policy, safe guest-work recovery, cloud and local project saving, and secure owner-scoped data access. Enforce administrator roles on trusted backend data, never editable user profile metadata. Use RLS for exposed Supabase tables and suitable storage policies. Never ship secret keys in frontend code. Cloudflare hosting and Supabase integration must be verified against the actual product architecture; neither is implemented by this template.

**Adigun BOT:** Floating product-aware assistant UI, backed by secure services and validated product-specific tools. Actions require schema validation, permissions, preview, user confirmation and undo where supported. Never claim a mockup or configuration is a functioning bot.

**Quality:** Every advertised button, menu, component, property editor and sample project must be functional and tested. No dummy components, misleading simulation, broken wiring, overlapping/overflowing UI or unverified pass counts. For PLC products, verify standards-based naming, properties, terminals, variables and logic; individually test every promised example project (AdigunSPs targets 200). For circuit generation, require native schema and validated canvas import.

Work incrementally, preserve existing application features, run regression and security tests, verify builds, and report actual Done / Tested / Next. Never claim zero errors or successful push/deployment without evidence.
