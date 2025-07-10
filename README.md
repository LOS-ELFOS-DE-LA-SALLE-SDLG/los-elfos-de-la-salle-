 Future Engineer 2025 – Team los elfos de la salle – Colegio De La Salle
 
👋 Hello everyone!

We are Fabricio Medina, Roberto Pereira, and Ganeshkumar Patel, three students passionate about robotics, technology, and innovation. Together, we are "Elfos de La Salle", proudly competing in the WRO Future Engineers 2025 international competition.

Our mission is to develop a creative and functional project that tackles real-world challenges through engineering, design, and programming.
We work as a team, constantly learn, and represent the values of our Lasallian community with pride.
We’re ready to give it our all on the road to WRO 2025!



Content / Contenido 

* **t-photos** includes two images showcasing the team members –
  **Contiene dos fotografías que muestran a los integrantes del equipo.**

* **v-photos** contains images of the vehicle used in the project –
  **Incluye fotos del vehículo utilizado en el proyecto.**

* **video** holds a `video.md` file with links to YouTube videos demonstrating the robot in action –
  **Contiene un archivo con enlaces a videos de YouTube donde se muestra el funcionamiento del robot.**

* **schemes** features schematic diagrams (PNG and Fritzing formats) that show the electromechanical layout of all components, including electronics and motors, and how they are interconnected –
  **Presenta diagramas esquemáticos en formato PNG y Fritzing que ilustran todos los componentes electromecánicos del vehículo y sus conexiones.**

* **src** includes the source code for the software that controls each of the robot’s programmed components used in the competition –
  **Incluye el código fuente del software que controla los componentes programados del vehículo para la competencia.**

* **models** contains 3D model files used to print parts of the vehicle with 3D printers –
  **Contiene los archivos de modelos 3D utilizados para imprimir piezas del vehículo.**

* **other** gathers additional resources such as hardware specs, communication protocols, shopping links, datasets, and other useful materials to understand and build the vehicle –
  **Agrupa recursos adicionales como especificaciones de hardware, protocolos de comunicación, enlaces de compra, conjuntos de datos y otros materiales útiles para preparar el vehículo.**


## 1. Materials

- PixyCam L209
- Breadboard (Protoboard)
- L298N Motor Driver
- 1.5 V DC Motor
- Servo Motor MG995
- 12 V LiPo Battery
- Switch
- Button
- Ultrasonic Sensors
- Arduino Mega
- LEGO Pieces
- Arduino Cables



First, we start with the **12 V LiPo battery**. From the battery, we connect two wires: one positive (**red**) and one negative (**black**).  
The positive wire is connected to the **switch**, and from the other side of the switch, another wire goes to the **Vcc input** of the **L298N motor driver**.  
The battery’s **ground cable** connects directly to the **GND input** on the L298N.

The **DC motor’s** positive and negative wires are connected to the motor output ports (**OUT1** and **OUT2**) on the L298N.

From the **Vcc** and **GND** of the L298N, an adapter cable powers the **Arduino Mega**, using the Arduino’s built-in voltage regulator.

On the L298N, we connect control wires (**IN1**, **IN2**, **ENA**) to the Arduino. These wires supply control signals to the motor driver to regulate the motor’s speed and direction.

On the **Arduino Mega**, we connected our **MG995 servo motor**, the **PixyCam L209**, and the three **ultrasonic sensors**, each to their dedicated pins.



## 2. Setbacks

We had to change the original motor due to its energy consumption and weight.  
We also replaced the four batteries in series with a single rechargeable **12 V LiPo battery**.

The wheel size had to be reduced to fit the ultrasonic sensors properly.

The 3D chassis base broke and had to be reinforced with additional parts.

We almost burned the new motor during one test with the new battery’s higher power output.



## 3. Motivation

The motivation for participating in **WRO 2025** was clear and exciting: to experience a robotics competition for the first time and to represent our school in the **Future Engineers** category.  
We want to establish a solid foundation for future students at our school, inspiring young people to get involved in robotics and helping promote its growth in Panama.



## 4. Code Explanation

In the first lines of the code, we import the required Arduino libraries and define all the pins for the electronic components — this is done outside of `void setup()`.

In the `setup()` function, we initialize the components and reset all the variables we use.

In `void loop()`, we get the distance readings from the ultrasonic sensors and receive the image feed from the **PixyCam L209**, which is then processed through conditional `if` statements.

If the camera detects the **yellow color**, it signals the robot to start turning and increase speed to complete the turn correctly. Then, when the **blue line** is detected, it adjusts the speed and returns the servo motor to its default angle.

If the camera does not detect anything, the ultrasonic sensors are used to detect obstacles and help the robot avoid them.

Each successful turn the robot makes is counted — when it reaches up to **12 turns**, the robot starts its automatic shutdown and ends the round.



## 5. Mobility Management

Mobility management in this project focuses on carefully selecting and implementing the motors, designing and assembling the 3D chassis, and integrating all components to ensure optimal performance.  
Key engineering principles considered include speed, torque, power efficiency, and structural strength.


## 6. Motor Selection and Implementation

**DC Motor 1.5 V:**  
- **Selection Process:**  
  The choice of the 1.5 V DC motor was based on its lightweight design and low power demand, which made it suitable for the robot’s compact size and for working with the L298N driver.

- **Pros:**  
  - Lightweight and compact  
  - Low power consumption, compatible with the battery  
  - Easy to mount and connect through the L298N

- **Cons:**  
  - Lower torque than larger motors  
  - Needs careful gear reduction to reach needed torque

**Servo Motor MG995:**  
- **Selection Criteria:**  
  The MG995 servo was chosen for its strength and ability to handle higher loads, making it perfect for steering and precise adjustments.

- **Gear System Integration:**  
  Just like the DC motor, a gear is attached to the servo shaft and linked to the steering mechanism through LEGO gears, allowing accurate directional control.
  
## 7. Implementation of Gear Systems

**DC Motor 1.5 V:**  
To convert the motor’s speed into controlled movement, a LEGO gear system was used. A gear is mounted on the motor shaft and meshes with another gear connected to the wheels. This reduction system helps manage speed and torque effectively, ensuring smooth and stable movement.

**Mounting Considerations:**  
The 3D chassis provides a strong but lightweight base to hold the motor securely while keeping the weight balanced.

**Servo Motor MG995:**  
The servo motor uses LEGO gears to control the steering mechanism. This setup provides precise control of the robot’s turning radius and direction.



## 8. Chassis Design and Component Mounting

**Chassis Selection:**  
The chassis was designed with 3D pieces to balance strength and weight, leaving enough space to hold the DC motor, servo, sensors, and wiring.

**Mounting of Components:**  
The motor, gears, and sensors are strategically mounted to keep the robot balanced. The DC motor is placed centrally for weight distribution, and the servo is positioned for effective steerin



## 9. Power and Sensor Management

The robot’s power system is centered around a **12 V LiPo battery**, chosen for its lightweight design and high energy capacity. It provides enough power to run the DC motor, servo, PixyCam, and sensors while maintaining good balance and efficiency. This battery replaced the old setup of four batteries in series because it delivers more stable power and reduces overall weight.

The robot’s sensors include three ultrasonic sensors and the **PixyCam L209**, selected for their accuracy and reliability in detecting obstacles and helping guide the robot through the course. The ultrasonic sensors are positioned to measure distances and detect objects to prevent collisions. The PixyCam is used for color tracking, enabling the robot to follow lines and make smart turns.

. This setup ensures a stable power supply to all parts, minimizes power loss, and keeps everything running reliably. For open challenge tests, the camera can be turned off to save energy if needed


**CHALLENGE**

This challenge motivates us to create and develop a working robot prototype aimed at addressing a real-life issue. It allows us to put into practice what we’ve learned about robotics, sensors, and coding, while also strengthening our creativity, collaboration, and technical skills through hands-on experience.
