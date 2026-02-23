# System Architecture — Pressure Protocol

Pressure Protocol is built using a modular architecture centered around a global Pressure Manager. The system is designed to separate core mechanics from career-specific logic, allowing scalability and maintainability.

---

## Overall Scene Flow

The game follows a structured scene progression:

Title Screen  
Central Hub (Space Shuttle Environment)  
Career Portal  
Difficulty Selection  
Career Simulation  
Results Screen  

Each major section is its own scene in Godot and connects through defined transitions.

---

## Core System: Pressure Manager

At the center of the game is the Pressure Manager.

This system controls:

- Stress level tracking
- Performance thresholds
- Difficulty scaling
- Outcome calculation
- Real-time feedback

Pressure increases when:

- The player hesitates
- A decision is incorrect
- A patient fails
- A task is missed
- A critical event occurs

Pressure decreases when:

- The player makes correct decisions
- Tasks are completed efficiently
- The player stabilizes high-risk situations

If pressure reaches critical levels, performance collapses and the final outcome is negatively affected.

The Pressure Manager is global, meaning all careers connect to the same stress calculation logic.

---

## Career Modules

Each career is implemented as an independent gameplay module.

### ER Physician
Handles:
- Patient triage logic
- Severity classification
- Timed treatment decisions
- Event-based interruptions

### Lawyer
Handles:
- Case analysis
- Risk assessment
- Strategic decision outcomes

### Financial Analyst
Handles:
- Market volatility simulation
- Timed investment decisions
- Risk versus reward evaluation

### Chef
Handles:
- Order management
- Escalating time pressure
- Mistake penalties

Each module communicates with the Pressure Manager but does not control it directly.

---

## Difficulty System

Each career includes three difficulty modes:

Easy — slower pacing, guided decisions  
Medium — moderate time constraints  
Hard — random events and rapid pressure escalation  

Difficulty modifies:

- Pressure gain rate
- Event frequency
- Time windows
- Penalty impact

---

## Modularity and Scalability

Pressure Protocol is engineered as a scalable platform.

Because the pressure system is centralized and careers are modular:

- New careers can be added without rewriting core mechanics
- Difficulty balancing can be adjusted globally
- Performance evaluation remains consistent across simulations

---

## Design Philosophy

The architecture mirrors real-world performance systems.

Instead of isolated scoring, Pressure Protocol uses cumulative stress modeling. Early mistakes influence later outcomes, creating realism and psychological depth.
