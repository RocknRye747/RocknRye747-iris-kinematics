# ADR-001: Treat Mobility Limbs as Modules

## Status

Accepted for concept development.

## Decision

T3 will use a common core chassis/interface with interchangeable mobility limbs. The rugged telescoping limb is an optional field module rather than a mandatory feature of every T3.

## Rationale

A fixed-length household/organizational limb can eliminate telescoping hardware where it provides little value. This reduces mechanical complexity, weight, cost, cable routing complexity, sealing requirements, and potential failure modes.

The field configuration can retain the more capable telescoping mechanism when the environment justifies it.

## Consequences

- The mechanical interface must be standardized early.
- Each mobility module needs an explicit kinematic description.
- Electrical and communication interfaces should be common across modules.
- Software must discover or load module-specific geometry and limits.
- Tests must verify that different modules produce compatible core-level interfaces.
