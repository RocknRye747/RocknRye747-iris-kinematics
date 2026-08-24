# Household / Organizational Limb

## Concept

The low-complexity T3 limb is a fixed-length mechanical member attached to a shoulder revolute joint and terminating in a driven wheel module.

```text
chassis
  |
shoulder (theta)
  |
fixed link (L)
  |
wheel
```

## Planar position model

For a simplified planar model with shoulder origin at `(x0, z0)`:

```text
x = x0 + L*cos(theta)
z = z0 + L*sin(theta)
```

The exact frame convention is to be established in the URDF/Xacro model and must not be inferred from concept-art orientation.

## Jacobian

For the simplified position vector `p = [x, z]`:

```text
J = [ -L*sin(theta) ]
    [  L*cos(theta) ]
```

This is a starting analytical model for validation, not a final hardware implementation.

## Engineering intent

Use this module when telescoping travel, high clearance, or extreme terrain adaptation is not worth the added mechanical complexity. The module should expose the same mechanical/electrical interface as the rugged limb.
