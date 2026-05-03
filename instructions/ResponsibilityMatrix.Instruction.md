---
description: "Defines role boundaries and ownership for all custom agents in this repository."
applyTo: "**"
---

# Agent Responsibility Matrix

Use this matrix to keep delegation consistent and avoid role overlap.

| Agent Name | Allowed File Zones | Forbidden Zones | Skills |
| --- | --- | --- | --- |
| Manager | `.github/workflows/**`, `Documentations/Features/**`, `Documentations/UI/**`, `Documentations/Architecture/**` (orchestration and consistency only) | `3DInventory-app/**` implementation code | `features-and-userstories`, `ui-design`, `high-level-architecture`, `data-models` |
| ProductOwner | `Documentations/Features/**` and product-planning markdown artifacts | `3DInventory-app/**`, backend/frontend implementation files | `features-and-userstories` |
| UIDesigner | `Documentations/UI/**` (UI specifications and HTML prototypes) | `3DInventory-app/**`, backend code, data model code | `ui-design` |
| Architect | `Documentations/Architecture/**` and architecture diagrams/docs | `3DInventory-app/**` feature implementation code | `high-level-architecture`, `backend-architecture`, `frontend-architecture`, `data-models` |
| LeadDeveloper | `3DInventory-app/src/main/**`, `3DInventory-app/src/preload/**`, `3DInventory-app/src/renderer/**` through delegation/orchestration | Product planning ownership docs (`Documentations/Features/**`) and UI specification ownership docs (`Documentations/UI/**`) unless explicitly requested | `backend-architecture`, `frontend-architecture` |
| NodeJsDeveloper | `3DInventory-app/src/main/**`, `3DInventory-app/src/preload/**`, Node/Electron backend modules and local persistence integration | `Documentations/Features/**`, `Documentations/UI/**`, architecture ownership docs | `backend-architecture` |
| ReactDeveloper | `3DInventory-app/src/renderer/**` (React UI implementation) | `3DInventory-app/src/main/**`, product/architecture ownership docs | `frontend-architecture` |
| Librarian | `.wiki/**` and wiki support artifacts | Application implementation code and source-of-truth product/architecture docs unless explicitly requested | `git-wiki` |
| NetDeveloper | .NET backend zones only when such project exists in the workspace (for example `src/**/*.cs`, `**/*.csproj`, API projects) | Electron/Node backend code and React renderer code in this project | `backend-architecture` |

## Additional Guardrails

- Manager is planning-only orchestration.
- ProductOwner owns features and user stories.
- UIDesigner owns UI documentation and prototypes.
- Architect owns architecture and data model documentation.
- LeadDeveloper owns implementation orchestration.
- NodeJsDeveloper owns Electron/Node backend implementation.
- ReactDeveloper owns renderer/frontend implementation.
- Librarian owns wiki maintenance.
- NetDeveloper is optional and should be used only when a .NET backend exists in the target workspace.
