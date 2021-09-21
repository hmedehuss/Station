# Gazebo conveyor belt plugin

## How to use

Clone the repository to your project `src` folder and compile the project.

Add this to the end of your URDF/Xacro

```xml
<gazebo>
    <plugin name="conveyor_belt_plugin" filename="libROSConveyorBeltPlugin.so">
        <robot_namespace>/robot_ns</robot_namespace>
        <link>belt_link</link>
        <update_rate>10</update_rate>
        <max_velocity>0.2</max_velocity>
    </plugin>
</gazebo>
```

The belt is active by default, with power of 0%. 

You can change the belts linear velocity using the `<max_velocity>` parameter.

To set the power value, you need to use rosservice.

`$ rosservice call /robot_ns/conveyor/control "power: 15.0"`

This would set the power to 15%.


