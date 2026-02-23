---
name: antigravity-dev-sop-en
description: An AI collaboration framework emphasizing "Strategy First" and "Self-Verification." Enforces environment variable isolation, Git context awareness, and iterative development of MVP features via an Agent Loop.
---

## Language & Documentation Preferences

* **Response Language**: All responses, explanations, and dialogues must be in **English**.
* **Code Comments**: All comments within the source code must be in **English**.
* **Documentation**: All generated files (e.g., README.md, technical docs) must be written in **English**.
* **Naming Conventions**: Follow standard programming conventions (camelCase, snake_case, etc.) using English for variables, functions, and classes.

## Engineering Standards

* **Integrity & Stability**:
When implementing or modifying a feature, **do not only verify the current change**. You must ensure that **existing functionalities remain intact** (preventing side effects or breaking legacy logic).
* If a modification affects shared modules, explicitly flag it and verify all dependent code.



## Git Workflow Standards

* **Context Awareness**:
* Before generating any commands that interact with remotes (e.g., `push`, `pull`, `fetch`), you **must** verify the current Git configuration.
* **No Guessing**: Never assume the remote is named `origin` or the branch is `main`/`master`. If uncertain, execute `git remote -v` and `git branch --show-current` first.


* **Commit & Release Control**:
* **No Early Commits**: Do not suggest `git add` or `git commit` until the code is fully refined and tested to avoid polluting the version history.
* **Pre-Push Verification**: Before suggesting a `push`, clearly state the target Remote and Branch, ensuring they exist based on previous checks.
* **Commit Messages**: Must list specific changes and functional descriptions in English.



## Security & Configuration

* **Credential Isolation**:
* Hardcoding sensitive information (e.g., API Keys, DB passwords, Secrets) is strictly prohibited.
* Mandatory use of Environment Variables or `.env` files for secret management.


* **Configurable Design**:
* Volatile parameters (e.g., PORT, DB Host, external URLs) should be defined as configurable variables rather than hardcoded in logic.



## Deployment & Ops

* **Process Management**:
* When designing backends or long-running scripts, prioritize configurations for process managers (e.g., PM2) rather than simple `node app.js` commands.
* Consider log management, auto-restart, and Cluster Mode support.


* **Standardized Scripts**:
* Clearly define standard `start`, `dev`, and `build` commands in `package.json` or project documentation.



## Solution Design Flow

* **Strategy Over Implementation**:
* For complex systems, **do not provide the final code immediately**.
* **Step 1**: Propose 2-3 technical architectures or implementation strategies with Pros/Cons analysis.
* **Step 2**: Suggest a "Minimum Viable Product (MVP)" and wait for confirmation before coding.


* **Self-Verification Loop**:
* Before outputting code, perform a "Simulated Execution":
1. Check if core requirements are met.
2. Verify compliance with security and configuration standards.
3. Validate integration logic (e.g., CORS, Port mapping).





## Exploration & Execution Flow (Agent Loop)

Follow these steps iteratively and **do not output full code blocks upfront**:

1. **Analyze & Strategize**:
* **Step 1**: Analyze mission goals and break down core MVP features.
* **Step 2**: Propose **2-3 feasible strategies** (e.g., Option A: Lightweight, Option B: Scalable/Feature-rich).
* **Step 3**: Suggest an MVP for user approval.


2. **Iterative Implementation**:
* **Self-Correction Loop**:
* After writing a feature, automatically verify if it works.
* If an error occurs: Read Log -> Analyze Cause -> Fix Code -> Re-verify.





## Agent Loop Rules

* **Environment First**: Always check for configuration files before requesting connection strings.
* **Max Iterations**: 20 cycles.

## Report Format (Per Round)

* **Current Phase**: (Analyzing / Designing / Implementing / Debugging)
* **Strategy/Architecture Confirmation**: (Briefly describe the current design direction)
* **Antigravity Check**: (Results of functional verification)
* **Next Step**:

## Completion Promise

Output `<promise>COMPLETE</promise>` only when:

1. MVP core features are verified and operational via Agent simulation.
2. All sensitive data is abstracted into configuration files.
