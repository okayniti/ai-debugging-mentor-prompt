# AI Debugging Mentor Prompt (Python)

This repository contains a refined **system prompt** that turns an AI into a **non-revealing Python debugging mentor**, designed to build student skill through **hints, micro-experiments, and adaptive depth**.  

It enforces a strict **“hints-not-solutions”** rule, ensures a clear structure, and scales support from **beginner to advanced learners**.



##  Files

- **PROMPT.md** — The exact prompt to paste into the AI system/developer message.  
- **README.md** — Rationale, usage, and example interactions.



##  How to Use

1. Open your AI tool and **paste `PROMPT.md` into the system or developer message** so it governs all replies.  
2. Provide a **small buggy Python snippet** plus a one-line **“expected vs. actual”** description to reduce ambiguity and speed diagnosis.  
3. Keep iterations short:  
   - Answer the AI’s **1–2 diagnostic questions**  
   - Apply checks  
   - Re-run to converge on the root cause  


##  Prompt (PROMPT.md)

Paste the **Final Prompt** from this repo into a **system/developer message** for consistent behavior and structure.



## Example Interaction (Non-Revealing)

**Student Input**  
Code: A function that builds a frequency dict but returns wrong counts.  
Expected vs Actual: Expected counts per value; actual shows all keys mapped to the same number.


**AI Response**

Observation- 
It looks like your function is trying to count how many times each value appears. Right now, every key ends up with the same count, so the structure of the dictionary is correct but the counting logic is off.

Potential Issues- 
One possibility is that the same counter is being reused for every key. This often happens if a mutable default object is shared, or if an increment operation updates a single variable instead of per-key values.

## Guidance
Try:

- Printing id() of the dictionary across calls to see if it’s reused.

- Printing the dictionary after each loop iteration to check how counts evolve.

- Testing on very small inputs like [], [1], [1,1].

## Questions

- Is this function called multiple times within the same run?

- What do you see when you print the dictionary inside the loop?
