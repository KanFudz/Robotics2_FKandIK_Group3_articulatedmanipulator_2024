<div align="center">
 
# **FORWARD AND INVERSE KINEMATICS OF ARTICULATED MANIPULATOR**

</div>
 
## Project Course Portfolio</h2>

[I. Abstract of the Project](#abstract)
<br>
[II. Introduction of the Project](#introduction)
 <br>
[III. Degrees of Freedom of Articulated Manipulator](#degrees-of-freedom)
 <br>
[IV. Kinematic Diagram and D-H Frame Assignment of Articulated Manipulator](#kinematic-diagram)
 <br>
[V. D-H Parametric Table of Articulated Manipulator](#parametric-table)
 <br>							
[VI. HTM of Articulated Manipulator](#htm)
 <br>
[VII. Inverse Kinematics of Articulated Manipulator](#inverse-kinematics)
 <br>
[VIII. Forward and Inverse Kinematics GUI calculator of Articulated Manipulator](#gui-calculator)
 <br>
[IX. References](#references)
<br>
[X. Group Members](#Group-Members)
<br>

<div align="justify">
 
## I. Abstract of the Project<a name="abstract"></a>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project explores the fundamental principles governing the motion control of articulated manipulators, focusing specifically on robotic arms equipped with rotary joints. Combining theoretical insights with practical implementations for a cohesive understanding of this dynamic field.
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;At the core of our exploration lies the concept of degrees of freedom (DOF), which dictates the manipulator's ability to perform independent movements. Building upon this foundation, we delve into the Denavit-Hartenberg (D-H) parameters, elucidating their role in constructing a D-H table. This table simplifies the derivation of the Homogeneous Transformation Matrix (HTM), a powerful tool for describing the manipulator's end-effector position and orientation relative to a base frame.
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Navigating through the complexities of manipulator kinematics, we tackle the challenging problem of inverse kinematics. By solving inverse kinematic equations, we establish a link between the manipulator's joint angles and the desired end-effector position and orientation.
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To enhance understanding and user interaction, we introduce a Python-based Graphical User Interface (GUI). This intuitive interface allows users to visualize the manipulator and solve both forward and inverse kinematics problems. The forward kinematics section computes the end-effector position and orientation for given joint angles, while the inverse kinematics section helps users determine the necessary joint angles to achieve a desired end-effector position and orientation.
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;By seamlessly integrating theory with hands-on application and facilitating user engagement, this project offers a cohesive exploration of manipulator kinematics, empowering users to understand and utilize these concepts effectively in practical robotics applications.
<br>
</div>

## II. Introduction of the Project<a name="introduction">

<div align="center">
 
![432889743_458344376635490_3344111488579056072_n](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/4990b5fd-4de6-4f8b-9e64-4fab57a77057)

</div>


### Introduction to Articulated Manipulator or Anthropomorphic Manipulator

<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Welcome to the introduction of the Articulated Manipulator! In this section, we'll explore the fundamental components and functionalities of an articulated manipulator with three joint variables: twisting joint, revolute joint, and revolute joint. 
</div>
 
### Purpose and Use
<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Articulated manipulators are versatile robotic systems designed for precise and flexible manipulation tasks in various industries. Their primary purpose is to handle objects, perform assembly tasks, and execute complex maneuvers with accuracy and efficiency. These manipulators find applications in:
</div>

- **Manufacturing:** Assembling products on assembly lines, handling materials in production processes, and performing quality control inspections.
- **Construction:** Handling heavy materials, assisting in building structures, and executing tasks in hazardous environments.
- **Research:** Conducting experiments, exploring environments inaccessible to humans, and developing new robotics technologies.


### Components of an Articulated Manipulator
<div align="justify">
 
- **Twisting Joint:** The twisting joint allows continuous rotation around an axis, enabling the manipulator to twist or rotate freely. It provides the manipulator with the ability to orient itself and adjust its position dynamically, enhancing its adaptability to different tasks and environments.
- **Revolute Joint:** A revolute joint facilitates rotation around a fixed axis within a limited range or angle. Similar to the hinge of a door, it enables the manipulator to bend, pivot, and articulate at specific points. This joint adds flexibility to the manipulator's movements, allowing it to reach various positions and orientations within its workspace.
- **Revolute Joint:** Another revolute joint further enhances the manipulator's articulation and maneuverability. Operating independently, it provides additional degrees of freedom, expanding the manipulator's dexterity and agility. With multiple revolute joints, the manipulator gains increased versatility, making it capable of performing complex tasks requiring precise positioning and manipulation.
</div>

### Historical Context
<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The development of articulated manipulators traces back to the mid-20th century, with significant advancements occurring in robotics research and industrial automation. Early manipulators were primarily designed for repetitive tasks in manufacturing environments. One notable example is the "Unimate," developed by George Devol and Joseph Engelberger in the 1950s, which became the first industrial robot to be employed in production lines.
</div>

### Advancements in Robotics Technology
<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Articulated manipulators have played a pivotal role in advancing robotics technology. Over the decades, advancements in materials, sensors, and control systems have led to the evolution of these manipulators into highly sophisticated and versatile robotic systems. Today, they are integral to automation across various industries, driving innovation, improving efficiency, and expanding the possibilities of robotics applications.
</div>


<br>

## III. Degrees of Freedom of Articulated Manipulator<a name="degrees-of-freedom"></a>
<div align="justify">
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In general, degrees of freedom (DOF) refers to the number of independent parameters or variables that define the configuration of a system. It represents the number of ways a mechanical system can move without violating any constraints. In physics and engineering, DOF is crucial for analyzing and understanding the behavior of various systems, including mechanical structures, molecules, and robots.
</div>

<br>
 
<div align="justify">
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In robotics, degrees of freedom play a significant role in characterizing the motion capabilities of robotic systems. For a robot, degrees of freedom refers to the number of independent movements or axes along which it can move. Each degree of freedom corresponds to a specific type of motion the robot can perform, such as translation along a linear axis or rotation around a rotational axis.
</div>

<br>

<div align="justify">
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The concept of degrees of freedom is essential for designing and controlling robots effectively. It helps engineers and researchers determine the kinematic structure of a robot, understand its workspace, and develop algorithms for motion planning and control. The degrees of freedom of a robot influence its agility, versatility, and ability to perform various tasks in different environments.
</div>
 
### The following are ideal DOF:
- A point in 2D: 2 DOF; in 3D: 3 DOF<br>
- A Rigid Body in 3D: 6 DOF<br>
- Planar Manipulator: 3 DOF<br>
- Spatial Manipulator: 6 DOF

<br>
 
### **Type of Manipulator Based on the number of DOF**

<div align="center">
 
|**Manipulator Type** | **DOF (f)** |
| --------------- | --------------- |
| Under-actuated Manipulator    | Spatial manipulator with less than 6 DOF or a Planar manipulator with less than 3 DOF    |
| Ideal Manipulator    | Spatial manipulator with exactly 6 DOF or a Planar manipulator with exactly 3 DOF    |
| Redundant Manipulator    | Spatial manipulator with more than 6 DOF or a Planar manipulator with more than 3 DOF    |
</div>

<br>
<br>

### **Joint Classification and DOF**

<div align="center">
 
| **Joint Classification** | **DOF (f)** | **Constraints c between two planar rigid bodies** | **Constraints c between two spatial rigid bodies** |
| --------------- | --------------- | --------------- | --------------- |
| Revolute (R)    | 1    | 2    | 5 |
| Prismatic (P)	    | 1    | 2    | 5 |
| Helical (H)    | 1    | N/A    | 5 |
| Cylindrical (C)    | 2    | N/A    | 4 |
| Universal (U)    | 2    | N/A    | 4 |
| Spherical (S)    | 3    | N/A    | 3 |
</div>

<br>


### **DOF vs Mobility** 

- If the DOF of a manipulator is more than the ideal or based on the calculation indicates a Redundant Manipulator, it will be called **MOBILITY**.

<br>
 
### **Grubler's Criterion for Mobility/DOF of Planar Manipulator**


$$
M = 3n - \sum_{i=1}^{m}(3 - C_i)
$$


### **Grubler's Criterion for Mobility/DOF of Spatial Manipulator**

$$
M = 6n - \sum_{i=1}^{m}(6 - C_i)
$$
 	
<br>

**The image below is the computation of Degrees of Freedom of RRR Articulated manipulator which is a spatial manipulator. So we are to use the formula**


$$
M = 6n - \sum_{i=1}^{m}(6 - C_i)
$$

<br>
<br>

<div align="center">
 
![DOF](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/0631420d-9b88-43fb-b8e7-8c210785d515)
</div>

<div align="center">
 
### Step-by-step process of solving the Degrees of Freedom of Articulated manipulator

[![Step-by-step process of solving the Degrees of Freedom of Articulated manipulator](https://img.youtube.com/vi/g7lCQ4IBkvA/0.jpg)](https://www.youtube.com/watch?v=g7lCQ4IBkvA)

Click on the image above to watch the video.
</div>

<br>

## IV. Kinematic Diagram and D-H Frame Assignment of Articulated Manipulator<a name="kinematic-diagram"></a>
<div align="justify">
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In robotics, a kinematic diagram is a schematic representation used to visualize the structure and motion of a robotic manipulator. It illustrates the arrangement of joints and links in the manipulator, as well as the direction of motion allowed at each joint.
</div>

### Purpose of Kinematic Diagrams

Kinematic diagrams serve several purposes in robotics:

1. **Visualization**: They provide a clear visual representation of the robotic system, aiding in understanding its structure and movement capabilities.

2. **Design**: Engineers use kinematic diagrams during the design phase to plan the layout of joints and links, ensuring that the manipulator can achieve the desired range of motion.

3. **Analysis**: Kinematic diagrams are used in kinematic analysis to study the relationship between joint motions and end-effector positions.

 
### Components of a Kinematic Diagram

A typical kinematic diagram includes the following components:

1. **Links**: Represent the rigid bodies or segments of the manipulator connected by joints. They are usually depicted as line segments.

2. **Joints**: Represent the points of connection between adjacent links where motion occurs. Different types of joints allow different degrees of freedom and types of motion.

3. **Axes**: Indicate the axes of rotation or translation associated with each joint.


 
### D-H Frame Assignment

<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Denavit-Hartenberg (D-H) frame assignment is commonly used in robotics to define the coordinate frames associated with each joint. This assignment simplifies the kinematic analysis of robotic manipulators by providing a systematic method for describing their geometry and motion.
</div>
 
### Frames

<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In a mechanical manipulator a coordinate system that the manipulator uses to know where it is and where to go. There are generally 3 types of frames used on a mechanical manipulator:
</div>

- **Base (World) frame**
- **User frame**
- **Tool frame**




### D-H Frame Rules

The following are used to assign frames in a kinematic diagram for applying D-H Notation.<br>

**Rule 1:** The z-axis must be the axis of rotation for a revolute / twisting joint or the direction of translation for a prismatic joint.<br>
**Rule 2:** The x-axis must be perpendicular both to its z-axis and the z-axis of the frame before it.<br>
**Rule 3:** Each x-axis must intersect the z-axis of the frame before it.<br>
**Rules for complying with Rule 3:**
 - Rotate the axis until it hits the other.
 - Or translate the axis until it hits the other.

**Rule 4:** All frames must follow the right-hand rule. <br>
<div align="center">
 
![righthandrule](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/239bcd4a-81ac-41cb-b37c-17f9952bfb8d)
</div>
 
### Kinematic Diagram and D-H Frame Assignment
<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Below is the kinematic diagram and D-H frame assignment of the articulated manipulator with a twisting joint and 2 revolute joints. Wherein Links, Joint Variables, Z, X, Y axis are identified.
</div>

<br>
<div align="center">

![Screenshot 2024-04-02 101920](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/202b4767-da41-4d16-84e7-3a760072f749)


### Watch the Video

[![Video Thumbnail](https://img.youtube.com/vi/gjgQ8rGPYRs/0.jpg)](https://www.youtube.com/watch?v=gjgQ8rGPYRs)

Click on the image above to watch the video.


</div>
<br>
 
## V. D-H Parametric Table of Articulated Manipulator<a name="parametric-table"></a>

<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Denavit-Hartenberg (D-H) parameters are used to describe the kinematic properties of robotic manipulators. They provide a standardized method for defining the coordinate frames and transformations between adjacent links in a manipulator.
</div>

### D-H Notation
<div align="justify">
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Jacques Denavit** and **Richard Hartenberg** introduced this convention in 1955 to standardize the coordinate frames for spatial linkages. D-H Notation is used to solve the forward kinematics of a mechanical manipulator.
</div>

<div align="justify">
 
### Steps in Denavit-Hartenberg Notation
1. Assign the frames according to the 4 D-H Frame Rules.
2. Construct and fill out the D-H Parametric Table.
3. Plug the table into the Homogeneous Transformation Matrix form.
4. Multiply the matrices together.


### Purpose of D-H Parametric Table


The D-H parametric table organizes the D-H parameters associated with each manipulator joint. These parameters include:

1. "**α**" is the rotation around X<sub>n</sub> required to align Z<sub>n-1</sub> with Z<sub>n</sub>, where α is the rotation about X<sub>n</sub> for the joint.

2. "**r**" is the distance from the origin of frame n-1 to frame n along the X<sub>n</sub> direction.

3. "**d**" is Represents the distance from the origin of frame n-1 to frame n along the Z<sub>n-1</sub> direction. For prismatic joints, d is the joint variable.

4. "**θ**" is Rotation around Z<sub>n-1</sub> required to align X<sub>n-1</sub> with X<sub>n</sub>, with θ as the joint variable for revolute or twisting joints.
</div>

### Components of the D-H Parametric Table

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The D-H parametric table consists of rows corresponding to each joint of the manipulator. Each row includes the D-H parameters for that joint.

### D-H Parametric Table of Articulated Manipulator
<div align="center">
 
![Screenshot 2024-04-02 101927](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/567a5b41-1098-47a3-96f4-dfe08b736ef3)
</div>

This table shows the Homogeneous Transformation Matrix from frame 0 to frame 3. Theta, Alpha, r, and d of Articulated Manipulator

Each row corresponds to a joint in the manipulator, and the parameters define the geometric relationship between adjacent links.

<div align="center">

### Watch the Video

[![Video Thumbnail](https://img.youtube.com/vi/TiDLddG-bKc/0.jpg)](https://www.youtube.com/watch?v=TiDLddG-bKc)

Click on the image above to watch the video.
</div>

<br>

 
## VI. HTM of Articulated Manipulator<a name="htm"></a>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In robotics, the Homogeneous Transformation Matrix (HTM) is a mathematical representation used to describe the transformation between coordinate frames in a robotic system. It allows us to represent the position and orientation of one coordinate frame relative to another.

 
### Concept
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The HTM is a 4x4 matrix that combines rotation and translation transformations. It enables us to express both the position (translation) and orientation (rotation) of a coordinate frame relative to another coordinate frame.
 
The images below are the computation of the Homogeneous Transformation Matrix of Articulated Manipulator
<div align="center">
 
![HTM1](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/c078fed1-b4a9-445a-b752-b06cd6acdd54)
![HTM2](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/89d03ab2-9463-4ad7-832d-454189ce2813)

### How to solve HTM of Articulated manipulator

[![Video Thumbnail](https://img.youtube.com/vi/xQnQXaHRIYk/0.jpg)](https://www.youtube.com/watch?v=xQnQXaHRIYk)

Click on the image above to watch the video.


</div>

<br>

 
## VII. Inverse Kinematics of Articulated Manipulator<a name="inverse-kinematics"></a>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Both Inverse Kinematics and Forward Kinematics are used to make a mechanical manipulator move. The difference between them is that in Forward Kinematics, the given inputs are Joint Variables and by using the Homogeneous Transformation Matrix we can get the output which is Position Vector. In Inverse Kinematics, the given is the Position Vector and the output is Joint Variables.

**The image below is the computation of each equation for Articulated Manipulator in Top View**
<br>
<div align="center">
 
![INV1](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/2072741b-b4e9-48a5-b0cb-d4e277255611)
</div>

**The images below are the computation of each equation for Articulated Manipulator in Front View**

<div align="center">
 
![INV2](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/dc018f20-ddf5-49e3-85a6-6bf237a15956)
![INV3](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157782959/e62e87fb-ea0d-4131-9d43-433cc6b1e6db)

### Watch the Video

[![Video Thumbnail](https://img.youtube.com/vi/38Otr9qVn1o/0.jpg)](https://www.youtube.com/watch?v=38Otr9qVn1o)

Click on the image above to watch the video.


</div>
<br>

## VIII. Forward and Inverse Kinematics GUI calculator of Articulated Manipulator<a name="gui-calculator"></a>

### Description
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Articulated Manipulator Calculator is a tool designed to facilitate kinematics calculations for articulated manipulators. This calculator provides a user-friendly interface for performing both forward and inverse kinematics analyses, enabling users to determine the position and orientation of the end-effector given the joint parameters or vice versa.

### Key Features

- **Forward Kinematics Button**: Shows a section for Link lengths and Joint variables (input), Position Vector (output), Calculate Button, and Reset Button. <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Calculate Button**: Calculates the position and orientation of the end-effector based on the joint parameters (link lengths and joint angles).<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Reset Button**: Empties the input and output fields.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Articulated Manipulator Simulation**: As a result of the Forward Kinematics Calculation, a simulation reflecting the input and output values is presented.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Messagebox For Error**: Shows a predetermined message if the inputs on the entry field are invalid.<br>

- **Inverse Kinematics**: Shows a section for Link lengths and Position Vector (input), Joint Variables Orientation (output), Calculate Button, and Reset Button. <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Calculate Button**: Computes the joint parameters required to achieve a desired position and orientation of the end-effector.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Reset Button**: Empties the input and output fields.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Articulated Manipulator Simulation**: As a result of the Forward Kinematics Calculation, a simulation reflecting the input and output values is presented.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - **Messagebox For Error**: Shows a predetermined message if the inputs on the entry field are invalid.<br>

### Benefits

- **Ease of Use**: The graphical user interface simplifies the input of parameters and visualization of results, making kinematics calculations more accessible.
  
- **Efficiency**: By automating kinematics calculations, the calculator reduces the time and effort required to analyze the manipulator's motion.
  
- **Visualization**: Users can visualize the manipulator's movements and configurations through the graphical interface, aiding in understanding and analysis.

### Dependencies

- **numpy**: Required for numerical computations.
  
- **matplotlib**: Used for visualization purposes.
  
- **roboticstoolbox**: A Python toolbox for robot manipulators, providing functions for kinematics calculations.
  
- **tkinter**: Used for creating the graphical user interface.

- **messagebox**: Used to create a messagebox for errors in the input field.

- **PhotoImage**: Used to create a background using a photo.


### GUI Color Palette
<div align="center">
 
![15773625-2bbe-4b32-b30f-c6a049a4ec2c](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/39504e36-4872-4113-89a6-5e02bab6458a)

</div>

#012228<br>
#032b28<br>
#0d3f2e<br>
#1f563e<br>
#136345<br>
#117955<br>
#3e8e6f<br>
#539d85<br>
#65ae91<br>
<br>

<div align="center">
 
![f2044472-a2e4-49a1-8387-284820694157](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/235eff19-ccdd-4a09-bc2f-9915cb2073a8)

</div>

#220203<br>
#380506<br>
#540f0d<br>
#6b0500<br>
#87080a<br>
#980b06<br>
#ae120a<br>
#c02a2a<br>
#d04346<br>

### Note
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensure that all input parameters are provided accurately to obtain correct kinematics solutions. Additionally, familiarize yourself with the limitations and assumptions of kinematics models used in the calculations.


## IX. References<a name="references"></a>

https://www.youtube.com/watch?v=i1wgyfCF-aI&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=7

https://www.youtube.com/watch?v=TKS_x3J55C8&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=8

https://www.youtube.com/watch?v=x4UnKbk0DU4&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=9

https://www.youtube.com/watch?v=pqprqrhFgDY&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=15

https://www.youtube.com/watch?v=pHSkcTVnjzE&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=35

https://www.youtube.com/watch?v=ri3Er5HdnEk&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=31

https://www.youtube.com/watch?v=caK3hJHN_CE&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=32

https://www.youtube.com/watch?v=Jj5pqbQWKuE&list=PLUgsbeZHs9qPc44a8O7MIcecCjpJteFwq&index=51

https://www.youtube.com/watch?v=0u2MycVhZSU&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=21

https://www.youtube.com/watch?v=QprI0SRvqSk&list=PLUgsbeZHs9qNk2rwPdRH-kn6eUQlJJl5c&index=27

https://youtube.com/watch?v=PBD06Toaymw&si=DnEPvbjfd-WdqmPv

## X. Group Members<a name="Group-Members"></a>

1. Comia, Alexandria B. (21-07197)
2. Hernandez
3. Malabanan, Angelo Louis D. (21-04184)
4. Malata, John Rei R. (21-08864)
5. Medrano
</div>
