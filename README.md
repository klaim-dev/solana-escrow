# solana-escrow

Security-hardened SPL escrow: full lifecycle, attack tests, dApp UI.

**Stack:** Rust · Anchor · SPL Token · TypeScript · Next.js

**Status:** work in progress - updated daily.

## Goal

Build a portfolio-grade Solana escrow application with a security-first on-chain program, attack-oriented tests, and a small production-style frontend.

This repository is intended to become the strongest hiring signal in the track: a focused project that shows protocol design, testing discipline, UI integration, and practical Solana security thinking.

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

## Roadmap

- `s2-day01`: escrow state model and account layout
- `s2-day02`: initialize + deposit flow
- `s2-day03`: accept + settle flow
- `s2-day04`: cancel + refund flow
- `s2-day05`: attack tests and hardening
- `s2-day06`: README architecture and threat model
- `s2-day19+`: frontend and live demo

## Local Development

```bash
anchor build
anchor test
```

## Keywords

Solana, Anchor, Rust, SPL Token, escrow, DeFi, smart contract security, attack tests, Next.js.
