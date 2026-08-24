# ADR-002: Reuse Mature Open-Source Kinematics

## Status

Accepted for initial development.

## Decision

T3 should compose mature open-source robotics libraries instead of implementing a proprietary general-purpose kinematics engine.

## Candidate stack

- URDF/Xacro for robot and module descriptions.
- ROS 2 / ros2_control for hardware and controller interfaces.
- Pinocchio for forward kinematics, Jacobians, and dynamics where appropriate.
- TRAC-IK / MoveIt for inverse kinematics where appropriate.
- Drake for advanced constrained kinematics and validation where useful.
- Gazebo / Isaac Lab for simulation.

## T3-specific code

The project should focus custom implementation on:

- T3 geometry and module descriptions.
- Module discovery/configuration.
- Calibration.
- Terrain/contact policy.
- Hardware-specific interfaces.
- Validation and regression tests.

## Principle

If an existing OSS library already solves a general robotics problem reliably, T3 should integrate it rather than recreate it.
