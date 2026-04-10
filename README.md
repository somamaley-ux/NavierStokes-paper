# Navier--Stokes Paper

Standalone Lean snapshot for the manuscript-facing Navier--Stokes theorem
surface and its current paper bundle.

## Contents

- `MaleyLean/Papers/NavierStokes/`
  standalone Lean dependency closure for the Navier--Stokes paper surface
- `MaleyLean/Papers/Meta/PrimitiveToPeriodicLocalTheory.lean`
  shared primitive-to-local-theory bridge required by the extracted surface
- `Checks/Axiom/NavierStokesPaperSurfaceSummaryCleanAxiomCheck.lean`
  dedicated axiom audit entry point
- `papers/navier_stokes/main.tex`
  canonical manuscript source
- `papers/navier_stokes/main.pdf`
  manuscript PDF supplied from the workspace
- `reports/audits/navier_stokes_paper_surface_summary_clean_axiom_audit.txt`
  human-readable audit note
- `reports/status/navier_stokes_status.md`
  human-readable status note

## Repository Layout

- `MaleyLean/`
  extracted Lean source closure needed to build the Navier--Stokes paper surface
- `Checks/`
  dedicated Lean entry points for axiom-audit verification
- `papers/navier_stokes/`
  manuscript source, PDF, appendices, readiness bundle, and build helpers
- `reports/`
  exported audit and status artifacts associated with this snapshot

## Build

This project uses Lean `v4.28.0` via `lean-toolchain`.

Build the extracted project with:

```text
lake build
```

Build just the dedicated axiom check with:

```text
lake env lean Checks\\Axiom\\NavierStokesPaperSurfaceSummaryCleanAxiomCheck.lean
```

## Verification

The extracted project builds successfully as a standalone Lean repo, and the
dedicated summary-surface axiom check reports that
`NavierStokesPaperSurfaceSummaryCleanStatement` depends on no axioms.

## Scope

This repo packages the current Navier--Stokes manuscript-facing theorem spine
in standalone form: the primitive route, continuation and obstruction layers,
obligation ledgers, verbatim manuscript registers, and the cleaned surface
summary.

It certifies the current paper surface as axiom-free at the manuscript-facing
level.

It does not claim a full end-to-end classical PDE proof of the periodic
three-dimensional Navier--Stokes theorem in Lean. It does, however, package a
structural route intended as a qualifying claim under the official Clay rules,
which explicitly allow genuinely new mathematical methods rather than only
classical PDE-native proof styles.
