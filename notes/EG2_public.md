# EG2 Public Note (Capture and Restart)

Canonical wording: `transport / local-to-global transfer`.

In-paper anchor: `paper/LITTLEWOOD_CONJECTURE_PREPRINT.md` (`LC_G2`).

## Goal
Expand the compressed capture/restart language into the local-to-global transport gate for `prove Littlewood's conjecture by routing admissible homogeneous-dynamics states through flow coercivity, nonescape capture, compactness, rigidity, exceptional-set transfer, and strict coherence`.

## Objects

- transport carrier: the admissible evolution, deformation, or routed lattice declared in the preprint.
- capture floor: `sigma_nonescape`.
- restart law: the normalization/re-entry rule that keeps corrective steps inside the admissible class.
- carried losses: defect, restart, and normalization losses that must remain explicit.

## Closure Criterion

`LC_G2` closes when `sigma_nonescape` survives admissible losses and restart corrections: nonescape defect stays above capture floor across transport and refinement losses.
This is the transport contribution to `M_LC`.

## Lemma Chain and Proof Payload

### Lemma EG2.1 (transport accounting)
Every transport step used by the lane is charged to the declared defect ledger instead of being absorbed into prose.

Payload: check that the capture constant `sigma_nonescape` is present in the constants registry and extraction inputs.

### Lemma EG2.2 (restart preservation)
Restart or normalization preserves the declared admissible class and does not create an untracked remainder.

Payload: inspect the repro script and guard output for the gate tied to `sigma_nonescape`.

### Theorem EG2.3 (capture gate closure)
If transport accounting and restart preservation hold, then `LC_G2` carries local control forward without breaking admissibility.

## Current Instantiation

- gate: `LC_G2`
- artifact key: `sigma_nonescape`
- canonical equivalent: `transport / local-to-global transfer`
- audit surface: `repro/run_repro.sh` and `repro/certificate_runtime.json`
