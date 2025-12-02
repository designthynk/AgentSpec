# Agentforce Lifecycle Specification

## Purpose
Defines the canonical workflow for designing, creating, testing, and deploying Agentforce agents using AgentSpec, `sf` CLI, and MCP tools.

## Requirements

### Requirement: High-Level Workflow
The development process SHALL follow a structured 7-step lifecycle.

#### Scenario: Standard Development Flow
- **WHEN** a user requests a new agent
- **THEN** follow these steps:
  1. **Understand**: Extract goals, data sources, personas.
  2. **Check Env**: Verify Org and DX project.
  3. **Design**: Generate `agent-spec.yml` using `sf agent generate agent-spec`.
  4. **Deactivate**: Run `sf agent deactivate` if modifying an existing agent.
  5. **Create**: Run `sf agent create` to scaffold metadata.
  6. **Wire**: Implement Apex, LWC, and Permissions using MCP guidance.
  7. **Activate**: `sf agent activate` and `sf agent preview` (interactive chat).
  8. **Test**: Generate test specs and run `sf agent test`.

### Requirement: Environment Verification
The system MUST verify the Salesforce environment before starting work.

#### Scenario: Missing Org
- **WHEN** `list_all_orgs` returns no connected orgs
- **THEN** instruct user to run `sf org login web`

#### Scenario: Missing Project
- **WHEN** no `sfdx-project.json` is found
- **THEN** instruct user to run `sf project generate`

### Requirement: Agent Design
Agent designs SHALL start with a Functional Spec (AgentSpec) and result in a Technical Spec (Salesforce YAML).

#### Scenario: Two-Spec Workflow
- **WHEN** designing a new agent
- **THEN** define functional requirements in `openspec/specs/[agent-name]/spec.md` (The "Why" & "What")
- **AND** use those requirements to prompt `sf agent generate agent-spec`
- **AND** refine the resulting `agent-spec.yml` (The "How") to match the functional requirements

### Requirement: Agent Creation
Agents SHALL be created in the org from the YAML spec.

#### Scenario: Creating Agent
- **WHEN** spec is ready
- **THEN** run `sf agent create --spec <path> --name <name>`
- **AND** retrieve generated metadata into the DX project

### Requirement: Testing Strategy
Agents MUST be tested using the Agentforce testing framework.

#### Scenario: Running Tests
- **WHEN** agent logic is implemented
- **THEN** use `sf agent generate test-spec` to define cases
- **AND** run `sf agent test run` to verify behavior
