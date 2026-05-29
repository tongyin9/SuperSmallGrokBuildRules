
# Super Small Grok Build Rules


**Lightweight rule set from Karpathy/Linux kernal/Hermes Hybrid**  

**For Small-Scale Experimental and Research Projects**

## What is this?

`AGENTS.md` is a set of lightweight coding rules used in Grok Build (beta) for small-scale experimental and research-aim projects. 

## Why Use These Rules?

The Grok Build (Early Beta) already covered many of the core ideas from Andrej Karpathy’s LLM coding principles [https://github.com/multica-ai/andrej-karpathy-skills/blob/main/skills/karpathy-guidelines] and Linux kernel development practices, like "smallest change" philosophy, avoiding adding unrequested features or speculative abstractions.

What this rule set `AGENTS.md` adds is the extra clarity and rules that often get missed but are specifically needed for experimental projects:

- A clear rule to always surface assumptions and uncertainties before making any change  
- A strict “let real errors show up” policy—no hiding problems behind broad `try/except` blocks, default fallbacks, or made-up data  
- Strong emphasis on never breaking existing user-facing behavior  
- The smallest possible change that solves the problem, while perfectly matching the current code style  
- Turning vague requests into concrete, testable goals  
- A simple, persistent project memory system (inspired by Hermes) using `PROJECT_PROGRESS.md` and an archive log

These additions make the rules especially useful for **small-scale experimental and research work**. You get:
- *Better transparency and reproducibility*
- *Easier debugging because root causes aren’t hidden*  
- *Smooth continuity across multiple sessions without drowning in chat history*  
- *Protection against over-engineering or unnecessary complexity that often creeps into exploratory projects*

## Detailed Rules

The full, authoritative rules live in [`AGENTS.md`](AGENTS.md).


## How to Use

1. Place `AGENTS.md` in the root directory of your project.  
2. CD into this directory and start the Grok Build CLI, then it will be followed.
