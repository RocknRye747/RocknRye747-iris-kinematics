# T3 Kinematic Architecture

## Objective

Model T3 as a common robotic core with interchangeable mobility modules. Kinematic behavior belongs to the module model rather than being hard-coded into the core.

## Mobility module families

### Household / organizational

The baseline simple limb is modeled as:

`shoulder revolute -> fixed link -> wheel`

This deliberately avoids telescoping hardware when the operating environment does not require it.

### Field / rugged

The rugged limb is modeled as:

`shoulder revolute -> upper link -> prismatic telescope -> wheel`

The telescoping mechanism is therefore an additional degree of freedom rather than a requirement of every T3.

## Separation of concerns

1. **Body mobility:** planar motion and wheel-speed relationships.
2. **Limb kinematics:** wheel/contact-point placement relative to the chassis.
3. **Terrain/contact policy:** selection of a desired contact geometry from terrain information.
4. **Actuator execution:** conversion of commanded joint states to hardware commands.

The ESP32/reflex layer should execute validated commands; it should not become the source of truth for high-level geometric models.

## Important open question

The concept currently shows two powered front wheel modules and passive rear spherical support. The exact wheel/contact model must be validated against the eventual mechanical design before selecting a final controller abstraction. Do not assume that the presence of omniwheel rollers makes the complete vehicle holonomic.
