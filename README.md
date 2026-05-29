
# Super Small Grok Build Rules


**Lightweight Karpathy/Linux kernal/Hermes Hybrid**  

**For Small-Scale Experimental and Research Projects**

## What is this?

`AGENTS.md` is a lightweight set of coding rules that guides all AI-assisted coding, refactoring, planning, and development work in Grok Build—specifically designed for small-scale experimental and research projects.

## Why Use These Rules?

The Grok Build (Early Beta) already covered many of the core ideas from Andrej Karpathy’s LLM coding principles and Linux kernel development practices. Things like explicit reasoning, minimal viable changes, preserving existing code patterns, and maintaining strict backward compatibility are already built in.

What this `AGENTS.md` adds is the extra clarity and rules that often gets missed:

- A clear rule to always surface assumptions and uncertainties before making any change  
- A strict “let real errors show up” policy—no hiding problems behind broad `try/except` blocks, default fallbacks, or made-up data  
- Strong emphasis on never breaking existing user-facing behavior  
- The smallest possible change that solves the problem, while perfectly matching the current code style  
- Turning vague requests into concrete, testable goals  
- A simple, persistent project memory system (inspired by Hermes) using `PROJECT_PROGRESS.md` and an archive log

These additions make the rules especially useful for **small-scale experimental and research work**. You get:
- Better transparency and reproducibility  
- Easier debugging because root causes aren’t hidden  
- Smooth continuity across multiple sessions without drowning in chat history  
- Protection against over-engineering or unnecessary complexity that often creeps into exploratory projects

## Detailed Rules

The full, authoritative rules live in [`AGENTS.md`](AGENTS.md).


## How to Use

1. Place `AGENTS.md` in the root directory of your project.  
2. CD into this directory and start the Grok Build CLI, then it will be followed.
