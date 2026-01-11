# Robotics Crane Project

## Description
The crane can rotate 360° and raise or lower a hook to pick up and place objects anywhere within its operating area. The project prioritizes lightweight construction and simplicity, making it suitable for learning mechanical design, motion control, and basic automation using mostly 3D-printed parts. It is intended as a hands-on platform for experimenting with real-world robotic concepts such as load handling, stability, and coordinated multi-axis movement at a small scale.

## Required Components
- **DC Motors** for controlling each moving part
- **Motor Drivers**
- **Joysticks** to handle the crane
- **Wires** and **Resistors** as needed
- **Arduino UNO** Board
- **Breadboard/s**
- **Buzzers** for sounds (BONUS)
- _**No ESP32 needed for this project!**_

## Initial Questions

### 1. What is the system boundary?
The system consists of the crane structure, the Arduino control board, the breadboard-mounted electronic components (motor drivers, buzzers, resistors), the motors responsible for rotation, trolley movement, and hook lifting, as well as a joystick-based control panel mounted to the crane’s base. These components are integrated into the crane assembly, with electronics housed in a 3D-printed enclosure and wiring routed beneath the base platform.

Elements outside the system include the operator and the objects being picked up, which interact with the crane but are not part of the control or mechanical system itself.

### 2. Where does intelligence live?
The system’s intelligence resides entirely on the Arduino microcontroller. The joystick panel acts only as an input interface, with all control logic executed locally on the device.

### 3. What is the hardest technical problem?
The primary technical challenge is the mechanical design of the crane, specifically creating reliable rotating and sliding mechanisms using 3D-printed parts that can handle loads without excessive friction or instability.

### 4. What is the minimum demo?
The minimum demo requires the crane to respond to joystick input by moving at least one axis and interacting with a real object, such as lifting a small load off the ground. The demo is considered successful if the user can control the motion through the joystick and observe a clear, repeatable mechanical response.

### 5. Why is this not just a tutorial?
This project goes beyond a tutorial because it requires custom mechanical and control design rather than assembling predefined modules. Decisions about component placement, motion mechanisms, and structural constraints must be made and evaluated, making the outcome dependent on design choices instead of following a fixed set of instructions.

## Credits
This project will be made in collaboration with [octavian-diaconescu](https://github.com/octavian-diaconescu).
