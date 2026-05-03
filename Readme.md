# GitHub Copilot Agents Repository

A centralized hub for GitHub Copilot agent configurations, instructions, skills, and workflows designed to enable structured AI-assisted development across projects.

## Table of Contents

- [What Is This Repository?](#what-is-this-repository)
- [Setup Instructions](#setup-instructions)
- [Repository Structure](#repository-structure)
- [Agents Overview](#agents-overview)
- [How to Use](#how-to-use)
- [Key Concepts](#key-concepts)

## What Is This Repository?

This is a **nested git repository** that lives inside your project's `.github/` folder. It provides:

- **Custom Agents**: Specialized AI personas with defined roles, skills, and boundaries
- **Instructions**: Global project rules and domain-specific guidelines
- **Skills**: Reusable knowledge packages for documentation, architecture, and development tasks
- **Workflows**: Structured processes for planning and implementation

The separation allows you to:
- Version control AI automation independently from project code
- Reuse consistent agent configurations across multiple projects
- Update agent behaviors without affecting your main repository

## Setup Instructions

### Initial Setup

1. **Add `.github/` to `.gitignore`** in your main project (prevents nested git conflicts):
   ```
   # In your project root .gitignore
   .github/
   ```

2. **Clone this repository into your project's `.github` folder**:
   ```bash
   cd your-project-root
   cd .github
   git clone <this-repo-url> .
   ```

3. **Result**: You now have two separate git repositories:
   - Main project repo: `your-project-root/.git/`
   - Agents repo: `your-project-root/.github/.git/`

Both can be version controlled independently.

## Repository Structure

```
.github/
├── copilot-instructions.md      # Global rules & constraints for all agents
├── Agents/                       # Agent configuration files
│   ├── Architect.agent.md       # System architecture & design decisions
│   ├── LeadDeveloper.agent.md   # Cross-functional feature coordination
│   ├── NetDeveloper.agent.md    # .NET backend implementation
│   ├── NodeJsDeveloper.agent.md # Node.js/Electron backend
│   ├── ReactDeveloper.agent.md  # React frontend implementation
│   ├── ProductOwner.agent.md    # Product requirements & features
│   ├── UIDesigner.agent.md      # UI design & prototypes
│   ├── Librarian.agent.md       # Project wiki & documentation
│   └── Manager.agent.md         # Team coordination
├── instructions/                 # Domain-specific guidelines
│   ├── DocumentationStructure.instruction.md
│   └── ResponsibilityMatrix.instruction.md
├── skills/                       # Reusable knowledge packages
│   ├── backend-architecture/
│   ├── data-models/
│   ├── features-and-userstories/
│   ├── frontend-architecture/
│   ├── git-wiki/
│   ├── high-level-architecture/
│   └── ui-design/
└── workflows/                    # Process workflows (deprecated; moved to skills)
```

## Agents Overview

### 🏗️ **Architect** (`Architect.agent.md`)
**Use when**: Defining or refining system architecture, data models, and technical decisions.

**Responsibilities**:
- Design system boundaries and integration patterns
- Create architecture documentation and diagrams
- Make trade-offs explicit and document decisions
- Align architecture with product goals and UI direction

**Key Skills**: high-level-architecture, backend-architecture, frontend-architecture, data-models

---

### 👨‍💼 **LeadDeveloper** (`LeadDeveloper.agent.md`)
**Use when**: Coordinating end-to-end feature implementation across backend and frontend.

**Responsibilities**:
- Break features into backend and frontend tasks
- Delegate to specialized developers
- Verify consistency between components
- Orchestrate implementation without pausing between steps

**Delegations**: NodeJsDeveloper, ReactDeveloper

---

### ⚙️ **NetDeveloper** (`NetDeveloper.agent.md`)
**Use when**: Building or updating .NET 10 backend, HTTP APIs, and database persistence.

**Responsibilities**:
- Implement controllers, services, and data access layer
- Design API contracts and DTOs
- Manage Entity Framework migrations
- Follow clean architecture principles

**Tech Stack**: .NET 10, Entity Framework Core, Minimal APIs / MVC Controllers

---

### 🖥️ **NodeJsDeveloper** (`NodeJsDeveloper.agent.md`)
**Use when**: Implementing Node.js/Electron backend, IPC handlers, and local database integration.

**Responsibilities**:
- Implement Electron main process and IPC communication
- Build Node.js services and business logic
- Manage SQLite database for local persistence
- Coordinate with React frontend over IPC

**Tech Stack**: Electron, Node.js, TypeScript, SQLite

---

### ⚛️ **ReactDeveloper** (`ReactDeveloper.agent.md`)
**Use when**: Creating or updating React components, hooks, routing, and frontend UI.

**Responsibilities**:
- Build reusable, typed React components
- Implement responsive layouts matching UI specs
- Connect to backend via IPC or HTTP APIs
- Handle loading, error, empty, and success states

**Tech Stack**: React, TypeScript, React Router, React Context

**Key Rules**:
- Keep components under 200 lines
- No props objects with >5 properties
- All components must be typed (no `any`)
- Define styles using `const styles` objects

---

### 📦 **ProductOwner** (`ProductOwner.agent.md`)
**Use when**: Defining features, refining requirements, or maintaining the product backlog.

**Responsibilities**:
- Write user stories and acceptance criteria
- Maintain feature documentation
- Clarify scope and product intent
- Prioritize backlog items

**Key Skills**: features-and-userstories

---

### 🎨 **UIDesigner** (`UIDesigner.agent.md`)
**Use when**: Designing UI specifications and creating HTML prototypes for screens/flows.

**Responsibilities**:
- Create paired `.md` specifications and `.html` prototypes
- Apply design system tokens consistently
- Document component states and interactions
- Ensure accessibility and usability

**Deliverables**: `UI-<id>-<name>.md` + `UI-<id>-<name>.html`

---

### 📚 **Librarian** (`Librarian.agent.md`)
**Use when**: Querying project knowledge, maintaining wiki consistency, or updating documentation.

**Responsibilities**:
- Build and maintain `.wiki/` project knowledge base
- Query codebase facts and architecture
- Lint wiki for consistency and completeness
- Ingest code changes into documentation

---

## How to Use

### In VS Code with GitHub Copilot Chat

#### 1. **Invoke an Agent**
Use the `@` symbol to mention a specific agent:

```
@NetDeveloper Implement the user authentication endpoint according to FE-002
```

VS Code will route your request to the specified agent with all its role definitions, rules, and skills.

#### 2. **Ask a General Question** (No Agent)
Let the default agent handle it:

```
What does the Architect agent do?
```

#### 3. **Use Inline References**
Include documentation links for context:

```
@ReactDeveloper Build the Browse Workspace screen according to UI-001 and FE-001 specifications
```

### Common Workflows

#### **End-to-End Feature Implementation**
```
@LeadDeveloper Implement user story US-003 (Register Owned Model) with backend API and React UI
```

This agent will:
1. Break it into backend and frontend tasks
2. Delegate to NodeJsDeveloper and ReactDeveloper
3. Verify consistency
4. Return a working implementation

#### **Design a New Screen**
```
@UIDesigner Design the model detail view screen for FE-003 showing title, photos, notes, and rating
```

Expect:
- `UI-<id>-model-detail-view.md` (specification)
- `UI-<id>-model-detail-view.html` (interactive prototype)

#### **Define an Architecture**
```
@Architect Design the authentication and session management flow for the desktop app
```

Expect:
- Architecture documentation with trade-offs
- Data model implications
- Integration points with UI and backend

#### **Query Project Knowledge**
```
@Librarian How does the collection hierarchy work? Show me the data model and related backend services.
```

Expect:
- Links to documentation and code
- Explanation of design patterns
- Offer to update wiki if gaps exist

## Key Concepts

### **Agents vs. Roles**
- **Agents** are AI personas with specific expertise, boundaries, and workflows
- **Roles** are team responsibilities (e.g., "backend developer", "product manager")
- Each agent mimics a role and enforces its constraints and best practices

### **Skills**
Reusable knowledge packages that agents use:
- `high-level-architecture` - System design and decision documentation
- `backend-architecture` - Service boundaries and integration patterns
- `data-models` - Entity relationships and persistence design
- `frontend-architecture` - Component hierarchy and routing
- `features-and-userstories` - Product specification templates
- `ui-design` - Design system tokens and UI specifications
- `git-wiki` - Project knowledge base management

### **Global Rules** (`copilot-instructions.md`)
Universal constraints that apply to all agents:
- **Documentation Stability**: Do not modify requirements/architecture without explicit permission (Architect/ProductOwner only)
- **API Contracts**: Backend and frontend contracts are immutable unless coordinated
- **Minimal Changes**: Keep modifications focused and coherent
- **Configuration**: No hardcoded secrets or environment values

### **Delegation Pattern**
Agents coordinate work by delegating to specialists:
- **LeadDeveloper** → delegates to NetDeveloper + ReactDeveloper
- **ProductOwner** → hands off to Architect or Implementation agents
- **Architect** → provides blueprint for developers

## Best Practices

1. **Be Specific**: Provide agent name and clear context
   ```
   @ReactDeveloper ✅ (clear target)
   Update the React code ❌ (ambiguous)
   ```

2. **Reference Documentation**: Link to specs and requirements
   ```
   @ReactDeveloper Implement the Browse Workspace screen per UI-001 and FE-001
   ```

3. **Use LeadDeveloper for Features**: Let the orchestrator handle cross-functional work
   ```
   @LeadDeveloper Implement US-006 (Manage Model Photos)
   ```

4. **Escalate Conflicts**: If an agent hits a boundary, ask for clarification or escalate
   ```
   @Architect Should we store photos in the database or as local files?
   ```

5. **Keep Wiki Updated**: Use Librarian to stay informed
   ```
   @Librarian Update the wiki with the new authentication flow
   ```

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Agent ignores my request | Check if request conflicts with agent boundaries; try a different agent |
| Multiple agents needed | Use `@LeadDeveloper` to coordinate across them |
| Documentation seems stale | Ask `@Librarian` to lint and update the wiki |
| Unclear requirements | Ask `@ProductOwner` to clarify scope and acceptance criteria |

## Contributing

To improve this repository:
1. Create a branch in the agents repo
2. Update agent files, skills, or instructions
3. Test changes in a project
4. Create a pull request

---

**Questions?** Ask `@Librarian` how something works, or refer to individual agent `.md` files for detailed role definitions.

# TODO
- The Planing Agnest should ask questions. right now they have thew asq tool, but it is not used. I think it's because it is not configured

- the system specific sections in the develeoper agents should be configured differently. I need to work on this

- UI designs should be reworked a bit, to be more distinctive
   - Antracite is totaly off, the whole design has to be redone from scratch
   - Aurora need soem furter definition
   - green white as well
   - I belive I need a fourth style to have 2 dark, and 2 light themed styles

- LLM wiki building should be introduced into the whole thing, right now it's a RAG system, every agent reviews the required documentation on every request.

- the Lead developer agent should query the wiki, and complie all the necessaray knowledge pieces, befor starting implementation. this way his sub agents, should have all the information neede to their work.
