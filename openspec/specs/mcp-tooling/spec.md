# MCP Tooling Specification

## Purpose
Defines the available Model Context Protocol (MCP) tools and their mandatory usage patterns in the AgentSpec workflow.

## Requirements

### Requirement: Tool Availability
The system SHALL support a core set of Salesforce MCP tools.

#### Scenario: Auth Tools
- **WHEN** needing org info
- **THEN** use `get_username` and `list_all_orgs`

#### Scenario: Apex Tools
- **WHEN** working with Apex
- **THEN** use `run_apex_test` and `run_soql_query`

#### Scenario: LWC Tools
- **WHEN** developing LWCs
- **THEN** use `guide_lwc_development`, `orchestrate_lwc_component_creation`, and `guide_lwc_accessibility`

### Requirement: Mandatory Tool Usage
Certain tasks MUST be preceded by specific MCP tool calls.

#### Scenario: LWC Development
- **WHEN** starting LWC work
- **THEN** `guide_lwc_development` MUST be called to get latest patterns

#### Scenario: Mobile Development
- **WHEN** building mobile features
- **THEN** mobile-specific MCP tools MUST be consulted

### Requirement: Tool vs CLI
MCP tools SHALL be preferred over CLI for information gathering.

#### Scenario: Information Gathering
- **WHEN** needing structured data (orgs, limits, code analysis)
- **THEN** use MCP tools

#### Scenario: Execution
- **WHEN** performing state-changing operations (deploy, create agent)
- **THEN** use `sf` CLI
