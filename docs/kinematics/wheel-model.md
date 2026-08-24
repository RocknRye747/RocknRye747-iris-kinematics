# T3 Wheel / Vehicle Kinematics

## Current physical concept

The concept art shows two prominent front wheel modules and passive spherical rear support. The final controller model must follow the actual mechanical design rather than the appearance of the wheels.

## Differential-drive candidate

If the two front wheels are independently driven and the rear supports are passive, the first candidate model is differential drive:

```text
v = r/2 * (omega_L + omega_R)
omega_z = r/b * (omega_R - omega_L)
```

where `r` is driven-wheel radius and `b` is the effective distance between driven wheel contact centers.

This should remain a hypothesis until the wheel contact geometry and steering constraints are validated.

## Omniwheel caution

Wheel rollers provide passive lateral compliance. They do not, by themselves, establish a holonomic vehicle. A controller should only expose independent planar `vx`, `vy`, and `omega_z` motion if the physical drive arrangement actually supports it.

## Validation tests

1. Straight-line equal-speed test.
2. In-place rotation test.
3. Curved-path odometry test.
4. Passive-caster alignment/slip test.
5. Lateral disturbance test.
6. Terrain-induced wheel unloading test.

The measured results should determine the final vehicle kinematic abstraction.
