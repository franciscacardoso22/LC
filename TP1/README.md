# 1. Project 1: Constraint Satisfaction & Optimization

Project 1 addresses combinatorial allocation and constraint modeling across two sub-problems:

## TP1.1: School Timetabling Generator [TP1.1](TP1.1/horario_escolar.py)
* **Goal:** Generate a weekly school schedule subject to teacher availability, room capacities (regular vs. specialized), and curricular workloads, while minimizing teacher idle periods ("buracos").
* **Approach:** Declarative CSP/COP modeling via CP-SAT. Supports automated parsing of CSV input data (`turmas.csv`, `disciplinas.csv`, `salas.csv`, `disponibilidade_excecoes.csv`).
* **Incremental Scheduling (R9):** Efficiently produces a modified valid schedule $H_1$ upon small resource disruptions (e.g., unexpected teacher unavailability, room breakdowns) by using baseline hints and bounding schedule perturbations.
* **Deliverable:** Reactive Marimo notebook (`horario_escolar.py`) and automated constraint verification suite.

## TP1.2: Generalized Sudoku as CSP [TP1.2](TP1.2/sudoku_resolucao.py)
* **Goal:** Model, generate, and solve generalized $n^2 \times n^2$ Sudoku puzzles using unified constraint abstractions.
* **Approach:** Implementation of a decoupled, generic `box` abstraction enforcing the "all-different" constraint over arbitrary sets of coordinates:
  * Specialization into sub-grid blocks (`cube`) and linear rows/columns (`path`).
  * Random clue generation within $[1, n^2]$ relying on the base `box` interface.
  * Formulation of the complete grid CSP without fixed-dimension assumptions (supporting $n=3$, $n=2$, and variant topologies).
* **Deliverable:** Interactive Marimo notebook (`sudoku_resolucao.py`).