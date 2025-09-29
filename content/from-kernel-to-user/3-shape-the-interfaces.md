+++
title = 'Shape the interfaces'
date = 2024-03-11T08:00:00+01:00
draft = false
+++

Previous: [Trace the stack](/from-kernel-to-user/2-trace-the-stack/)
Next: [Deliver to the user](/from-kernel-to-user/4-deliver-to-the-user/)

Interfaces are the treaties that keep each layer in sync.
Design them so every participant can speak succinctly and fail loudly when expectations drift.

Focus on a few guardrails:

- Keep contracts versioned and discoverable.
- Automate checks that assert the contract still holds.
- Offer observability hooks so callers learn how the system behaves in production.

Well-shaped interfaces give higher layers confidence to move fast without breaking the foundation.

