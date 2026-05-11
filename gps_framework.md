The **GPS framework** (Gaslight, Push back, Stress test) outlined by Vaibhav Sisinty in that video is an incredible way to force LLMs out of their "polite, default" mode and into delivering expert-level, highly nuanced advice.

Applying this framework to a complex technical task like upgrading Spring Boot is a fantastic idea because standard LLM answers for upgrades usually just spit out the official Spring Boot migration guide, which lacks real-world, battle-tested insights.

Here is how you can apply the exact GPS framework to your Spring Boot upgrade task.

### The Baseline (What NOT to ask)

*“I need to upgrade Spring Boot for my applications. What are the steps?”* (This will give you a generic, unhelpful checklist).

---

### Step 1: (G) Gaslight — Raise the Emotional Stakes

You aren't lying to the AI; you are establishing high stakes so it stops giving you safe, people-pleasing answers and switches to a hyper-critical, expert persona.

**Your Initial Prompt:**

> *"I am a Lead Enterprise Architect overseeing a mission-critical suite of microservices. We need to upgrade our applications from Spring Boot 2.x to 3.x (and Java 17/21). If this upgrade causes downtime, performance degradation, or data corruption in production, my company loses millions, and heads will roll. I have zero patience for generic fluff from migration guides. Walk me through the upgrade strategy the way you would present it to a deeply skeptical, highly technical CTO. Focus heavily on the exact breaking changes (like Jakarta EE namespace shifts, Hibernate 6 changes, and security config rewrites) that cause real-world outages."*

### Step 2: (P) Push Back — Challenge the Output

Once the AI gives you its initial architecture plan, it will likely still be a bit too neat and tidy. You need to push back hard to extract the hidden, non-obvious issues.

**Your Follow-Up Prompt:**

> *"This is a standard upgrade path that I could have just read in the official Spring documentation. I need real-world insight. Give me the perspective of a Senior Developer who recently botched a Spring Boot 3 migration. What are the 'silent killers'? What are the non-obvious runtime issues, dependency conflicts, or memory leaks that compile perfectly fine but explode in production?"*

### Step 3: (S) Stress Test — The 3-Step Refinement

As mentioned in the video, don't just accept the revised plan. Put it through the 90-second stress test.

**Test 1: The Gap Check**

> *"Before I begin executing this migration plan, look at my original prompt and your current plan together. What are the gaps? What critical details about my infrastructure, database layer, external dependencies, or CI/CD pipeline should I have told you so that you could give me a truly bulletproof upgrade strategy?"*
> *(The AI will now ask you about your specific tech stack. Answer it with details like what database you use, if you use Kafka/RabbitMQ, what cloud provider you are on, etc.)*

**Test 2: The Bias Sweep**

> *"Now reverify your updated migration plan. Specifically, check for confirmation bias or survivorship bias. Are you only modeling this advice based on 'happy path' successful migrations? What are the edge cases where companies tried to upgrade to Spring Boot 3 and had to completely revert due to catastrophic issues?"*

**Test 3: Injecting Stakes (The Final Polish)**

> *"If I follow this exact rollout and deployment strategy, and an unforeseen backward-compatibility issue breaks our API contracts, rolling back the database and application versions will cause a 4-hour system-wide outage. Given those severe consequences, what specific steps in your deployment strategy would you change, soften, or add strict warnings/fallback plans to?"*

### Why this works for Software Engineering:

By using this exact sequence, the AI will stop telling you to simply "update your `pom.xml` and run tests." Instead, it will start advising you on advanced strategies like:

* Setting up parallel staging environments to run shadow traffic against the new Spring Boot instances.
* Writing specific integration tests for the `javax` to `jakarta` package namespace migrations.
* Gradual rollout strategies to catch Spring Security filter chain regressions before they hit 100% of your users.


***************************************************************************************************************************************************************************************************************
***************************************************************************************************************************************************************************************************************

Building an automated, agent-like framework inside your IDE using Copilot to handle a massive upgrade like Spring Boot 2 to 3 is the holy grail of platform engineering.

To achieve this, you need to force Copilot out of its standard "code completion" mindset and into the mindset of a **Platform Tooling Architect**. Standard Copilot will just want to give you regex commands or bash scripts, which are far too brittle for a framework of this scale.

Here is how you use the GPS framework inside GitHub Copilot Chat (using the `@workspace` command) to build this automated upgrade engine.

### Step 1: (G) Gaslight — Establish the Persona and High Stakes

You need to explicitly tell Copilot that this is not a one-off task, but the creation of a permanent, deterministic automation framework.

**Copy and paste this into Copilot Chat:**

> *"Act as a Principal Platform Engineer and Tooling Architect. I am tasked with building a highly automated, agentic framework inside this IDE to handle Spring Boot 2.x to 3.x and Java 17+ migrations across dozens of repositories. If this framework relies on brittle search-and-replace, hallucinates code, or requires heavy manual intervention per repository, the project will fail and cause massive regressions. I need you to design the architecture for this internal tool/workflow. How do we combine AST-based migration tools (like OpenRewrite) with highly constrained, step-by-step Copilot prompts to guarantee a deterministic, error-free migration? Give me the exact blueprint."*

### Step 2: (P) Push Back — Challenge the Brittle Parts

Copilot will likely give you a decent blueprint involving running OpenRewrite first, and then using Copilot for the leftovers. But it will probably be too vague on *how* to actually chain these together agentically. You must push back on the human element.

**Your Follow-Up Prompt:**

> *"This blueprint still requires too much human decision-making. I want to build this so a Junior Developer can trigger it with near-zero contextual knowledge. Your current plan leaves the most dangerous refactors (like migrating deprecated `WebSecurityConfigurerAdapter` or custom Hibernate 6 dialects) to manual Copilot prompting. Push deeper. Give me the exact, hyper-specific Copilot prompts (using `#file` and `@workspace` context) that I need to save into my team's framework to safely automate the Security and JPA layers without hallucination."*

### Step 3: (S) Stress Test — The 3-Step Refinement

Now that Copilot has given you the architecture and the specific IDE prompts for your framework, put the framework itself through the 90-second stress test.

**Test 1: The Gap Check**

> *"Before we finalize this migration framework, look at the architecture and prompts you just generated. What are the blind spots? What specific types of internal corporate libraries, transitively vulnerable dependencies, or custom configurations will this automated pipeline completely fail to upgrade, causing silent runtime errors?"*

**Test 2: The Bias Sweep**

> *"Now run a bias sweep on this framework. Are you optimizing this workflow only for standard, REST-based microservices? How does this automation completely break down if the target repository is heavily reliant on older messaging queues (like outdated Kafka/RabbitMQ binders) or legacy batch processing jobs? Adjust the framework to account for these architectural variations."*

**Test 3: Injecting Stakes (The Final Polish)**

> *"If I deploy this Copilot-driven workflow to my team tomorrow, and it successfully compiles a microservice, but silently drops data during database serialization because of a missed Jackson or Hibernate 6 change, it will corrupt production data. Given that catastrophic consequence, what specific automated validation steps, custom test-generation prompts, or CI/CD safety nets MUST be injected into this framework before we consider an upgrade 'complete'?"*

---

### Pro-Tip for Execution in VS Code / IntelliJ

Since you are looking to build this as a reusable skill or agent, consider taking the outputs from these prompts and turning them into a **Custom VS Code Extension** or integrating them into **Copilot Custom Instructions**.

Instead of having developers type out complex prompts, you can take the hyper-refined prompts generated by this GPS exercise and bind them to a single IDE command (e.g., `/runSpringBootMigrationAgent`), ensuring the constraints and guardrails are applied identically every single time.
