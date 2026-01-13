# Project Requirements

## 1. Project Goal
This project is a deterministic, rule-driven combat simulation platform.
Gameplay is intentionally minimal and serves only as a validation layer
for system correctness, determinism, and reliability.

## 2. Non-Goals
The following are explicitly out of scope:
- PvP gameplay
- Character progression or equipment systems
- Narrative, story, or world-building
- Advanced client-side prediction or rollback
- Visual polish or animation quality

## 3. Core Constraints
- 4-player cooperative session vs AI
- Server-authoritative simulation
- Fixed tick rate: 20 TPS
- Deterministic execution with fixed RNG seed
- Replayable by re-simulating recorded inputs
- Must be completable within 4 months

## 4. Gameplay as Validation
Gameplay mechanics (cards, units, buildings) exist solely to validate:
- Rule system correctness
- State transitions
- Deterministic outcomes
- Session recovery and replay

## 5. Success Criteria
The project is considered complete if:
- A full match can be simulated deterministically
- The same inputs always produce the same outcome
- Sessions can recover from disconnects
- Match results are idempotent and persistent
- Metrics and basic load tests are available
