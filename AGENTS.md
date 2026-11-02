# Design-system agent guidance

## Authority and scope

The [global AI policy](https://github.com/HephzibahBehulahHQ/hb-AI-policy) takes precedence for agent governance, security, testing, source control, cloud work, token efficiency and reporting. This repository is canonical for visual tokens, approved brand assets, reusable UI standards, templates and the Adigun BOT component standard.

Read `README.md`, the relevant token files and component documentation before a change.

## Boundaries

- Keep product application code, product tests, deployment workflows, product data and product-specific engineering requirements in their product repositories.
- Do not modify approved image assets, tokens, colors, themes, accents, logos, mission or company identity without explicit authorization.
- Keep global AI-agent policy in `hb-AI-policy`; local instructions here must remain design-system-scoped.
- Keep templates product-neutral. Put product-specific values in named examples.

## Adigun BOT

Start at [components/AdigunBot/README.md](components/AdigunBot/README.md). Product adapters must expose only implemented, authorized and validated capabilities; no mock functionality may be represented as working.

## Change rules

Use a dedicated branch and PR. Validate changed JSON and Markdown links. Do not merge, deploy, change access controls or claim tests/integrations without evidence.

STATUS

- Done:
- Tested:
- Blocked:
- Next:
