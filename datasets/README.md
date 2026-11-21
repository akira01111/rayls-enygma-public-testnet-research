# datasets

Processed, tabular data derived from `raw-data/` (for example CSV files built
from event logs or RPC responses).

Rules:

- Every dataset states which `raw-data/` files it came from, the method used,
  the date it was built, and a checksum.
- Derived data never replaces raw evidence. If a number is questioned, the
  check goes back to `raw-data/`.
- Observed, reconstructed, and estimated values are kept separate and labelled
  as such.
