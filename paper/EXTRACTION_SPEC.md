# Constant Extraction Spec (LC)

This file defines the theorem-constant extraction contract for this repository.

## Objective
Move constants from manual placeholder assignment to deterministic promotion:

1. extract raw constants from explicit component inputs and formulas,
2. normalize by declared references,
3. promote into `artifacts/constants_registry.json` and `artifacts/stitch_constants.json`.

## Inputs
- `artifacts/constants_extraction_inputs.json`

## Extracted Output
- `artifacts/constants_extracted.json`

## Promotion Output
- `artifacts/constants_registry.json`
- `artifacts/stitch_constants.json`
- `artifacts/promotion_report.json`

## Formula Set
- `kappa_flow_raw = c_flow_raw * density_floor_raw - e_flow_raw`
- `sigma_nonescape_raw = nonescape_floor_raw - transport_loss_raw - refinement_loss_raw`
- `kappa_compact_raw = 1.0 / (1.0 + delta_comp_sup_raw)`
- `rho_rigidity_raw = rho_rigidity_raw`
- `exceptional_transfer_raw = c_exc_raw * transfer_gain_raw - e_exc_raw`
- `eps_coh_raw = eps_coh_raw`
- `sigma_star_can_raw = sigma_star_can_raw`

## Validations
- positivity required for: `kappa_flow`, `sigma_nonescape`, `kappa_compact`, `rho_rigidity`, `exceptional_transfer`, `sigma_star_can`
- nonnegative required for: `eps_coh`
- strict-zero required for: `eps_coh` in strict mode

## Execution
`repro/run_repro.sh` runs:
1. `scripts/extract_constants.py`
2. `scripts/promote_constants.py`
3. `scripts/lc_closure_guard.py`
