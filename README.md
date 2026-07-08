# solana-escrow

Security-hardened SPL escrow: full lifecycle, attack tests, dApp UI.

**Stack:** Rust · Anchor · SPL Token · TypeScript · Next.js

**Status:** active development.

## Goal

Build a portfolio-grade Solana escrow application with a security-first on-chain program, attack-oriented tests, and a small production-style frontend.

This repository is designed as a focused production-style project that shows protocol design, testing discipline, UI integration, and practical Solana security thinking.

## Scope

- Initialize escrow offer
- Deposit SPL tokens into a program-controlled vault
- Accept and settle the trade
- Cancel and refund safely
- Validate owners, mints, amounts, token accounts, and PDA authority
- Cover invalid signer, wrong mint, double-spend, replay, and close-account edge cases
- Expose a small Next.js app for the happy path

## Layout

```text
programs/escrow/  Anchor program
tests/e2e/        End-to-end and attack tests
app/              Next.js frontend
```

## Security Checklist

- PDA authority owns escrow vaults
- Token mints and token accounts are validated explicitly
- State transitions are one-way where required
- Cancel and accept paths cannot both settle
- Tests include malicious or malformed accounts
- No private keys, `.env`, or local validator artifacts in git

## Implementation Roadmap

- Escrow state model and account layout
- Initialize + deposit flow
- Accept + settle flow
- Cancel + refund flow
- Attack tests and hardening
- Architecture notes and threat model
- Frontend and live demo

## Local Development

```bash
anchor build
anchor test
```

## Keywords

Solana, Anchor, Rust, SPL Token, escrow, DeFi, smart contract security, attack tests, Next.js.
