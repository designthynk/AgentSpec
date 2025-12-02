# AgentSpec: Salesforce Agentforce Development Framework

AgentSpec is a specialized framework for building, testing, and managing Salesforce Agentforce agents, flows, and Lightning Web Components (LWCs). It leverages the OpenSpec CLI to provide a spec-driven development workflow tailored for the Salesforce ecosystem.

## Technology Stack
- **Core Framework**: OpenSpec (CLI)
- **Execution Engine**: Salesforce CLI (`sf`)
- **Intelligence Layer**: Model Context Protocol (MCP) via `@salesforce/mcp`
- **Platform**: Salesforce Agentforce (Agents, Flows, Apex, LWC)

## Project Structure
```
openspec/
├── project.md              # AgentSpec Project Definition
├── AGENTS.md               # Developer Instructions (Agentforce focus)
├── specs/                  # Specifications
│   ├── agentforce-lifecycle/ # Workflow for creating/managing agents
│   ├── salesforce-standards/ # Coding standards (Apex, LWC, etc.)
│   └── mcp-tooling/          # Available MCP tools and usage
└── changes/                # Active Change Proposals
```

## Conventions
- **MCP First**: Always prioritize MCP tools for context and guidance.
- **CLI Second**: Use `sf` CLI for execution and lifecycle management.
- **Metadata Discipline**: All changes must be tracked as Salesforce metadata.
- **Spec-Driven**: Define behavior in specs before implementation.

## Development Workflow
1. **Plan**: Create a Change Proposal in `changes/`.
2. **Spec**: Define requirements in `specs/`.
3. **Implement**: Use `sf` and MCP tools to build in the org.
4. **Verify**: Run tests and update specs.