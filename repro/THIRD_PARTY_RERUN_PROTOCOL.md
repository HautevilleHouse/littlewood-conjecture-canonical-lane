# Third-Party Rerun Protocol

1. Clone the repository.
2. Run:

   ```bash
   bash repro/run_repro.sh
   ```

3. Confirm that `repro/certificate_runtime.json` reports:

   - `lane.active_lane = manifold_constrained`,
   - `LC_G1` through `LC_G6` are `PASS`,
   - `LC_GM = PASS`,
   - `all_pass = true`.

4. Confirm that `scripts/release_gate.py --mode fully_extracted` returns `ok = true`.
5. Confirm that the tracked files in `repro/repro_manifest.json` all match their SHA-256 hashes.

The rerun path is deterministic on the shipped extraction inputs and public-pack files.
