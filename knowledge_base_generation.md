> **System Role:** You are an Expert Technical Writer and Senior Software Engineer. Your task is to analyze the provided files and context to generate a highly accurate, dual-audience Knowledge Base (KB) for the **[Insert Screen Name]** screen.
> 
> **STRICT ANTI-HALLUCINATION RULES:**
> 1. Derive ALL information *exclusively* from the code, CSS, and context I have provided or have open. 
> 2. You are forbidden from guessing. If a requirement (like how a specific color is triggered) is not explicitly found in the provided code, output exactly: *"Information not found in the current context."*
> 3. You MUST cite the specific filename, class, or function name for every technical claim you make.
> 4. Keep the Business section simple and jargon-free (understandable by a beginner). Keep the Developer section highly technical.
> 
> **Output Structure:**
> 
> ### Part 1: Business User Knowledge Base
> *Plain English, simple analogies, non-technical.*
> *   **Basic Purpose:** What is the main goal of this screen?
> *   **Core Functionality:** What exactly does this screen calculate, forecast, or process? Explain the business rules.
> *   **Information Displayed:** Complete list of data points and metrics visible.
> *   **Visuals & Color Coding:** List every color used to convey meaning. Explain exactly what business condition triggers each color based on the styling code.
> *   **User Workflow:** Step-by-step plain-English breakdown of the user journey on this screen.
> 
> ### Part 2: Application Developer Knowledge Base
> *Highly technical, code-focused.*
> *   **Component Architecture:** Primary UI components and layout structures.
> *   **State & Data Flow:** API endpoints, queries, or state management stores feeding this screen.
> *   **Exact Logic & Algorithms:** Detail the specific calculations or data transformations. Cite the exact function names.
> *   **Conditional Rendering & Styling:** The exact programmatic conditions (variables, thresholds) triggering the UI state and color changes.
> *   **Workflow & Event Listeners:** Technical user journey (e.g., function calls on button clicks).

***

### How to Execute This in Your IDE for Maximum Accuracy

Since we can't lower the temperature, we have to meticulously control Copilot's *context window* (what it is "looking at" when it generates the answer). 

**In VS Code:**
1. **Clear the Chat:** Start a completely fresh chat session (`+` icon) so previous conversations don't bleed into the context.
2. **Target the Files:** Use Copilot's chat variables. At the top of your prompt, explicitly tag the files. For example: `Review #file:ForecastComponent.tsx, #file:forecastStyles.css, and #file:ForecastController.java.` 
3. **Alternatively, use `@workspace`:** If the logic is scattered, start the prompt with `@workspace`, but be warned that this searches the whole project and might pull in irrelevant data, slightly increasing the risk of hallucination compared to explicitly linking files.

**In IntelliJ:**
1. **Manage Open Tabs:** IntelliJ's Copilot relies heavily on what is currently visible and open. Close all tabs *except* the frontend component, the CSS/styling file, and the backend controller/service handling the logic for this specific screen.
2. **Use Context Menu:** You can highlight the specific block of forecasting logic in your editor, right-click, select **GitHub Copilot -> Copilot Chat**, and append the prompt above.

**The "CSS Trick" for Color Logic:**
Copilot will hallucinate color meanings if it can't see the CSS. Make absolutely sure your styling file (or the file where your conditional CSS classes are defined) is open or referenced. If it only sees `<div className={statusClass}>`, it will guess what the status colors are. If it sees the CSS, it will know for a fact.

Do you have the frontend code and the backend logic for this screen living in the same repository, or will you need to run this analysis across two different projects?
