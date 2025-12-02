<p align="center">
  <picture>
    <source srcset="assets/openspec_pixel_dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset="assets/openspec_pixel_light.svg" media="(prefers-color-scheme: light)">
    <img src="assets/openspec_pixel_light.svg" alt="AgentSpec logo" height="64">
  </picture>
</p>

# AgentSpec: Salesforce Agentforce Development Framework

AgentSpec is a specialized framework for building, testing, and managing Salesforce Agentforce agents, flows, and Lightning Web Components (LWCs). It leverages the OpenSpec CLI to provide a spec-driven development workflow tailored for the Salesforce ecosystem.

## Why AgentSpec?

Building Agentforce agents requires coordinating multiple metadata types (Agents, Flows, Apex, LWC) and adhering to strict platform rules. AgentSpec provides a structured workflow to ensure:
- **Agreement before Implementation**: Define agent behavior in specs before writing code.
- **MCP First**: Integrate Model Context Protocol (MCP) tools for real-time org insights.
- **Salesforce Standards**: Enforce security and coding best practices automatically.

## Getting Started

### Prerequisites
- Node.js >= 20.19.0
- Salesforce CLI (`sf`) installed and authenticated

### Installation

**From Source** (recommended for development):
```bash
git clone https://github.com/designthynk/AgentSpec.git
cd AgentSpec
npm install -g .
```

**From npm** (once published):
```bash
npm install -g @designthynk/agentspec
```

### Initialization

Navigate to your Salesforce DX project and run:

```bash
agentspec init
```

This will create the `openspec/` directory structure with the necessary Salesforce-specific templates.

## Workflow

1.  **Draft Proposal**: `agentspec init` (if not already done) -> Ask your AI to create a change proposal.
2.  **Spec**: Define requirements in `specs/`.
3.  **Implement**: Use `sf` and MCP tools to build in the org.
4.  **Verify**: Run tests and update specs.
5.  **Archive**: `agentspec archive <change-id>` to merge changes into the permanent specs.

## Upstream Updates

AgentSpec is a fork of OpenSpec tailored for Salesforce. To benefit from upstream OpenSpec updates, you can merge changes from the [OpenSpec repository](https://github.com/Fission-AI/OpenSpec) into this project, resolving conflicts in `src/core/templates/agents-template.ts` (where Salesforce-specific instructions live).

## Credits & Acknowledgments

AgentSpec is built on top of [OpenSpec](https://github.com/Fission-AI/OpenSpec) by the Fission AI team. We are grateful for their work on creating a robust spec-driven development framework.

**Key Resources:**
- **OpenSpec Framework**: [github.com/Fission-AI/OpenSpec](https://github.com/Fission-AI/OpenSpec)
- **Salesforce Agentforce Documentation**: [developer.salesforce.com/docs/einstein/genai](https://developer.salesforce.com/docs/einstein/genai)
- **Salesforce CLI Plugin (Agent)**: [github.com/salesforcecli/plugin-agent](https://github.com/salesforcecli/plugin-agent)
- **Model Context Protocol (MCP)**: [@salesforce/mcp](https://www.npmjs.com/package/@salesforce/mcp)

This project adapts OpenSpec's methodology specifically for Salesforce Agentforce development, integrating MCP-first workflows and the Salesforce CLI agent lifecycle.

## License

MIT

