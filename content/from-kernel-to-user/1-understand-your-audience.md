+++
title = 'Understand your audience'
date = 2024-03-09T23:41:00+01:00
draft = false
+++

Previous: [Overview](/from-kernel-to-user/0-overview/)
Next: [Trace the stack](/from-kernel-to-user/2-trace-the-stack/)

Every layer of the stack hears a different accent.
Browsers expect carefully structured markup, APIs listen for predictable payloads, kernels wait for syscalls that respect their contracts.

Map the actors you depend on, then tailor your message for each one:

- What inputs do they accept, and in what shape?
- Which constraints, quotas, or timing guarantees do they enforce?
- How do they report success, failure, or back pressure?

Clarity starts with empathy for whoever—or whatever—is on the other side of the message.

