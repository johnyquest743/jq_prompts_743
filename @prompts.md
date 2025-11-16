# Complete GitHub Copilot @ Prompts & Commands Reference

Based on the latest GitHub documentation, here's a comprehensive guide to all GitHub Copilot chat participants (@), slash commands (/), and chat variables (#) for software development and troubleshooting.

---

## **@ Chat Participants** (Domain Experts)

Chat participants act as specialized domain experts you can invoke by typing @ followed by the participant name.

### **Core Participants**

**@workspace** - Knows everything about the code in your currently open workspace
- Best for: Solution-wide queries, architectural questions, codebase understanding
- Examples:
  - `@workspace explain the authentication flow`
  - `@workspace where is the user validation logic?`
  - `@workspace find all API endpoints related to payments`
  - `@workspace how does error handling work across the project?`

**@terminal** - Knows all about the integrated terminal shell, its contents, and its buffer
- Best for: Shell commands, terminal errors, command explanations
- Examples:
  - `@terminal find the largest file in the src directory`
  - `@terminal #terminalLastCommand` - Explain the last command and any errors
  - `@terminal how do I recursively search for a string in all files?`
  - `@terminal explain this error message`

**@vscode** - Knows about the VS Code editor, its commands, and features
- Best for: VS Code settings, shortcuts, editor features
- Examples:
  - `@vscode how do I enable autosave?`
  - `@vscode show me keyboard shortcuts for refactoring`
  - `@vscode how to configure the minimap?`
  - `@vscode code preview in scrollbar` - Identifies editor.minimap settings

**@github** - Available in some environments
- Best for: GitHub-specific queries, repository management
- Examples:
  - `@github show my open issues`
  - `@github create a PR from this branch`

---

## **/ Slash Commands** (Quick Actions)

Slash commands are shortcuts to avoid writing complex prompts for common scenarios.

### **Code Generation & Modification**

**/fix** - Fix errors in the active file or selected code
- Examples:
  - `/fix` - Fix error in current file
  - `/fix optimize memory usage`
  - `/fix improve performance`

**/new** - Create new projects or files
- Examples:
  - `/new React component with TypeScript`
  - `/new Express REST API`
  - `/new Python data processing script`

**/newNotebook** - Generate a new Jupyter notebook
- Example:
  - `/newNotebook data analysis with pandas`

### **Testing**

**/tests** - Write tests for the active file or selected code
- Examples:
  - `/tests` - Generate tests for current file
  - `/tests for the authentication module`
  - `/tests using Jest and React Testing Library`

### **Documentation & Understanding**

**/explain** - Explain selected code or concepts
- Examples:
  - `/explain` - Explain selected code
  - `/explain the decorator pattern in this class`
  - `/explain #file:config.yaml`

**/doc** - Generate documentation
- Examples:
  - `/doc` - Document current function/class
  - `/doc generate JSDoc comments`

### **Code Review & Analysis**

**/review** - Review code for improvements
- Examples:
  - `/review` - Review current file
  - `/review security vulnerabilities`
  - `/review performance bottlenecks`

### **Search & Navigation**

**/search** - Search within workspace or codebase
- Examples:
  - `/search where is JWT validation implemented?`
  - `/search all database queries`

### **Utility Commands**

**/clear** - Clear chat history
**/help** - Show available commands

---

## **# Chat Variables** (Context References)

Chat variables allow you to include specific context in your prompt using # followed by the variable name.

### **File & Code Context**

**#file** - Points to a specific file in your workspace
- Examples:
  - `#file:src/auth.js explain the login function`
  - `#file:package.json what dependencies are outdated?`
  - `Refactor #file:utils/helpers.ts to use arrow functions`

**#selection** - The visible source code in the active editor
- Example:
  - `Optimize #selection for better performance`

**#editor** - Source code in the editor's viewport (visible part)
- Example:
  - `Review #editor for security issues`

**#codebase** - All content of the open workspace, similar to @workspace but can be used with other participants
- Examples:
  - `@terminal #codebase find all TODO comments`
  - `Add unit tests consistent with #codebase patterns`
  - `#codebase where is the payment processing logic?`

### **Repository & Version Control**

**#git** - Current git repository: branch, remotes, path, etc.
- Examples:
  - `#git show recent changes`
  - `What files changed in #git?`

**#githubRepo** - Search and reference GitHub repositories
- Examples:
  - `#githubRepo:microsoft/vscode how do they implement extensions?`
  - `Show examples from #githubRepo:facebook/react`

### **Terminal Context**

**#terminalLastCommand** - The active terminal's last run command
- Example:
  - `@terminal #terminalLastCommand explain what this does`

**#terminalSelection** - The active terminal's selection

### **Web & External Content**

**#fetch** - Retrieve content from web pages
- Examples:
  - `#fetch https://code.visualstudio.com/updates/v1_100 What are the highlights?`
  - `Update to .NET 9 based on #fetch https://learn.microsoft.com/aspnet/core/migration/80-90`

---

## **Powerful Combination Patterns**

### **Deep Code Analysis**
```
@workspace #codebase analyze the complete data flow from API to database
```

### **Contextual Bug Fixing**
```
/fix #file:src/components/UserProfile.tsx using patterns from #codebase
```

### **Test Generation with Context**
```
/tests #selection consistent with testing patterns in #codebase
```

### **Terminal + Codebase**
```
@terminal #codebase find all files modified in the last 24 hours
```

### **Multi-File Refactoring**
```
@workspace refactor authentication to use JWT tokens across 
#file:auth.js #file:middleware.js #file:routes.js
```

### **Documentation with External Reference**
```
/doc #selection following conventions from #fetch https://jsdoc.app/
```

### **Security Review**
```
@workspace #codebase review for SQL injection vulnerabilities
```

---

## **Advanced Troubleshooting Patterns**

### **1. Error Analysis Flow**
```
Step 1: @terminal #terminalLastCommand
Step 2: @workspace find where this error originates
Step 3: /fix with error handling best practices from #codebase
```

### **2. Performance Investigation**
```
Step 1: @workspace #codebase identify performance bottlenecks
Step 2: /review #file:slowComponent.tsx
Step 3: Optimize based on patterns in #codebase
```

### **3. Integration Debugging**
```
Step 1: @workspace trace the API call from #file:frontend.js to #file:backend.js
Step 2: /explain the data transformation in between
Step 3: /fix any data mismatches
```

### **4. Dependency Issues**
```
Step 1: @terminal #terminalLastCommand
Step 2: #file:package.json what's causing this conflict?
Step 3: @vscode how to update dependencies safely?
```

---

## **Pro Tips for Maximum Productivity**

**Keyboard Shortcuts:**
- Use Ctrl+Enter (Cmd+Enter) to automatically insert @workspace before sending
- Use arrow keys to navigate through suggestions after typing `/`, `@`, or `#`

**Context Specificity:**
- Use `@workspace` for broad codebase questions
- Use `#codebase` when combining with other participants or tools
- Use `#file` when you need specific file context

**Iterative Refinement:**
```
First: @workspace what does this module do?
Then: /explain #file:specificFile.js in detail
Finally: /fix with improvements suggested
```

**Testing Workflow:**
```
1. /tests #selection
2. Review generated tests
3. @workspace are these tests consistent with our testing strategy?
4. Refine based on #codebase patterns
```

**Multi-Step Problem Solving:**
```
@workspace #codebase
I'm getting [error]. Please:
1. Locate where this error is thrown
2. Explain why it's happening
3. Suggest a fix consistent with our error handling patterns
4. Generate tests for the fix
```

---

## **JetBrains IDE Difference**

If you're using a JetBrains IDE, use @project rather than @workspace.

---

## **Key Takeaways**

1. **@ Participants** = Domain experts (workspace, terminal, vscode, github)
2. **/ Commands** = Quick actions (fix, tests, explain, new, review)
3. **# Variables** = Context references (file, selection, codebase, git, terminal)

**Best Practice:** Combine all three for powerful queries:
```
@workspace /fix #file:auth.js using patterns from #codebase
```

This gives you expert knowledge (@workspace) + specific action (/fix) + targeted context (#file) + broader patterns (#codebase) all in one prompt!
