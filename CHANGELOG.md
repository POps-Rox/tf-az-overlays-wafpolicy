# v2.0.0 - 2026-05-11

Changed
- **BREAKING**: Upgrade `azurerm` provider to `~> 4.20` (was `~> 3.116`).
- **BREAKING**: Raise minimum Terraform CLI to `>= 1.10` (was `>= 1.9`).
- Declare `azapi ~> 2.0` provider for fleet alignment.
- Examples: pin matching provider versions; add `subscription_id` env-var hint
  (azurerm 4.x requires `ARM_SUBSCRIPTION_ID` for apply; `validate` unaffected).
- Root `versions.tf` preserves the `configuration_aliases = [azurerm.hub_network]` declaration that consumers depend on. Removed the deprecated `skip_provider_registration = true` from all 4 example `versions.tf` files (removed in azurerm 4.x; replaced by `resource_provider_registrations = "none"` if opted in).

Notes
- Cross-module dependency: transitive sibling overlays must also ship 4.x-compatible
  releases before this version can resolve cleanly via `terraform init -upgrade`.

# Changelog

# v1.0.0 - 02/03/2024

Added
- Init Source
