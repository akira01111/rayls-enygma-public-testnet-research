# scripts

Audit and reproduction scripts: read-only RPC queries, log parsing, and checks
that let anyone reproduce a number in this repository.

Rules:

- Scripts are read-only. They never send transactions, sign anything, or
  change on-chain state.
- Each script records the tool and client versions it was run with.
- A script that needs a secret or a private key does not belong here.
