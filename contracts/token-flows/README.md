# token-flows

Documentation of how tokens move through the Enygma system.

A token flow must keep four things separate:

1. **Main transaction** — the transaction that starts the flow.
2. **Destination contract address** — which contract the call was sent to.
3. **Token recipient from the Transfer event** — the actual recipient on
   record, which may differ from the address that was called.
4. **Balance changes** — before/after balances per address, from observable
   state only.

These four are never merged into a single number, and the same movement is
never counted twice. Shielded amounts that cannot be observed are recorded
as unobservable, not estimated.
