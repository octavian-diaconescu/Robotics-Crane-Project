# Robotics Crane Project

## Description
The crane can rotate 360° and raise or lower a hook to pick up and place objects anywhere within its operating area. The project prioritizes lightweight construction and simplicity, making it suitable for learning mechanical design, motion control, and basic automation using mostly 3D-printed parts. It is intended as a hands-on platform for experimenting with real-world robotic concepts such as load handling, stability, and coordinated multi-axis movement at a small scale.

## Required Components
- **Stepper Motors** for controlling each moving part
- **Motor Drivers**
- **Bluetooth Controller** (e.g., PS4, Xbox, or generic Bluetooth gamepad)
- **Wires** and **Resistors** as needed
- **ESP32** Board
- **Breadboard/s**
- **LEDs** (BONUS)
- **Buzzers** for sounds (BONUS)

## Initial Questions

### 1. What is the system boundary?
The system consists of the crane structure, the ESP32 control board, the breadboard-mounted electronic components (motor drivers, buzzers, resistors), and the motors responsible for rotation, trolley movement, and hook lifting. These components are integrated into the crane assembly, with electronics housed in a 3D-printed enclosure and wiring routed beneath the base platform.

Elements outside the system include the operator, the Bluetooth controller used for wireless input, and the objects being picked up, which interact with the crane but are not part of the control or mechanical system itself.

### 2. Where does intelligence live?
The system's intelligence resides entirely on the ESP32 microcontroller. The Bluetooth controller acts only as a wireless input interface, with all control logic and Bluetooth communication handling executed on the ESP32.

### 3. What is the hardest technical problem?
The primary technical challenge is the mechanical design of the crane, specifically creating reliable rotating and sliding mechanisms using 3D-printed parts that can handle loads without excessive friction or instability. Additionally, implementing stable Bluetooth communication and controller input parsing on the ESP32 presents a secondary challenge.

### 4. What is the minimum demo?
The minimum demo requires the crane to respond to Bluetooth controller input by moving at least one axis and interacting with a real object, such as lifting a small load off the ground. The demo is considered successful if the user can control the motion wirelessly through the Bluetooth controller and observe a clear, repeatable mechanical response.

### 5. Why is this not just a tutorial?
This project goes beyond a tutorial because it requires custom mechanical and control design rather than assembling predefined modules. Decisions about component placement, motion mechanisms, structural constraints, and wireless control implementation must be made and evaluated, making the outcome dependent on design choices instead of following a fixed set of instructions.

## Credits
This project will be made in collaboration with [octavian-diaconescu](https://github.com/octavian-diaconescu).
