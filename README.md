# Robotics Crane Project

## Description
The crane can rotate 180° and raise or lower a hook to pick up and place objects anywhere within its operating area. The project prioritizes lightweight construction and simplicity, making it suitable for learning mechanical design, motion control, and basic automation using mostly 3D-printed parts. It is intended as a hands-on platform for experimenting with real-world robotic concepts such as load handling, stability, and coordinated multi-axis movement at a small scale.

## Required Components
- [x] 4 x **Stepper Motors** for controlling each moving part
- [x] 4 x **ULN2003 Motor Drivers**
- [x] **Bluetooth Controller** (e.g., PS4, Xbox, or generic Bluetooth gamepad)
- [x] **ESP32** Board
- [x] 2 x **Breadboard Mini**
- [x] 1 x **Medium Breadboard**
- [x] **Wires/Jumpers** as needed 
- [x] 16 x AA **Alkaline Batteries**
- [x] High tension, low diameter **nylon**(the fishing kind)
- [x] **Lead weights** for creating tension in the hook

## Initial Questions

### 1. What is the system boundary?
The system consists of the crane structure, the ESP32 control board, the breadboard-mounted electronic components (motor drivers), and the motors responsible for rotation, trolley movement, and hook lifting. These components are integrated into the crane assembly, with electronics housed in a 3D-printed enclosure and wiring routed beneath the base platform.

Elements outside the system include the operator, the Bluetooth controller used for wireless input, and the objects being picked up, which interact with the crane but are not part of the control or mechanical system itself.

### 2. Where does intelligence live?
The system's intelligence resides entirely on the ESP32 microcontroller. The Bluetooth controller acts only as a wireless input interface, with all control logic and Bluetooth communication handling executed on the ESP32.

### 3. What is the hardest technical problem?
The primary technical challenge is the mechanical design of the crane, specifically creating reliable rotating and sliding mechanisms using 3D-printed parts that can handle loads without excessive friction or instability. Additionally, implementing stable Bluetooth communication and controller input parsing on the ESP32 presents a secondary challenge.

### 4. What is the minimum demo?
The minimum demo requires the crane to respond to Bluetooth controller input by moving at least one axis and interacting with a real object, such as lifting a small load off the ground. The demo is considered successful if the user can control the motion wirelessly through the Bluetooth controller and observe a clear, repeatable mechanical response.

### 5. Why is this not just a tutorial?
This project goes beyond a tutorial because it requires custom mechanical and control design rather than assembling predefined modules. Decisions about component placement, motion mechanisms, structural constraints, and wireless control implementation must be made and evaluated, making the outcome dependent on design choices instead of following a fixed set of instructions.

## Implementation Details and Challenges

>[!IMPORTANT]
>We decided to have the breadboard next to the crane plate, on the ground level, so we had to run wires up the leg and into the cabin. Due to limited space, the crane can safely operate in a 180 degree range without any of the cables coming loose, and without them getting stuck on the stepper motor responsible for the crane's rotation. This can be fixed by storing the breadboard assembly in the operator cabin, but this would require a much bigger scale.

We have overcome many challenges during the creation of this project. Most were related to creating the 3D models from scratch, using our real-world knowledge to adapt to the constraints of the project. One such constraint was related to size: we wanted to pick a scale that both respects the real-world equivalent, and also keeps the presentation concise and to the point. A crane is fundamental to construction, and while its operation is straightforward, it was very fun and interesting to implement. 

<img width="1053" height="1072" alt="image" src="https://github.com/user-attachments/assets/6339771c-a248-4a24-9c26-afcbadee21ab" />


We chose stepper motors in spite of their slow speeds, because we liked their inherent high torque. We consider this to be faithful to real life, as cranes need to lift heavy construction materials at the cost of speed. To power a stepper motor, we need 5V DC, so we connected 4 x AA batteries(in series) per motor, to a total of 16 batteries, each set providing about 6V DC. Two motors control the trolley on the X-Axis, one controls the rotation of the crane on the Z-Axis, and the last controls the hook on the Y-Axis. We wanted the project to look as best it could, so we came up with creative ways to hide the steppers. One is hidden at the back, two are hidden in what would be the crane operator's cabin, and the last is hidden underneath that cabin.

<img width="822" height="1111" alt="image" src="https://github.com/user-attachments/assets/8d771bbf-c385-48c3-99d9-9569469139f5" />


What made this project really challenging was the fact that we didn't settle for schematics available online, but instead modeled the crane ourselves from the ground up. We chose the specific positions of the motors, the movement of the trolley and the size of the _"counter weight"_, using a real crane as an inspiration and adapting things to our needs on the fly. After we figured out how many motors we needed, and their respective uses, we had to come up with creatives ways to incorporate them into a polished 3D body. First, we focused on the trolley functionality: how it would move, how it should look and how it would fit onto the crane's arm. We settled for a horizontal pulley system with a closed loop of nylon(yes, the fishing kind) with two steppers moving it on the X-axis by spinning spools of nylon. This approach isn't perfect, as we lose some of the already low speeds to the low levels of friction between the spools of nylon and the wheels we printed for the steppers. *We couldn't come up with a better way to increase friction between the two without modifying the scale of the project.* At the same time, we designed and printed the arm, which went through about two iterations or so before everything fitted as we wanted it. **Tolerances and plastic warping _are_ real and they _will_ hurt us :c.**

<img width="1172" height="894" alt="image" src="https://github.com/user-attachments/assets/d8656b1b-f5a8-4541-bdcf-9aa73a258ba9" />


After we decided that the operator cabin would hide most of the components(three drivers and two motors), we had to model it around them and make sure we had enough space to mount everything, all while keeping it proportional to the rest of the crane. Naturally, after printing we realized we omitted a few things, so we had to brute-force it and cut some plastic to make room. Thankfully, the biggest cut was made on the underside of the cabin, so it doesn't affect the project aesthetically. The stepper responsible for the hook is housed at the back of the crane, in the counterweight, and nylon crosses the length of the crane all the way to the front. Another challenge was the hook, as it is too light to keep tension in the string. To overcome this limitation, we used lead spheres, the kind one would use when fishing, to induce more tension in the wire.

<img width="1600" height="306" alt="image" src="https://github.com/user-attachments/assets/23ba1a7b-f131-4969-8f9b-d4dc47f98356" />


The easiest part was writing the code for the motors, as we used a pre-existing library available on GitHub, named [BluePad32](https://github.com/ricardoquesada/bluepad32). This allowed us to easily control the crane assembly with almost any kind of wireless controllers.

We feel like this project, while not being technologically complex, impresses through its aesthetic and solid functionality. It's not perfect, but we had a great deal of fun designing it from the ground up, feeling like true engineers by coming up with creative ideas, adapting on the fly and getting better at it and improving the design through trial and error. As the last blueprint for the Robotics class, this is our _love letter_ and _passion project_.

## How to Control the Crane Assembly
>These controls are viable for both Xbox and Playstation controllers.
<img width="1920" height="1080" alt="crane_project_controlls" src="https://github.com/user-attachments/assets/1c3d89e2-ad64-4215-a734-b98ec6b66851" />


## Pin Map

|Motor|ULN2003 Pins|ESP32 GIOP Pins|
|-----|------------|---------------|
|Motor 1|IN1, IN2, IN3, IN4|25, 26, 27, 14|
|Motor 2|IN1, IN2, IN3, IN4|32, 33, 22, 23|
|Motor 3|IN1, IN2, IN3, IN4|18, 19, 21, 4|
|Motor 4|IN1, IN2, IN3, IN4|16, 17, 5, 13|

 <img width="1068" height="591" alt="2026-02-05_19-31-42" src="https://github.com/user-attachments/assets/b0878234-436f-4c96-a0da-9318aa8de3b5" />


## Pictures and Demo
 [Youtube Link](https://youtu.be/Kfjp9-Fd0ek)
<details>
  <Summary>
  Pictures  
  </Summary>
  
  ![IMG_0709](https://github.com/user-attachments/assets/b8c06bae-ed45-48b3-9a16-4b6426e42578)
  ![IMG_0710](https://github.com/user-attachments/assets/53cc46b1-6a1c-490a-9bb5-94e7e5c58f82)
  ![IMG_0712](https://github.com/user-attachments/assets/e0a4b685-b800-4495-9deb-28a8c96f397d)
  ![IMG_0711](https://github.com/user-attachments/assets/74f67227-83f3-4f89-aa58-82faf17d7e46)
  
</details>

![](./docs/crane.gif)


## Credits
>[!NOTE]
>This project took roughly 15 hours to model, 30 hours to print and 16 hours to assemble and test.

This project will be made in collaboration with [octavian-diaconescu](https://github.com/octavian-diaconescu) and [Sed4u](https://github.com/Sed4u).
