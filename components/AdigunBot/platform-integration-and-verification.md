# Global Adigun BOT — Floating AI Copilot Component Standard

**Standard ID:** HB-UI-ADIGUNBOT-001  
**Version:** 1.1  
**Scope:** Reusable Adigun BOT component requirements for Hephzibah Behulah products.  
**Status:** Mandatory design-system component standard.

The global AI-agent policy in [hb-AI-policy](https://github.com/HephzibahBehulahHQ/hb-AI-policy) governs agent operation, security and approvals. These documents govern the reusable component and product-integration contract.


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
