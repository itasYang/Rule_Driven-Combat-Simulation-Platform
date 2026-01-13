# System Architecture

## 1. Purpose

This document defines the high-level architecture of the project.
It exists to freeze system boundaries and prevent uncontrolled complexity.

## 2. High-Level Overview

The system is divided into a small number of clearly separated modules.
Gameplay logic is isolated from networking, persistence, and tooling.

## 3. Core Modules

### Gateway
- Manages client connections
- Handles session and room entry
- Does NOT contain gameplay logic

### Simulation Server
- Runs a deterministic tick loop (20 TPS)
- Owns all gameplay state
- Executes combat simulation and AI
- Produces state snapshots

### Rule Engine
- Applies data-driven rules and modifiers
- Evaluates rule conditions
- Manages rule lifecycles (start / active / expire)

### Replay System
- Records simulation inputs
- Replays matches deterministically
- Used only for debugging and validation

### Storage
- Redis: session state and room metadata
- SQL database: match results and settlements

### Observability
- Metrics collection
- Tracing and logging
- Used to validate system behavior

## 4. Non-Goals

The following responsibilities are explicitly excluded:
- Client-side prediction or rollback
- Visual rendering or animation logic
- Gameplay polish or balance tuning
