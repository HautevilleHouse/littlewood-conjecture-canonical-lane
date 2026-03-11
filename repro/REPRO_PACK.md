# Repro Pack

This pack is the public rerun surface for the canonical-lane workspace.

## What the pack does

`bash repro/run_repro.sh` deterministically:

1. extracts theorem constants from `artifacts/constants_extraction_inputs.json`,
2. promotes them into the registry and stitch artifacts,
3. runs `scripts/lc_closure_guard.py` in strict coherence mode,
4. refreshes `repro/repro_manifest.json`,
5. enforces `fully_extracted` release-gate mode.

## Pass condition

- `repro/certificate_runtime.json` has `all_pass == true`,
- all gates `LC_G1, LC_G2, LC_G3, LC_G4, LC_G5, LC_G6, LC_GM` are `PASS`,
- strict margin `M_LC = 0.8038585209003215`.
- `repro/repro_manifest.json` has no missing files or hash mismatches.

## Public pack files

- `paper/LITTLEWOOD_CONJECTURE_PREPRINT.md`
- `paper/CANONICAL_ROUTING_INDEX.md`
- `paper/EXTRACTION_SPEC.md`
- `notes/EG1_public.md`
- `notes/EG2_public.md`
- `notes/EG3_public.md`
- `notes/EG4_public.md`
- `notes/IDENTIFICATION_BRIDGE.md`
- `artifacts/constants_extraction_inputs.json`
- `artifacts/constants_extracted.json`
- `artifacts/constants_registry.json`
- `artifacts/stitch_constants.json`
- `artifacts/promotion_report.json`
- `repro/certificate_baseline.json`
- `repro/run_repro.sh`
- `scripts/lc_closure_guard.py`
- `scripts/extract_constants.py`
- `scripts/promote_constants.py`
- `scripts/update_manifest.py`
- `scripts/release_gate.py`
