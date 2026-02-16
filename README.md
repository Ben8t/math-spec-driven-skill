# Math Spec-Driven Skill

The Math Spec-Driven skill helps you turn vague requirements into precise, testable specifications.

It treats mathematics as a specification method (not just a school subject), using sets, functions, relations, invariants, and explicit edge cases to define what a system is and what it must do.

## Why this skill exists

Natural language is often ambiguous. This skill is designed for situations where precision and correctness matter more than narrative description.

It enforces three principles:

- Explicitness: every assumption is stated
- Composability: parts can be specified independently, then combined safely
- Falsifiability: claims are written so they can be proven or disproven

## When to use it

Use this skill when you need:

- Clear boundaries for ambiguous requirements
- Reliable behavior across many interacting rules
- Guaranteed input/output contracts
- Invariants that must always hold
- Complete edge-case coverage (including empty and error states)

## Method at a glance

1. Model the domain with mathematical primitives (sets, functions, relations, predicates).
2. Define the universe of discourse (what exists, what is excluded, what empty means).
3. Specify each function with signature, preconditions, postconditions, and invariants.
4. State invariants explicitly and define failure modes.
5. Handle boundary and degenerate cases as first-class behavior.
6. Verify composition between components (domain/codomain alignment).
7. Quantify uncertainty when needed (probability, expectation, variance).

## Expected output structure

When using the skill, outputs should generally follow:

1. Domain Model
2. Functions / Operations
3. Invariants
4. Edge Cases
5. Composition / Interaction
6. Open Questions

## Example prompt (TicTacToe)

Use this prompt to ask an AI assistant to create a math-spec-driven design for TicTacToe before implementation:

```text
Create a formal mathematical specification for a TicTacToe game engine, then derive an implementation plan.

Requirements:
- Use a 3x3 board, two players (X and O), alternating turns.
- Define all sets, types, and state variables explicitly.
- Specify core operations with signatures and contracts:
  - initializeGame
  - makeMove
  - checkWinner
  - isDraw
  - nextPlayer
- For each operation, provide preconditions, postconditions, and invariants.
- Include explicit edge cases: invalid coordinates, occupied cell, out-of-turn move, move after terminal state, and empty board behavior.
- Define terminal states and prove mutual exclusion where applicable (for example, game cannot be both win and draw).
- Describe composition flow for one full turn and for complete game progression.
- List open questions separately from the formal spec.

Output format:
1) Domain Model
2) Functions / Operations
3) Invariants
4) Edge Cases
5) Composition / Interaction
6) Open Questions

After the spec, provide pseudocode and a minimal test matrix that maps each invariant to at least one test.
```

## Source

The full skill definition lives at:

- `skills/math-spec-driven/SKILL.md`
