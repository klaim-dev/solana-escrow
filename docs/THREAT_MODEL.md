# Threat Model

Escrow security goals:

- only authorized signers can change escrow state
- vault token accounts are controlled by the escrow PDA
- expected mints and amounts are validated before settlement
- cancel and accept paths cannot both finalize the same escrow
- malformed accounts should fail with explicit errors

Planned test cases:

- wrong initializer
- wrong taker
- wrong mint
- reused escrow state
- invalid vault authority
- double accept
- cancel after accept
