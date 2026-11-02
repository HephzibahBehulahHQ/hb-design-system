# Global Adigun BOT — Floating AI Copilot Component Standard

**Standard ID:** HB-UI-ADIGUNBOT-001  
**Version:** 1.1  
**Scope:** Reusable Adigun BOT component requirements for Hephzibah Behulah products.  
**Status:** Mandatory design-system component standard.

The global AI-agent policy in [hb-AI-policy](https://github.com/HephzibahBehulahHQ/hb-AI-policy) governs agent operation, security and approvals. These documents govern the reusable component and product-integration contract.


## 1. PRIMARY OBJECTIVE

Replace every existing fixed, blocking or modal-based Adigun BOT chat interface with a professional, floating, draggable, resizable, minimizable, maximizable and persistent AI copilot window.

The new Adigun BOT must allow users to continue working inside the application while simultaneously communicating with the AI assistant.

The BOT must behave like a lightweight desktop application window floating above the workspace, rather than a traditional modal dialog.

**Fundamental principle: The user must never lose access to the application workspace simply because Adigun BOT is open.**

This standard must be reusable across all Hephzibah Behulah products without rebuilding the same functionality separately.

## 2. GLOBAL CORPORATE INTEGRATION

Before implementation, inspect and follow the authoritative corporate resources:

Corporate website:
https://github.com/HephzibahBehulahHQ/HephzibahBehulahHQ.github.io

Global design system:
https://github.com/HephzibahBehulahHQ/hb-design-system

Elektroniker division:
https://github.com/HephzibahBehulahHQ/hb-elektroniker

Follow the existing corporate branding hierarchy:

**Hephzibah Behulah → Division → Product → Adigun BOT**

Use the official corporate logo, design tokens, typography, theme settings, component conventions and product-specific accent colors.

For HB Elektroniker products, use the approved electric-cyan division accent where appropriate.

Do not invent a new corporate logo, unrelated BOT identity or competing visual design system.

The floating BOT must integrate seamlessly with light mode, dark mode, responsive layouts and the global navigation structure.

## 3. REQUIRED COMPONENT ARCHITECTURE

Implement the BOT as a reusable global component with a clear separation between:

1. Floating window presentation.
2. Window state management.
3. Drag-and-resize interaction engine.
4. Chat transcript and message composer.
5. AI provider and backend integration.
6. Product context integration.
7. Notification and unread-message handling.
8. Persistent user preferences.
9. Accessibility and keyboard interactions.
10. Security, logging and testing.

Suggested component structure:

`components/AdigunBot/`

- `AdigunBotFloatingWindow`
- `AdigunBotLauncher`
- `AdigunBotHeader`
- `AdigunBotConversation`
- `AdigunBotComposer`
- `AdigunBotWindowControls`
- `AdigunBotResizeHandle`
- `AdigunBotStatusIndicator`
- `AdigunBotNotificationBadge`
- `AdigunBotContextFooter`
- `AdigunBotSettings`
- `useAdigunBotWindow`
- `useAdigunBotPersistence`
- `useAdigunBotNotifications`
- `useAdigunBotContext`

Adapt component naming to the actual project framework.

Avoid introducing unnecessary dependencies or duplicating existing design-system functionality.

## 4. FLOATING NON-MODAL WINDOW

Clicking the Adigun BOT launcher must open a floating chat window above the active application workspace.

Requirements:

- Do not use a blocking full-screen modal on desktop.
- Do not render a backdrop that intercepts workspace interactions.
- Do not disable canvas interaction.
- Do not lock page scrolling unless required by the mobile presentation.
- Keep the floating window above ordinary application panels.
- Allow interaction with the workspace outside the BOT window.
- Ensure pointer events inside the BOT window operate normally.
- Ensure pointer events outside the BOT window reach the underlying application.
- Avoid unintended canvas selection or drawing actions when interacting with the BOT.
- Use an appropriate design-system-managed z-index rather than arbitrary extreme values.

The BOT must feel like a native floating workspace tool.

## 5. DRAG-TO-MOVE FUNCTIONALITY

Users must be able to move the BOT window by dragging its header.

Requirements:

- Dragging begins only from designated header regions.
- Header buttons must remain clickable without starting a drag.
- Use pointer events for consistent mouse, stylus and touch support.
- Update the window position smoothly.
- Prevent text selection during dragging.
- Prevent accidental dragging when typing or selecting messages.
- Constrain the window within the available viewport or workspace bounds.
- Ensure the title bar and window controls remain accessible.
- Recalculate valid coordinates after browser resizing.
- Prevent the window from becoming permanently inaccessible.

Persist the last valid position after dragging ends.

Do not perform a database write on every pointer movement.

Use appropriate animation-frame scheduling or equivalent performance optimization during dragging.

## 6. RESIZABLE WINDOW

Provide a visible but unobtrusive resize affordance, normally at the bottom-right corner.

Where appropriate, support additional edge or corner resizing.

Desktop default size:

- Width: approximately 420 px.
- Height: approximately 600 px.

Recommended minimum size:

- Width: 320 px.
- Height: 400 px.

Recommended maximum size:

- No greater than the available viewport minus a reasonable margin.
- Allow larger sizes on sufficiently large screens, up to approximately 900 × 800 px by default.

These values are design defaults, not rigid requirements on smaller viewports.

Requirements:

- Smooth resize behavior.
- Chat transcript expands or contracts correctly.
- Message composer remains visible.
- No clipped controls.
- No horizontal overflow.
- No broken text wrapping.
- No layout shift in the underlying canvas.
- Preserve the last user-selected size.
- Clamp dimensions after viewport changes.
- Support touch resizing where practical.

Save the final dimensions after the resize interaction ends.

## 7. WINDOW CONTROLS

Display the following controls at the top-right of the BOT header.

### Minimize

Minimize the BOT to a compact header, pill or docked indicator.

The conversation remains in memory.

The user can restore it immediately.

Minimizing must not delete messages or interrupt an in-progress request unnecessarily.

### Maximize

Expand the window to occupy most of the available desktop viewport.

Maintain an appropriate margin around the window.

Maximization must not create an inaccessible overlay or permanently disable the underlying workspace.

Save the previous normal dimensions and coordinates before maximizing.

### Restore

Return the window to its previous normal position and size.

Restoration must work correctly after minimizing or maximizing.

### Close

Hide the BOT window completely while keeping its launcher accessible.

Closing must not automatically delete chat history.

Reopening must restore the last appropriate position and size.

### Tooltips

All window controls must provide clear localized labels and tooltips.

Use recognizable icons:

- Minimize: horizontal dash.
- Maximize: square.
- Restore: overlapping squares.
- Close: X.

## 8. ADIGUN BOT LAUNCHER

Provide a persistent launcher in the application's approved interface location.

Possible placements:

- Bottom-right floating action button.
- Global toolbar.
- Product navigation bar.
- Existing AI assistant entry point.

Follow the existing application pattern rather than adding multiple competing launchers.

### Launcher behavior

When closed:
- Click opens the BOT.

When minimized:
- Click restores the BOT.

When already open:
- Click brings the BOT into focus or to the front.

When maximized:
- Click focuses the existing BOT rather than creating another instance.

Do not create duplicate windows from repeated launcher clicks.

### Notification indicators

The launcher must display appropriate notification indicators for:

- New assistant messages.
- Pending suggestions.
- Completed background AI operations.
- Actions requiring user review.

Unread counts must update correctly and clear when the corresponding content is viewed.

## 9. PERSISTENT WINDOW STATE

Persist the following state:

- Open or closed.
- Normal window position.
- Normal window dimensions.
- Minimized state.
- Maximized state.
- Previous restore geometry.
- Unread-message count where appropriate.
- Selected conversation.
- Product and project context identifiers.

### Guest users

Use browser-local storage where appropriate.

Namespace keys by product, application version and user/session identity to avoid collisions.

Example logical namespace:

`hb:adigun-bot:<product-id>:<user-scope>:window:v1`

Do not store confidential AI messages, credentials or sensitive engineering data in unprotected localStorage.

### Authenticated users

Use Supabase-backed preferences when an authenticated account and approved Supabase integration are available.

Store window preferences separately from chat content.

Use authenticated, owner-scoped access controls.

Apply Row Level Security to relevant user-owned tables.

Do not permit one user to read or modify another user's window preferences.

### Cross-device behavior

Window dimensions and coordinates are device-specific.

Do not blindly apply a large desktop window position to a small mobile screen.

Use device-class or viewport-aware preference handling.

Clamp restored geometry to the current viewport.

### Synchronization

Prefer local-first UI updates.

Synchronize to Supabase asynchronously where supported.

Handle network failures gracefully.

If cloud synchronization fails, continue operating with the available local preferences.

Use a documented conflict-resolution strategy for preferences changed on multiple devices.

## 10. SUPABASE DATA MODEL

Where the application already uses Supabase, extend the existing schema carefully.

Suggested logical table:

`user_bot_window_preferences`

Suggested fields:

- `id`
- `user_id`
- `product_id`
- `project_id` (nullable)
- `device_class`
- `is_open`
- `is_minimized`
- `is_maximized`
- `position_x`
- `position_y`
- `width`
- `height`
- `restore_geometry`
- `updated_at`

Add an appropriate unique constraint for the selected preference scope.

Use database migrations rather than manual, undocumented schema edits.

Implement owner-only policies based on authenticated user identity.

Do not create unnecessary duplicate preference tables if the project already provides an equivalent settings system.

## 11. CHAT INTERFACE

The floating window must preserve all existing working Adigun BOT functionality.

### Header

Display:

- Adigun BOT title.
- Product context or division identifier where appropriate.
- AI availability status.
- Minimize, maximize/restore and close controls.

### Conversation area

Provide:

- Scrollable message history.
- Clear distinction between user and assistant messages.
- Proper rendering of supported Markdown and code.
- Safe display of engineering results.
- Loading and streaming indicators where supported.
- Error and retry states.
- Auto-scroll behavior that respects users reading older messages.
- Accessible message announcements.

### Message composer

Provide:

- Multiline text input.
- Send button.
- Keyboard submission behavior.
- Disabled or pending state where appropriate.
- Optional attachment controls only where actually supported.
- Clear feedback for errors.

Enter may submit a message, while Shift+Enter inserts a newline.

Prevent accidental duplicate submissions.

### Footer

Where useful, display:

- Current product.
- Current project.
- Current drawing or canvas.
- AI connection status.
- Clear conversation action.

Clearing chat history must require deliberate user action.

## 12. LIVE AI COPILOT INTEGRATION

The floating window is the presentation layer for the existing functional Adigun BOT.

Do not replace a working AI backend with hardcoded messages or a dummy interface.

The BOT must remain product-aware.

Depending on the application, it may assist with:

- Electrical schematic design.
- Component selection.
- Circuit validation.
- Simulation explanation.
- Lighting design.
- PLC-related workflows.
- Engineering calculations.
- Project documentation.
- CAD operations.
- Error interpretation.

Only expose tools that are actually implemented and authorized.

### Proactive suggestions

When the BOT detects a useful suggestion:

1. Do not automatically open the chat window.
2. Do not steal keyboard focus.
3. Do not interrupt an active canvas interaction.
4. Update the launcher notification badge.
5. Display a nonintrusive toast where appropriate.
6. Preserve the suggestion until viewed or dismissed.

The user controls when to open the BOT.

### AI actions affecting the workspace

For actions such as adding components, editing schematics, modifying geometry or changing project settings:

- Validate tool inputs.
- Show a preview where feasible.
- Explain expected changes.
- Request confirmation before consequential changes.
- Execute through authorized application APIs.
- Preserve undo/redo support.
- Report actual execution results.
- Never claim a modification succeeded without confirmation.

## 13. ACCESSIBILITY

Implement keyboard-accessible window controls.

Requirements:

- Launcher is keyboard reachable.
- Controls have accessible names.
- Focus indicators are visible.
- Focus moves appropriately when the BOT opens.
- Closing returns focus to the launcher when appropriate.
- Tab and Shift+Tab follow a predictable order.
- Escape closes or minimizes the window according to a documented convention.
- Enter sends messages where appropriate.
- Shift+Enter inserts a newline.
- Window status and notifications are announced accessibly.
- Dragging is not the only way to reposition the window.

Provide keyboard-accessible movement and resizing alternatives, such as an accessible position/size menu or documented keyboard commands.

Use appropriate non-modal accessibility semantics.

Do not mark the floating window as modal when the background remains interactive.

Avoid trapping keyboard focus inside a non-modal panel.

Use accessible labeling for the title, conversation region, composer and window controls.

Respect reduced-motion preferences.

## 14. MOBILE AND TOUCH BEHAVIOR

On smaller screens, use an adaptive presentation.

Recommended behavior:

- Desktop: floating, draggable, resizable panel.
- Tablet: floating panel where practical, with viewport-aware constraints.
- Mobile: full-screen or near-full-screen chat view.

On mobile:

- Provide a prominent close button.
- Respect safe-area insets.
- Keep the composer visible above the virtual keyboard.
- Avoid horizontal scrolling.
- Prevent content from being hidden beneath fixed navigation.
- Preserve conversation state during orientation changes.
- Do not require dragging or resizing to access essential functions.

Support pointer and touch interactions without interfering with the application's own touch gestures.

## 15. THEME AND VISUAL DESIGN

The BOT must use the global Hephzibah Behulah design system.

Requirements:

- Official corporate branding.
- Approved division accent.
- Existing typography.
- Existing icon conventions.
- Consistent border radius.
- Professional shadows and elevation.
- Light and dark themes.
- Responsive spacing.
- High-contrast focus indicators.
- Clear status colors.
- Smooth but restrained transitions.

Avoid heavy modal styling.

Avoid excessive animations, glowing effects or distracting visual elements.

The interface should feel professional, lightweight and suitable for technical engineering software.

## 16. FOUR-LANGUAGE LOCALIZATION

Support the corporate languages:

- English (`en`).
- German (`de`).
- Yoruba (`yo`).
- Nigerian Pidgin (`pcm`).

Localize:

- Window titles.
- Tooltips.
- Buttons.
- Status indicators.
- Notifications.
- Error messages.
- Settings.
- Help documentation.
- Accessibility labels.

Reuse the product's existing localization infrastructure.

Do not hardcode English labels into the shared component.

Ensure translated labels do not overflow controls.

## 17. PERFORMANCE REQUIREMENTS

The floating BOT must not degrade the performance of engineering canvases, 3D scenes or simulation engines.

Requirements:

- Avoid unnecessary canvas re-renders during dragging.
- Throttle or schedule pointer-driven updates appropriately.
- Persist state after interactions rather than on every movement.
- Use efficient message rendering for long conversations.
- Clean up event listeners.
- Prevent memory leaks.
- Avoid duplicate AI connections.
- Suspend unnecessary work when the window is hidden.
- Preserve in-progress requests safely when minimized.
- Prevent stacking-context and pointer-event conflicts.

Use existing tested drag/resize utilities when appropriate and compatible with the design system.

## 18. CLOUDFLARE AND SUPABASE INTEGRATION

The owner authorizes development and configuration of the Adigun BOT integration with the existing Cloudflare and Supabase infrastructure, subject to actual connector access, security controls and the approval boundaries below.

### Cloudflare

Where Cloudflare is part of the application architecture:

- Preserve the existing deployment architecture.
- Use appropriate server-side functions or Workers for AI requests where supported.
- Keep provider credentials server-side.
- Apply appropriate request validation and rate limiting.
- Preserve existing environment separation.
- Avoid exposing privileged credentials to browser code.
- Validate deployment compatibility before publishing.

### Supabase

Where Supabase is already used:

- Integrate authenticated user preferences.
- Apply Row Level Security.
- Use safe migrations.
- Maintain owner-scoped project data.
- Reuse existing authentication sessions.
- Validate permission boundaries.
- Avoid unnecessary database duplication.

### Authorization boundaries

Approval to develop and integrate these services does not authorize:

- Publishing credentials.
- Disabling authentication or security policies.
- Deleting production data.
- Unreviewed destructive migrations.
- Unapproved paid resource provisioning.
- Changing billing plans.
- Unrestricted production deployment.

Use the existing authorized project environments and report any required additional access.

## 19. REQUIRED TESTS

Implement automated tests where technically feasible, plus documented manual verification for interaction behavior.

### Window interaction tests

1. Open the BOT from its launcher.
2. Drag the window to another location.
3. Reload and verify restored position.
4. Resize the window.
5. Reload and verify restored dimensions.
6. Minimize and restore.
7. Maximize and restore.
8. Close and reopen.
9. Confirm no duplicate windows appear.
10. Confirm the underlying canvas remains interactive outside the BOT.

### Persistence tests

11. Guest preferences survive reload.
12. Authenticated preferences persist correctly.
13. One user's preferences cannot be accessed by another user.
14. Small viewport restoration clamps invalid desktop coordinates.
15. Offline preference synchronization fails gracefully.

### AI behavior tests

16. New suggestions do not force the window open.
17. Notification badges update correctly.
18. Sending a message reaches the actual configured AI backend.
19. AI errors are handled without breaking the window.
20. Consequential AI workspace actions require appropriate confirmation.
21. Minimizing preserves an active conversation.

### Accessibility tests

22. Keyboard-only open, navigate, minimize, close and reopen.
23. Accessible window movement and resizing.
24. Screen-reader labels and status announcements.
25. Correct focus restoration.
26. Reduced-motion behavior.

### Responsive tests

27. Desktop viewport.
28. Tablet viewport.
29. Mobile viewport.
30. Mobile keyboard and orientation changes.

### Regression tests

31. Existing canvas tools still work.
32. Existing project saving still works.
33. Existing AI tools still work.
34. No unintended layout overflow.
35. No critical browser-console errors.

Record actual test outcomes. Do not claim tests passed if they were not executed.

## 20. DOCUMENTATION

Update the product's `docs/HELP.md`.

Add a Table of Contents entry:

**Using the Adigun BOT Floating Window**

Document:

- How to open the BOT.
- How to drag the window.
- How to resize it.
- How to minimize.
- How to maximize.
- How to restore.
- How to close.
- How to reopen.
- How notifications work.
- How position and size are remembered.
- How mobile behavior differs.
- How to use keyboard controls.
- How to clear chat history.
- What happens when the AI service is unavailable.

Where supported, provide localized help content.

## 21. DELIVERABLES

The agent must deliver:

1. A reusable global floating Adigun BOT component.
2. Working drag-and-drop positioning.
3. Working resize controls.
4. Working minimize, maximize, restore and close actions.
5. Reliable launcher and unread-message behavior.
6. Local preference persistence.
7. Authenticated preference persistence where Supabase is configured.
8. Nonintrusive proactive AI notifications.
9. Existing functional AI chat and product-context integration.
10. Accessibility and mobile support.
11. Automated and documented manual tests.
12. Updated help documentation.
13. Integration instructions for other Hephzibah Behulah products.
14. A concise report of actual changes, tests and remaining limitations.

## 22. IMPLEMENTATION ORDER

Implement progressively:

**Phase 1 — Audit:** Inspect the existing BOT, product UI, design system and AI backend.

**Phase 2 — Shared component:** Implement the floating non-modal window and launcher.

**Phase 3 — Window management:** Add dragging, resizing, minimizing, maximizing, restoring and closing.

**Phase 4 — Persistence:** Add local preferences and authenticated Supabase synchronization where applicable.

**Phase 5 — AI integration:** Preserve existing conversations, tool calls, context and proactive suggestions.

**Phase 6 — Accessibility and responsive design:** Complete keyboard, screen-reader, touch and mobile behavior.

**Phase 7 — Verification:** Run functional, regression, security and accessibility tests.

**Phase 8 — Documentation and rollout:** Update help documentation, prepare integration guidance and deploy only through the authorized workflow.

Do not replace working functionality unnecessarily.

Do not claim completion based only on the visual appearance of the window.

## 23. FINAL AGENT DIRECTIVE

Implement the Adigun BOT as a reusable, production-oriented floating AI copilot across the Hephzibah Behulah ecosystem.

Preserve the existing AI capabilities.

Make the workspace interactive while the BOT is open.

Provide reliable window controls and state persistence.

Follow corporate branding and four-language requirements.

Integrate Cloudflare and Supabase securely where applicable.

Test actual behavior.

Use isolated Git branches and preserve existing work.

Report only verified results.

**Adigun BOT must behave like a professional floating engineering assistant, not a blocking chatbot modal or decorative AI button.**
