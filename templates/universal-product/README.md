# Universal product template

This is a product-neutral configuration contract, not a finished UI package or deployment. Copy `product.config.json` to a product repository and supply that product's identity, division, links, capabilities and integrations. The approved corporate and division tokens remain in `tokens/`.

## What every adopting product must decide

- Product and division identity, repository and public links.
- Which approved languages, themes and accessibility features it actually supports.
- Whether Adigun BOT is enabled and which documented product capabilities it exposes.
- Whether accounts, guest access, local saving, cloud saving or administration are enabled.
- Whether a server-side AI endpoint, product action adapter, Supabase project or Cloudflare deployment exists.

Use `null` or `false` for unavailable capabilities. Never use a template value to imply that an unimplemented backend, account system, translation, action or deployment exists.

## Shared interface and BOT contract

Use approved visual tokens and assets. Keep controls accessible and truthful. If the product includes Adigun BOT, follow the [component standard](../../components/AdigunBot/README.md): the backend stays server-side, actions use typed schemas, permissions are checked, consequential changes are previewed and confirmed, and product-native undo/redo is preserved where supported.

## Repository ownership

The `product.repository` field is the exclusive destination for application code, tests, product docs and deployment workflows. `references` are read-only standards. Inspect local work before migration, preserve history, and never re-clone over local work or force-push.

## Examples

Product-specific settings belong in named examples. See [AdigunSPs](examples/adigun-sps.config.json) for a PLC product with account, guest-session and cloud-storage settings. Those values are not defaults for other products.

## Delivery

Document only verified functionality, including setup, architecture, security, limitations, test evidence and deployment status. A configuration file or successful build is not proof of a working product.
