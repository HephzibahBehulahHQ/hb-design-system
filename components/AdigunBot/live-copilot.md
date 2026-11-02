# ADDENDUM A — GLOBAL ADIGUN BOT INTELLIGENCE, PURPOSE AND LIVE COPILOT STANDARD

**Standard ID:** HB-AI-ADIGUNBOT-002  
**Version:** 1.0  
**Applies to:** Every Hephzibah Behulah product, application, platform, website and future software division.  
**Parent specification:** Global Adigun BOT Floating AI Copilot Component Standard.

---

## A1. UNIVERSAL PURPOSE OF ADIGUN BOT

Adigun BOT is the official intelligent, context-aware, action-capable AI assistant integrated into Hephzibah Behulah software products.

Its purpose is to help users accomplish the actual goals of the product in which it operates.

Adigun BOT must not be limited to answering questions or generating text.

Where the host application provides the necessary functionality, Adigun BOT must be capable of:

1. Understanding the user's current work and goals.
2. Observing relevant application state in real time.
3. Explaining the current project or selected content.
4. Identifying verifiable errors, omissions and opportunities.
5. Proactively offering useful assistance.
6. Creating new product-native content and projects.
7. Editing existing content through authorized application tools.
8. Analyzing and validating work against applicable rules.
9. Performing supported calculations and simulations.
10. Importing generated results directly into the application's workspace.
11. Automating repetitive workflows with appropriate approval.
12. Explaining actions and their consequences.
13. Supporting beginners and advanced users.
14. Learning the current session's stated goals and preferences.
15. Preserving user control, data security and undo capabilities.

**The BOT's intelligence, tools, terminology, workflows and capabilities must adapt to its host product.**

There must not be one generic, prompt-only BOT that behaves identically across unrelated applications.

## A2. GLOBAL COMPONENT, PRODUCT-SPECIFIC INTELLIGENCE

Maintain one reusable global Adigun BOT foundation.

The foundation supplies common capabilities:

- Floating chat interface.
- Window controls and persistence.
- Conversation management.
- AI provider integration.
- Tool-calling infrastructure.
- Real-time application context.
- Proactive suggestion framework.
- Notification handling.
- User approvals.
- Audit logging.
- Error recovery.
- Localization.
- Accessibility.
- Authentication and permission checks.

Each product must supply its own domain adapter.

The domain adapter defines:

- Product identity.
- Product purpose.
- Supported workflows.
- Domain-specific knowledge.
- Available application tools.
- Readable application state.
- Writable application state.
- Validation rules.
- Supported calculations.
- Supported import and export formats.
- Action permissions.
- Safety boundaries.
- Testing requirements.

Do not hardcode electrical engineering, cybersecurity, religion, finance, education or any other specialized domain into the shared BOT foundation.

Domain-specific capabilities belong in the appropriate product adapter.

## A3. PRODUCT CAPABILITY CONTRACT

Every product integrating Adigun BOT must declare a machine-readable capability contract.

Suggested configuration:

`adigun-bot.config.json`

The configuration must identify:

- Product ID and display name.
- Division.
- Product description.
- Available languages.
- Supported AI features.
- Context providers.
- Available tools.
- Tool input and output schemas.
- Tool permission levels.
- Confirmation requirements.
- Validation capabilities.
- Supported content types.
- Persistence capabilities.
- Simulation or execution capabilities.
- Domain-specific safety rules.
- Applicable help documentation.

The BOT must discover and use only tools that are actually implemented and registered.

Never advertise a feature that the host product does not support.

If a capability is unavailable, explain the limitation and offer the closest supported alternative.

## A4. EXAMPLES OF PRODUCT-SPECIFIC BOT BEHAVIOR

These examples illustrate the required architecture. They do not limit future products.

### Electrical engineering and electronic design products

The BOT should be able to:

- Understand electrical and electronic schematics.
- Identify existing components and connections.
- Design circuits from natural-language instructions.
- Select compatible components using verified data.
- Create valid product-native schematic objects.
- Route supported electrical connections.
- Insert completed designs into the actual canvas.
- Explain electrical behavior.
- Analyze incomplete or disconnected circuits.
- Run available simulations.
- Interpret simulation results.
- Perform supported engineering calculations.
- Generate bills of materials.
- Validate applicable engineering rules.
- Assist with control panels, PLC logic and electrical documentation where supported.

Example request:

"Design a three-phase motor starter with start, stop, overload protection and indicator lamps."

Expected behavior:

1. Interpret the engineering requirements.
2. Ask for essential missing specifications.
3. Select appropriate verified components.
4. Generate a valid circuit model.
5. Check connectivity and relevant constraints.
6. Show a schematic preview.
7. Explain assumptions and limitations.
8. Request permission to insert the design.
9. Import it into the real editor through the application API.
10. Preserve undo/redo and project integrity.
11. Report validation results accurately.

Do not replace this workflow with a decorative image or unconnected diagram.

### Cybersecurity products

The BOT should understand the current authorized security workspace and help with:

- Security findings.
- Risk assessment.
- Vulnerability interpretation.
- Log analysis.
- Defensive investigation.
- Security reporting.
- Remediation recommendations.
- Authorized testing workflows.

It must operate within the application's permissions and applicable security restrictions.

### Data analytics products

The BOT should be able to:

- Understand available datasets.
- Explain columns and metrics.
- Generate supported analyses.
- Identify data-quality issues.
- Create charts and dashboards.
- Apply transformations through authorized tools.
- Explain calculations.
- Export supported analytical results.

### Artificial intelligence and machine-learning products

The BOT should help users:

- Prepare datasets.
- Configure supported models.
- Explain training metrics.
- Inspect evaluation results.
- Generate supported experiments.
- Compare model performance.
- Identify reproducible errors.
- Operate available AI workflows.

### Religious, educational and theological products

The BOT should adapt to the product's religious or educational purpose.

Depending on the product, it may:

- Explain religious texts and concepts.
- Help users navigate approved study resources.
- Create lesson plans.
- Assist with educational content.
- Compare interpretations with appropriate attribution.
- Generate study questions.
- Support multilingual learning.
- Organize educational materials.

It must distinguish quotations, source-backed claims, interpretations and generated commentary.

It must not fabricate scriptural quotations, citations or source references.

### Business and productivity products

The BOT should support the actual product workflows, including:

- Document creation.
- Structured planning.
- Business analysis.
- Workflow assistance.
- Reporting.
- Authorized task automation.

These examples establish the principle:

**Every Adigun BOT must be deeply integrated with the actual purpose and functionality of its host product.**

## A5. LIVE APPLICATION-AWARE COPILOT

Upgrade Adigun BOT from a reactive prompt-only assistant into a live copilot.

The BOT must be capable of understanding relevant changes occurring inside the active product workspace.

For canvas-based applications, this may include:

- Components.
- Objects.
- Connections.
- Layers.
- Coordinates.
- Selection state.
- Project metadata.
- Simulation state.
- Validation findings.
- Recent edits.

For non-canvas applications, equivalent context may include:

- Current document.
- Selected text.
- Active dataset.
- Dashboard filters.
- Open lesson.
- Current workflow.
- Security findings.
- Selected records.
- User-approved task context.

Use the host application's actual state APIs.

Do not infer authoritative application state from screenshots when structured state is available.

## A6. REAL-TIME STATE SUBSCRIPTION

Implement a product-aware context subscription.

Requirements:

1. Subscribe to meaningful application-state changes.
2. Receive typed, structured events.
3. Debounce or batch high-frequency changes.
4. Distinguish committed changes from temporary interactions.
5. Track the active document, project or workspace.
6. Detect selection changes where relevant.
7. Track supported execution or simulation status.
8. Maintain a current context version.
9. Handle project switching correctly.
10. Unsubscribe and clean up listeners when necessary.

Suggested event types:

- `project.opened`
- `project.changed`
- `document.updated`
- `object.added`
- `object.modified`
- `object.deleted`
- `selection.changed`
- `connection.changed`
- `validation.completed`
- `simulation.completed`
- `user.idle`
- `user.active`
- `tool.execution.completed`

Products may extend this vocabulary.

Do not transmit every mouse movement, keystroke or full project state to an external AI service.

Prefer local event processing and minimal relevant context.

The BOT must not continuously transmit sensitive user data without an appropriate lawful basis, notice and authorization.

## A7. CONTEXT ANALYZER

Build a domain-specific analyzer that interprets the live application state.

The analyzer must identify meaningful findings using verifiable rules and available product data.

Possible finding categories:

- Incomplete work.
- Invalid configuration.
- Missing required elements.
- Unconnected or unused objects.
- Inconsistent settings.
- Duplicate or conflicting definitions.
- Failed validation.
- Unsupported combinations.
- User-requested opportunities for improvement.
- Ambiguous project goals.

Use deterministic validation rules wherever possible.

The language model may interpret findings and propose solutions, but must not fabricate analyzer results.

Each finding should include:

- Finding ID.
- Product and project scope.
- Relevant object identifiers.
- Evidence.
- Severity.
- Confidence where applicable.
- Recommended action.
- Validation source.
- State version.

A finding must be invalidated or recalculated when the relevant application state changes.

## A8. PROACTIVE SUGGESTION ENGINE

The BOT should offer relevant assistance without waiting for a direct question.

Examples:

Electrical design:
"I noticed this motor control circuit has no overload protection. Would you like me to review the protection arrangement?"

Data analytics:
"This dataset contains missing values in a field used by your chart. Would you like me to inspect them?"

Cybersecurity:
"Three findings appear to share the same affected asset. Would you like me to group them for review?"

Educational application:
"You have completed this lesson. Would you like a short knowledge check?"

Suggestions must be grounded in actual application state.

Do not invent warnings or claim to have detected problems that were not verified.

### Suggestion structure

Each suggestion must contain:

- Short title.
- One-line explanation.
- Relevant context.
- Proposed action.
- Accept button.
- Dismiss button.
- Tell me more button.

Where appropriate, include severity and evidence.

### Nonintrusive presentation

Suggestions should appear as:

- A compact speech bubble.
- A small dismissible side panel.
- A notification attached to the BOT launcher.
- A lightweight toast.

Never force-open the floating chat window.

Never steal focus during active work.

Never display a blocking modal for ordinary suggestions.

## A9. RATE LIMITING AND INTERRUPTION CONTROL

The live copilot must be calm and respectful of user attention.

Default behavior:

- No more than one ordinary proactive suggestion every 20–30 seconds.
- Suppress suggestions during dragging, typing, drawing or other active interactions.
- Avoid repeating dismissed suggestions.
- Group related findings.
- Prefer high-value suggestions.
- Suppress stale suggestions.
- Allow users to disable proactive assistance.

Provide configurable modes:

- Off.
- Quiet.
- Standard.
- Proactive.

Default to a nonintrusive mode appropriate for the product.

Critical, verified safety findings may use a distinct notification policy, but must still avoid unsupported alarm claims.

## A10. USER INTENT AND GOAL UNDERSTANDING

The BOT should understand what the user is trying to accomplish.

Sources may include:

- Explicit user instructions.
- Project description.
- Selected workflow.
- Active document.
- Recent authorized interactions.
- Current project metadata.

If the goal is unclear, ask a concise clarifying question.

Examples:

"What are you trying to build?"

"Should I optimize this design for cost, efficiency or maintainability?"

"Would you like an explanation or should I prepare a change?"

Remember the answer within the relevant session or project scope.

Do not permanently store inferred personal preferences without appropriate authorization.

## A11. ACTION-CAPABLE AI TOOLS

Every product must expose appropriate application tools to Adigun BOT.

Use typed, validated tool interfaces.

Suggested universal tool categories:

### Read tools

- Get current project.
- Get current selection.
- Get document structure.
- Get validation results.
- Get available capabilities.
- Get supported component or content catalog.

### Create tools

- Create product-native objects.
- Generate supported projects.
- Add components or content.
- Insert generated results into the workspace.

### Edit tools

- Modify selected objects.
- Update properties.
- Reorganize supported content.
- Apply validated changes.

### Analyze tools

- Validate current work.
- Run supported calculations.
- Execute authorized simulations.
- Explain detected problems.

### Export tools

- Generate supported reports.
- Export supported project formats.
- Create product-specific deliverables.

The actual tools must be implemented by the host product.

Do not create a universal tool that bypasses domain-specific validation.

## A12. NATURAL LANGUAGE TO REAL WORKSPACE ACTION

A central requirement is that Adigun BOT must be capable of turning natural-language requests into actual product-native operations.

For example, an electrical design request must be capable of producing real schematic objects and connections rather than merely describing them.

Required execution pipeline:

1. Interpret the user request.
2. Read the relevant current project context.
3. Check supported product capabilities.
4. Identify missing requirements.
5. Produce a structured action plan.
6. Validate proposed operations.
7. Generate a preview or diff.
8. Request user approval.
9. Execute through authorized product APIs.
10. Verify the resulting application state.
11. Record the change in undo/redo history where supported.
12. Report success or failure accurately.

For multi-step operations, use transactions or equivalent rollback mechanisms where practical.

Never claim an operation succeeded simply because the language model generated a plausible response.

## A13. APPROVAL, PREVIEW AND ROLLBACK

The BOT must never silently make consequential changes to a user's project.

For proposed modifications:

- Explain what will change.
- Show affected objects or content.
- Provide a preview where feasible.
- Request explicit confirmation.
- Apply the change through validated tools.
- Preserve an undo mechanism where supported.
- Roll back failed operations where technically possible.

If rollback is not supported, disclose that limitation before execution.

The user remains in control.

## A14. LIVE EXPLANATIONS

The BOT should be able to explain the current application state.

Examples:

- "What does this component do?"
- "Why is this circuit not working?"
- "Explain this chart."
- "What does this security finding mean?"
- "Summarize this lesson."
- "What changed in my project?"

Use the actual selected object, document, dataset or project context.

Distinguish verified facts from assumptions.

Do not invent nonexistent components, connections, data fields or project history.

## A15. GUEST AND AUTHENTICATED ACCESS

Provide useful AI assistance to guests where the product permits it.

Guest users may receive:

- Contextual explanations.
- Supported live suggestions.
- Local analysis.
- Previews.
- Permitted temporary workspace operations.

Apply product-specific usage limits and security controls.

Authentication is required for account-bound cloud saving and other protected operations.

Do not require login merely to display an explanation when guest access is supported.

### Saving behavior

The BOT must not automatically save projects to local or cloud storage solely because it generated a suggestion.

Saving must follow the host product's explicit save workflow and permissions.

Guest saving rules must match the product's approved behavior.

Do not assume all local saving requires authentication.
