# Hephzibah Behulah — Design System

The canonical visual and reusable-component standard for the five Hephzibah Behulah divisions.

## Authority boundaries

- [hb-AI-policy](https://github.com/HephzibahBehulahHQ/hb-AI-policy) owns global AI-agent governance, security, testing, cloud execution and collaboration.
- This repository owns visual tokens, official assets, reusable UI standards, product templates and the Adigun BOT component standard.
- Division repositories own their domain guidance; product repositories own application code, product-specific requirements, tests and deployments.

## Corporate identity

The existing corporate tokens and approved assets remain authoritative and unchanged. Do not create, replace or modify official visual identity assets without explicit authorization.

## Current repository structure

```text
assets/corporate/                 approved corporate asset and handling guidance
tokens/                           corporate and division color tokens
components/AdigunBot/             reusable floating-copilot standards
templates/universal-product/      product-neutral configuration contract and examples
docs/                             naming and supporting standards
AGENTS.md                         repository-scoped instructions
```

## Key documents

- [Agent guidance](AGENTS.md)
- [Brand and product naming](docs/brand-and-product-naming.md)
- [Adigun BOT component standard](components/AdigunBot/README.md)
- [Universal product template](templates/universal-product/README.md)

## Architecture rules

1. All five divisions inherit the corporate visual foundation.
2. A division may apply its approved accent color and appropriate specialized components.
3. Product application logic stays in its dedicated product repository.
4. Shared components must be documented and tested in the consuming product.
5. Products adopt design-system changes explicitly; no existing working product is changed by documentation alone.
