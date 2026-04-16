# Changelog

All notable changes to the Azure plugin will be documented in this file.

This project adheres to [Semantic Versioning](https://semver.org/).

## [1.0.19] - 2026-04-16

### Changed

- Updated `azure-compute` skill with VM families and quotas reference documentation.
- Updated `azure-quotas` skill.
- Updated `microsoft-foundry` skill with agent deployment improvements.

## [1.0.18] - 2026-04-15

### Added

- `azure-prepare`: Static Web Apps deployment and Terraform configuration references.
- `azure-validate`: Terraform validation recipe.

### Changed

- Updated `azure-deploy` with pre-deploy checklist updates and Terraform error-handling guide.
- Updated `azure-prepare` with Azure YAML and Terraform configuration docs.
- Updated telemetry hook scripts.

## [1.0.17] - 2026-04-13

### Added

- Azure logo SVG asset (`assets/azure-logo.svg`).

## [1.0.16] - 2026-04-13

### Changed

- Updated `azure-cost` skill: all Cost Management API requests now require the `ClientType: GitHubCopilotForAzure` header.
- Updated `azure-prepare` and `azure-validate` skills.

## [1.0.15] - 2026-04-10

- Version bump.

## [1.0.14] - 2026-04-10

### Added

- `azure-kubernetes`: AKS autoscaler, rightsizing, spot nodes, and Vertical Pod Autoscaler (VPA) references.
- `azure-validate`: role verification reference.

### Changed

- Updated `azure-deploy` with live role verification guidance.
- Updated `azure-prepare` with functional verification and requirements docs.

## [1.0.13] - 2026-04-09

### Added

- `azure-cloud-migrate`: Google Cloud Run to Azure Container Apps migration guides (assessment, deployment, and conversion).

### Changed

- Updated `azure-deploy` skill.
- Updated `azure-prepare` with SQL Database and Container Apps improvements.

## [1.0.12] - 2026-04-08

### Added

- `azure-compute`: Expanded VM troubleshooter with dedicated reference guides for credential/auth errors, firewall blocking, network connectivity, RDP connectivity, RDP service configuration, SSH connectivity, and VM agent issues.
- `azure-deploy`: Entity Framework Core migration scripts (`apply-migrations`, `grant-and-migrate`) for azd workflows.
- `azure-prepare`: SQL Database access grant scripts (`grant-sql-access.sh`, `grant-sql-access.ps1`).

### Changed

- Updated `azure-enterprise-infra-planner` and `azure-hosted-copilot-sdk` skills.
- Updated `azure-prepare` with App Service and SQL Database Bicep improvements.

## [1.0.11] - 2026-04-07

### Added

- `azure-deploy`: Pre-deploy checklist reference.
- `azure-prepare`: Enhanced .NET Aspire deployment support and updated Aspire reference.
- `microsoft-foundry`: Agent invoke and troubleshoot workflow references.

### Changed

- Updated `azure-deploy` and `microsoft-foundry` skills.

## [1.0.10] - 2026-04-06

### Added

- `azure-deploy`: Entity Framework migrations recipe (`ef-migrations`), SQL managed identity configuration, and post-deployment steps.
- `azure-prepare`: Container Apps Bicep support.

### Changed

- Updated `azure-hosted-copilot-sdk` skill.
- Updated `microsoft-foundry` quota workflow.

## [1.0.9] - 2026-04-03

### Added

- `microsoft-foundry`: Foundry quota management workflow with capacity planning reference.

### Changed

- Updated telemetry hook scripts with improved tracking logic.
- Updated `azure-hosted-copilot-sdk`, `azure-prepare` (security references, App Service configuration), and `entra-app-registration` skills.

## [1.0.8] - 2026-04-02

- Version bump.

## [1.0.7] - 2026-04-02

### Added

- `azure-cost` — Unified Azure cost management: query historical costs, forecast future spending, and optimize to reduce waste.
- `azure-cost-optimization`: Redis cache detailed analysis and subscription-level report templates.
- `azure-deploy`: Live role verification and troubleshooting reference docs.
- `azure-prepare`: Functional verification, IAC rules, Bicep patterns, and specialized routing references.
- `azure-validate`: Role verification reference.

### Changed

- Updated `azure-resource-lookup` and `azure-validate` skills.

## [1.0.6] - 2026-03-31

### Added

- `azure-deploy`: Functions deployment recipe and CI/CD README.
- `azure-prepare`: New reference docs for architecture, context, generate, recipe selection, requirements, research, and resource limits/quotas.
- `azure-validate`: Error guides for azd and Azure CLI recipes.

### Changed

- Refactored `azure-deploy` skill with structured per-tool recipe references.
- Refactored `azure-prepare` skill with improved planning and recipe selection flow.
- Updated `azure-enterprise-infra-planner` references.
- Cleaned up `entra-app-registration` skill files.

## [1.0.5] - 2026-03-30

### Added

- `azure-cost-optimization`: AKS cost anomaly detection and AKS cost add-on references.
- `azure-prepare`: .NET Aspire deployment validation guidance.

### Changed

- Updated `azure-messaging` skill.

## [1.0.4] - 2026-03-27

### Changed

- Updated plugin README with improved documentation.

## [1.0.3] - 2026-03-26

### Added

- `azure-prepare`: Azure Functions deployment slot support with hosting-plan and OS compatibility matrix, and Bicep/Terraform examples.

## [1.0.2] - 2026-03-25

### Added

- `azure-enterprise-infra-planner` — Architect and provision enterprise Azure infrastructure from workload descriptions; generates Bicep or Terraform for networking, identity, security, and multi-resource topologies with WAF alignment.
- `azure-kubernetes` — Plan, create, and configure production-ready AKS clusters; covers Day-0 checklist, SKU selection, networking, security, autoscaling, and cost analysis.
- Telemetry hooks (`track-telemetry.sh`, `track-telemetry.ps1`) for PostToolUse events; added `hooks` field to plugin manifest.
- `azure-compute`: VM recommender and VM troubleshooter workflow references.
- `azure-deploy`: Per-recipe verification files (azd, Azure CLI, Bicep, Terraform, CI/CD).
- `microsoft-foundry`: Trace, observe, and eval-datasets workflow references; project connections doc.

### Changed

- Refactored `azure-compute` skill, extracting VM recommender and troubleshooter into dedicated workflow docs.
- Updated `azure-cloud-migrate`, `azure-compliance`, `azure-cost-optimization`, `azure-messaging`, `azure-prepare`, `azure-rbac`, `azure-resource-lookup`, and `azure-validate` skills.

## [1.0.1] - 2026-03-13

### Added

- `azure-upgrade` — Assess and upgrade Azure workloads between plans, tiers, or SKUs.

### Changed

- Removed `foundry-mcp` HTTP server from `.mcp.json` (non-spec `type`/`url` fields).
- Updated `azure-diagnostics` description.
- Updated `microsoft-foundry` description and bumped to version 1.0.5.

## [1.0.0] - 2025-03-12

### Added

- Initial release of the Azure plugin.
- Vendor-neutral `.plugin/plugin.json` manifest following the [Open Plugins Specification](https://open-plugins.com/plugin-builders/specification).
- Claude Code manifest (`.claude-plugin/plugin.json`).
- MCP server configuration (`.mcp.json`) for Azure MCP, Foundry MCP, and Context7.
- MIT `LICENSE` file at the plugin root.
- 21 agent skills:
  - `appinsights-instrumentation` — Azure Application Insights telemetry setup.
  - `azure-ai` — Azure AI Search, Speech, OpenAI, and Document Intelligence.
  - `azure-aigateway` — Azure API Management as an AI Gateway.
  - `azure-cloud-migrate` — Cross-cloud migration assessment and code conversion.
  - `azure-compliance` — Security auditing and best practices assessment.
  - `azure-compute` — VM size recommendation and configuration.
  - `azure-cost-optimization` — Cost savings analysis and recommendations.
  - `azure-deploy` — Azure deployment execution (azd, Bicep, Terraform).
  - `azure-diagnostics` — Production issue debugging and log analysis.
  - `azure-hosted-copilot-sdk` — Build and deploy GitHub Copilot SDK apps to Azure.
  - `azure-kusto` — Azure Data Explorer KQL queries.
  - `azure-messaging` — Event Hubs and Service Bus SDK troubleshooting.
  - `azure-prepare` — Application preparation for Azure deployment.
  - `azure-quotas` — Quota and usage management.
  - `azure-rbac` — RBAC role recommendation and assignment.
  - `azure-resource-lookup` — Azure resource discovery and listing.
  - `azure-resource-visualizer` — Mermaid architecture diagram generation.
  - `azure-storage` — Blob, File, Queue, Table, and Data Lake storage.
  - `azure-validate` — Pre-deployment validation checks.
  - `entra-app-registration` — Microsoft Entra ID app registration and OAuth setup.
  - `microsoft-foundry` — Foundry agent deployment, evaluation, and management.