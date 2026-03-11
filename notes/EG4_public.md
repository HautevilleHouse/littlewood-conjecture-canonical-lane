# EG4 Public Note

Gates: `LC_G4`, `LC_G5`
Constants: `rho_rigidity`, `exceptional_transfer`

This note packages rigidity and transfer. Rigidity excludes the bad-limit class by contradiction with the admissible identities, while the transfer inequality carries the rigid endpoint into the intended target class. The extracted theorem-level constants are `rho_rigidity > 0` and `exceptional_transfer > 0`, obtained from

- `rho_rigidity_raw`
- `c_exc_raw * transfer_gain_raw - e_exc_raw`

Together these gates block spurious endpoint models and preserve the intended target structure.
