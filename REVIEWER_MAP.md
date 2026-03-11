# Reviewer Map

## Claim Scope

- Canonical-lane claim: inside the `manifold_constrained` lane, if the theorem chain in this repository holds and the guard certificate passes, the repository-level closure claim is satisfied.
- Standard target claim: carried by the in-repo bridge theorems tying the lane to the target statement.

## Theorem Dependency Chain

1. `EG1`: coercive response and active control floor.
2. `EG2`: capture and admissible continuation.
3. `EG3`: compactness and no-collapse spacing.
4. `EG4`: rigidity and transfer.
5. Identification bridge: strict coherence on the determining class.
6. Scalar closure: `LC_G1, LC_G2, LC_G3, LC_G4, LC_G5, LC_G6, LC_GM` all `PASS`.

Primary files:

- `paper/LITTLEWOOD_CONJECTURE_PREPRINT.md`
- `notes/EG1_public.md`
- `notes/EG2_public.md`
- `notes/EG3_public.md`
- `notes/EG4_public.md`
- `notes/IDENTIFICATION_BRIDGE.md`

## Closure Gates

| Gate | Constant | Description |
|------|----------|-------------|
| `LC_G1` | `kappa_flow` | projected flow response has a strict positive floor |
| `LC_G2` | `sigma_nonescape` | nonescape defect stays above capture floor across transport and refinement losses |
| `LC_G3` | `kappa_compact` | normalized near-failure families are precompact and escape windows do not collapse |
| `LC_G4` | `rho_rigidity` | bad invariant-measure models are excluded |
| `LC_G5` | `exceptional_transfer` | rigid limit transfers to the zero exceptional-set endpoint class |
| `LC_G6` | `eps_coh` | strict coherence / identification closure |
| `LC_GM` | derived | final strict margin |

## Falsification Conditions

- `repro/certificate_runtime.json` has any non-`PASS` gate.
- `lane.active_lane != "manifold_constrained"`.
- `all_pass != true`.
- Any manifest hash mismatch under `repro/repro_manifest.json`.
- A verified counterexample to any EG theorem statement used in the paper.

## Reproducibility Check

Run:

```bash
bash repro/run_repro.sh
```

Then verify:

```bash
python3 - <<'PY'
import json
from pathlib import Path
d=json.loads(Path('repro/certificate_runtime.json').read_text())
assert d.get('all_pass') is True
assert d.get('lane',{}).get('active_lane') == 'manifold_constrained'
for g in ['LC_G1','LC_G2','LC_G3','LC_G4','LC_G5','LC_G6','LC_GM']:
assert d['gates'].get(g) == 'PASS', g
print('OK')
PY
```
