# AssetWatch App

> Stellar asset issuer change monitor

![Logo](assets/logo.svg)

## Product overview

A watcher for issuer configuration and asset metadata changes, producing an auditable timeline when important trust, authorization, or documentation fields change.

This repository is the user-facing side of the project. It turns the protocol behavior
into a workflow that a person can inspect, understand, and test. It should not hide
important Stellar operations behind unexplained automation.

## What the app should show

- Current network and connection state.
- The user action being performed.
- Relevant Stellar transaction or contract references.
- Clear success, pending, and failure states.
- A readable history of protocol events.
- Links to deeper technical documentation.

## Architecture

```text
Browser
  |
  +-- application UI
  |
  +-- Stellar SDK / wallet integration
  |
  +-- asset-watch-backend
          |
          +-- database / index
          +-- asset-watch-contracts
```

The browser should never contain server-side secrets. Network configuration belongs in
environment variables and deployment settings.

## Local setup

```bash
npm install
cp .env.example .env.local
npm run dev
```

The default configuration is intended for development and Testnet. Do not paste
production credentials into `.env.local` or commit them.

## UX principles

The application should explain protocol actions before asking for wallet approval.
Errors should preserve enough context for a user or developer to diagnose what happened.

## Roadmap

- [ ] Replace baseline screen with the project-specific workflow
- [ ] Add wallet connection
- [ ] Connect to the contract layer
- [ ] Add transaction status tracking
- [ ] Add error and retry states
- [ ] Add end-to-end Testnet flow
- [ ] Add accessibility and mobile review

## Maintainer

Maintainer: 
JerryOJJ

