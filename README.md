# 2026-WRO-Future_Engineering-LCDMCFE

## Contents

- [Preface](#Preface)

- [Design plan](#Design-plan)

    - [Obstacle Avoidance System Design](#Obstacle-Avoidance-System-Design)

    - [Velosity Controling System Design](#Velosity-Controling-System-Design)

    - [Turning System Design](#Turning-System-Design)

- [Materials List](#Materials-List)

- [Team Photo](#Team-Photo)

- [Videos](#Videos)

    - [Anti-clockwise non-obstacle track](#Anti-clockwise-non-obstacle-track)

    - [Anti-clockwise obstacle track](#Anti-clockwise-obstacle-track)

- [Reference link](#Reference-link)

## Preface

We are students from the Tung Wah Group of Hospitals Lee Ching Tak Memorial College. This year, our team members are XXX, XXX, and XXX. This is our technical document. Our team consists of a group of students passionate about technology and robotics. We hope to explore how to use robots to solve real-world problems through innovative design, technology, and diverse perspectives. In the upcoming World Robot Competition (WRO), we will showcase our creativity and technical strength, striving for excellent results.

Therefore, our main goal in the WRO is to demonstrate our problem-solving abilities and teamwork. We aim to design and develop robots capable of solving real-world problems. We believe that only by constantly challenging ourselves can we achieve greater success. Every competition is a learning opportunity, and we will fully utilize these experiences to continuously improve and pursue excellence.

## Design plan

### Vehicle Chassis Selection

We used the WPL D12 as the chassis for this vehicle because there are more aftermarket parts available for the WPL D12 compared to other toy cars,thus offering greater modification potential.We also used the WPL D12 in 2024 and 2026,and itsexcellent handling and extremely small turning radius led us to decide to use it again.

### What upgrades were make to WPL D12?

We made upgrades,including the rear suspension,front steering servo,and brushless motor,but most importantly,we upgraded the mechanical differential rear axle.

#### Rear Suspension

We adopted a stiffer rear suspension to withstand greater loads,allowing us to install more sensors or other tools.

#### Front Steering Servo

This increases torque,resulting in faster cornering speeds and reducing the risk of hitting obstacles or walls due to slow cornering speeds.

#### Brushless Motor

This can increase torque.

#### Mechanical Differential Rear Axle

In 2024 and 2025, our vehicles lacked a mechanical differential rear axle. This caused a jamming effect when the front steering angle was too large, as both rear wheels were steering in the same direction. This year, however, we've installed a mechanical differential rear axle, allowing the two wheels to travel at different speeds, eliminating the jamming caused by excessive front steering angles.(You can find the sample video in the [other] file)

#### Visual Solutions

For this vehicle,we adopted a purely vision-based solution,so we chose to use the IMX219 camera for road and obstacle recognition because it works out of the box and supports jetson orin nano.

### Obstacle-Avoidance System Design

Use a ResNet18 to input camera image and generate steering angle. The ResNet18 AI model is trained with pictures that took with on board IMX219 camera and labelled manually to teach the model to turn correctly in different situation
<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/23140565-9eb8-437e-823f-192dfa11003c" />
After that we build a model of yolo to tell Orin Nneo what the object is and it can give action

A YOLO11n model is used to get the boundary box and label of the red/green obstacle. Once the yolo model recognized the obstacle and the obstacle is in range, the program will override ResNet18 model steering output, control car's steering base on obstacle's color and position.

In code,we make use of yolo model to identify object with different colour and follow the flow show in figure1.1
<img width="1728" height="1079" alt="image" src="https://github.com/user-attachments/assets/9bee869b-9a18-42a4-988b-1bf90bd7021d" />

### Velosity Controling System Design

### Turning System Design

## Materials List

## Team Photo

## Videos

### Anti-clockwise non-obstacle track

### Anti-clockwise obstacle track

## Reference link
