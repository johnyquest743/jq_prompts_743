Upgrading from Python 3.8 directly to 3.14 is a massive leap—you are bypassing six major versions of language changes, deprecations, and dependency shifts. Because these applications are business-critical and lack test coverage, the strategy must rely heavily on static analysis, automated syntax upgrades, and fail-safe, resumable scripting.

Here is the breakdown of the analysis you need to do, the best tools for the job, and the optimized prompt to feed into your LLM.

## 1. Pre-Migration Analysis (What you need to gather)

Before running the prompt below, gather these details to feed into the LLM. The more context the AI has, the less manual intervention you will need.

1. **Dependency Snapshots:** Grab the exact `requirements.txt` files from `repo1/submod` and `repo2`. The biggest hurdle will be third-party packages (like `cryptography` or `numpy`) that may have dropped 3.8 support or haven't added 3.14 support yet.
2. **OS specifics:** Identify the exact Linux distribution and version of your production server (e.g., RHEL 8, Ubuntu 22.04). Installing Python 3.14 without breaking the system's default Python requires specific OS-level commands.
3. **Integration Points:** For `repo1`, how does the Java application interact with the Python `submod`? (e.g., REST API, shell execution, shared database). The LLM needs to know this so it doesn't break the bridge between them.
4. **Smoke Test Candidates:** Since there are no unit tests, identify 2-3 critical endpoints, CLI commands, or functions you can execute to prove the application simply runs without crashing.

## 2. Best Tools for Automated Upgrades

Avoid doing this manually. The Python ecosystem has evolved significantly, and modern tooling can automate the bulk of this work.

* **Ruff (by Astral):** The current gold standard for Python code modernization. It replaces older tools like `pyupgrade`, `flake8`, and `black`. With a single command, Ruff can scan your codebase and automatically rewrite Python 3.8 syntax to modern standards (e.g., updating old `typing` imports, converting `format()` to f-strings).
* **uv (by Astral):** An incredibly fast Python package and environment manager. It is currently the best tool for installing Python 3.14 side-by-side on Linux and resolving complex dependency conflicts in milliseconds.
* **deptry:** A command-line tool that checks for obsolete, missing, or transitive dependencies in your project. It will help clean up your `requirements.txt` before the upgrade.
* **MonkeyType:** A tool by Instagram that runs your code and automatically generates type annotations based on runtime behavior. Adding types makes static analysis much more reliable since you don't have tests.

---

## 3. The Optimized Meta-Prompt

Copy and paste this exact prompt into your LLM (like Claude 3.5 Sonnet, GPT-4o, or Gemini 1.5 Pro). I have engineered it to generate resumable, idempotent scripts (meaning if the script fails halfway, you can run it again safely without corrupting the server) and to mitigate the lack of tests.

**[Copy everything below this line]**

 **Role:** You are a Senior DevOps Architect and Principal Python Engineer. You specialize in zero-downtime legacy migrations, idempotent automation, and CI/CD pipelines.
 **Task:** Engineer a fully automated, state-tracking migration pipeline to upgrade two critical repositories from Python 3.8 to 3.14.
 * `repo1`: Contains a Python submodule (`submod`) alongside Java submodules.
 * `repo2`: A standalone Python application.
 * Both use a Jules-based deployment pipeline that bundles `requirements.txt`.
 * Target environment: Production Linux server.
 
 
 **Critical Constraints & Failure Modes:**
 1. **No Test Coverage:** Because there are minimal/no tests, you must rely on static analysis (e.g., `ruff`, `mypy`) and generate automated "smoke tests" (dry-run imports) to validate the upgrade.
 2. **Resumability:** All Bash/Python deployment scripts must be strictly idempotent. Use state-tracking (e.g., checking for a `.migration_step_X.done` file) so that if the process is interrupted, running the script again resumes exactly where it left off without duplicating effort or breaking the system.
 3. **System Isolation:** The Linux server's system Python must remain untouched. Python 3.14 must be installed side-by-side using modern tools (like `uv` or isolated binaries) and symlinked securely for the applications.
 4. **Audit Trail:** Every change must be automatically logged to a `migration_audit.md` file.
 
 
 **Required Output Structure:**
 Please provide your solution in the following phases:
 **Phase 1: Codebase Modernization Strategy**
 Provide the exact CLI commands using **Ruff** (and its `pyupgrade` rules) to automatically parse and rewrite the 3.8 syntax in `repo1/submod` and `repo2` safely.
 **Phase 2: Dependency Resolution & Smoke Testing**
 Write a lightweight Python script that can be dropped into both repos to automatically import all modules listed in `requirements.txt` and flag any runtime crashes (acting as our synthetic test suite).
 **Phase 3: The Idempotent Server Upgrade Script**
 Generate the Bash script for the Linux server. It must:
 * Define variables for OS-level package managers.
 * Safely install Python 3.14 alongside the existing system Python.
 * Create isolated virtual environments for both repos.
 * Implement checkpointing (`if [ -f .step1 ]; then skip...`) so it is fully resumable.
 * Output a detailed log file of every action taken.
 
 
 **Inputs for Context:**
 * [Insert OS version here, e.g., Ubuntu 22.04]
 * [Insert repo1/submod requirements.txt here]
 * [Insert repo2 requirements.txt here]
 
 
 Ensure all scripts are production-ready, heavily commented, and prioritize safety over speed.

---
