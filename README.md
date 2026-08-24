# IRIS T3 Kinematics

Open-source kinematics, robot description, simulation interfaces, and validation work for the IRIS T3 modular robotic platform.

## Scope

This repository separates the T3 **common core** from interchangeable physical modules. The current physical concept uses two articulated front mobility limbs and passive rear support. Two primary limb families are being developed:

- **Household / organizational limb:** simple, lightweight, non-telescoping mobility limb.
- **Field / rugged limb:** articulated, telescoping mobility limb for increased clearance and terrain adaptation.

The goal is to reuse established open-source robotics mathematics and tooling wherever practical rather than creating a new kinematics framework unnecessarily.

## Proposed software stack

- URDF/Xacro — robot and module descriptions
- ROS 2 / ros2_control — hardware and controller abstraction
- Pinocchio — forward kinematics, Jacobians, and dynamics where required
- TRAC-IK / MoveIt — inverse kinematics where appropriate
- Drake — advanced constrained kinematics and validation where useful
- Gazebo / Isaac Lab — simulation and regression testing
- ESP32 firmware — low-level actuator execution only

## Architecture principle

```text
                    T3 CORE
                       |
              +--------+--------+
              |                 |
       HOUSEHOLD LIMB      RUGGED LIMB
              |                 |
       revolute + wheel   revolute + prismatic + wheel
              |                 |
              +--------+--------+
                       |
                 common module
                    interface
```

The kinematics repository owns the **geometric and mathematical contract** between the T3 core and its interchangeable physical modules. It does not attempt to replace mature robotics libraries.

## Current status

Early architecture / model-definition phase. Dimensions, actuator limits, wheel geometry, mass properties, and contact parameters are intentionally treated as configurable engineering inputs until validated against physical hardware.

## Design rule

Do not treat placeholder concept-art specifications as engineering truth. Every physical parameter should eventually be traceable to a measured component, CAD model, datasheet, or explicit engineering assumption.
