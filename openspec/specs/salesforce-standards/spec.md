# Salesforce Standards Specification

## Purpose
Defines the mandatory coding standards and best practices for Salesforce development within AgentSpec.

## Requirements

### Requirement: General Development Rules
All development SHALL follow standard Salesforce DX and MCP practices.

#### Scenario: CLI Usage
- **WHEN** executing commands
- **THEN** always use `sf` (never `sfdx`)
- **AND** use MCP tools when available for insights

#### Scenario: Metadata Tracking
- **WHEN** creating objects, classes, or triggers
- **THEN** corresponding `-meta.xml` files MUST be created and tracked

### Requirement: Apex Standards
Apex code MUST adhere to security, performance, and testing standards.

#### Scenario: Security
- **WHEN** writing database operations
- **THEN** use `WITH USER_MODE` or `WITH SECURITY_ENFORCED`
- **AND** check Field Level Security (FLS)

#### Scenario: Testing
- **WHEN** writing Apex classes
- **THEN** maintain minimum 75% code coverage
- **AND** use `Test.startTest()` / `Test.stopTest()`
- **AND** do not use `SeeAllData=true`

### Requirement: LWC Standards
Lightning Web Components MUST follow SLDS and architectural guidelines.

#### Scenario: Component Creation
- **WHEN** creating a new LWC
- **THEN** call `guide_lwc_development` MCP tool first
- **AND** use `sf lightning generate component`

#### Scenario: HTML Structure
- **WHEN** writing LWC templates
- **THEN** use SLDS classes (`slds-card`, `slds-grid`)
- **AND** use semantic HTML

### Requirement: Permissions
Every feature MUST have associated permission sets.

#### Scenario: Permission Set Naming
- **WHEN** creating a permission set
- **THEN** follow format `[AppPrefix]_[Component]_[AccessLevel]`
- **EXAMPLE** `Sales_Opportunity_Read`

#### Scenario: Documentation
- **WHEN** adding permissions
- **THEN** update `Permissions.md` with purpose and assignment rules
