AI Debugging Mentor Prompt (Python)
This repository contains a refined system prompt that turns an AI into a non‑revealing Python debugging mentor, designed to build student skill through hints, micro‑experiments, and adaptive depth. It enforces “hints-not-solutions,” ensures a clear structure, and scales from beginner to advanced learners.

Files
PROMPT.md — The exact prompt to paste into the AI system/developer message.

README.md — Rationale, usage, and example interactions.

How to use
Open the AI tool and paste PROMPT.md into the system or developer message so it governs all replies.

Provide a small buggy Python snippet plus a one-line “expected vs. actual” description to reduce ambiguity and speed diagnosis.

Keep iterations short: answer the bot’s 1–2 diagnostic questions, apply checks, and re‑run to converge on the root cause.

Prompt (PROMPT.md)
Paste the “Final Prompt” from this repo into a system/developer message for consistent behavior and structure.

Example interaction (non-revealing)
Student input:

Code: A function that builds a frequency dict but returns wrong counts.

Expected vs Actual: Expected counts per value; actual shows all keys mapped to the same number.

AI (Observation):

Summarizes intent and current behavior in plain language, acknowledging partial correctness.

AI (Potential Issues):

Points to use of a single mutable default dict reused across calls, or incrementing a shared counter rather than per-key updates, explaining the likely mechanism.

AI (Guidance):

Suggests printing id() of the dict across calls, adding an assertion on per-key increments, and testing with inputs like [], , and to isolate state/mutation issues—without writing any code changes.

AI (Questions):

“Is this function called multiple times within the same run?”

“What does printing the dict after each loop iteration show?”.

Design choices
Structured triad response keeps feedback focused and scannable, mirroring expert debugging workflows and reducing hallucinations.

Strict “no patches” rule enforces incremental hinting and student agency consistent with tutoring best practices.

Adaptive depth directive helps different learners: fundamentals for novices; deeper software-engineering concerns for advanced students.

Clarity-first constraints improve output reliability: role specification, explicit format, prioritization rule, concise tone.
