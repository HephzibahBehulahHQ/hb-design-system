# Universal product template

This is a **configuration contract**, not a finished UI package. Copy `product.config.json` into a product and change the brand key, product identity, links and integrations. The canonical corporate and brand colors are in `tokens/`.

## Mandatory UI
- Corporate, division and product identity in a responsive accessible header; use verified approved logos only.
- Footer with real links and a dynamic copyright year.
- Theme switcher, language selector (English `en`, German `de`, Yoruba `yo`, Nigerian Pidgin `pcm`), accessible navigation and status feedback.
- Floating **Adigun BOT** launch button and chat panel on every product page, with keyboard access and mobile support.
- Do not render fake controls, unavailable translations or unimplemented product actions as working features.

## Localization
Each product supplies complete locale dictionaries for all four languages, including navigation, dialogs, error messages, validation and bot interface. Use stable translation keys, interpolation, fallback warnings during development, and language persistence. Language selection must not change engineering values or corrupt saved projects. Technical terminology can retain standard symbols and units.

## Adigun BOT integration
Adigun BOT is a shared **interface and protocol**. The product supplies its own verified documentation, capabilities, tools and action adapter. The AI backend is server-side; never embed secret keys in browser code. Enforce authentication/authorization where needed, rate limits, input validation and safe logging. Answers must distinguish documentation from guesses.

Product actions use a structured request: `{type, version, payload}`. The product adapter validates the payload against its own schema, checks capability and permissions, generates a preview/diff, asks for explicit user confirmation, then applies the action through the product's native state/undo system. Never allow the assistant to execute arbitrary code or silently overwrite work.

For circuit simulation, the simulator must define a canonical circuit document schema, component library, pin and wire constraints, coordinate/grid rules, collision handling and a native import API. The bot may propose a circuit document; the simulator validates and previews it before importing to the canvas. The bot cannot promise perfect placement until verified by automated and visual tests.

## Implementation order
1. Inventory existing design assets and application APIs.
2. Implement tokens, locale dictionaries, accessible shared shell and floating bot interface.
3. Connect product-specific documentation and a secure AI backend.
4. Implement product-specific action adapters and tests.
5. Migrate existing products on branches, test, then deploy with approval.

No AI backend, working assistant, translation bundle or circuit import integration is included in this configuration-only foundation.
