# Field / Rugged Telescoping Limb

## Concept

The rugged mobility limb adds a prismatic extension to the basic shoulder-and-wheel chain.

```text
chassis
  |
shoulder (theta)
  |
upper link (L)
  |
telescope (d)
  |
wheel
```

## Simplified planar model

With a shoulder origin `(x0, z0)` and a collinear telescoping section:

```text
r = L + d
x = x0 + r*cos(theta)
z = z0 + r*sin(theta)
```

The generalized coordinates are:

```text
q = [theta, d]
```

## Jacobian

For `p = [x, z]`:

```text
J = [ -(L+d)*sin(theta)   cos(theta) ]
    [  (L+d)*cos(theta)   sin(theta) ]
```

This is intentionally a minimal analytical reference. The final model must account for the actual telescope axis, offsets, joint limits, wheel center, and mechanical compliance.

## Why this is a module

The telescoping mechanism should not be required on household or organizational T3 configurations. It exists for applications where additional clearance, reach, terrain adaptation, or rugged mobility justify its added mass and complexity.
