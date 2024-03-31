<h1 style="font-size: xx-large; text-align: center;">FORWARD AND INVERSE KINEMATICS OF ARTICULATED MANIPULATOR</h1>


<hr>


## Project Course Portfolio

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
 <hr>



<br>

## I. Abstract of the Project<a name="abstract"></a>
Your abstract content goes here. Replace this text with your actual abstract.



<br>

## II. Introduction of the Project<a name="introduction"></a>

![432889743_458344376635490_3344111488579056072_n](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/4990b5fd-4de6-4f8b-9e64-4fab57a77057)

<div style="text-align: justify;">

### Introduction to Articulated Manipulator or Anthropomorphic Manipulator
 Welcome to the introduction of the Articulated Manipulator! In this section, we'll explore the fundamental components and functionalities of an articulated manipulator with three joint variables: twisting joint, revolute joint, and revolute joint.

### Purpose and Use
 Articulated manipulators are versatile robotic systems designed for precise and flexible manipulation tasks in various industries. Their primary purpose is to handle objects, perform assembly tasks, and execute complex maneuvers with accuracy and efficiency. These manipulators find applications in:

- Manufacturing: Assembling products on assembly lines, handling materials in production processes, and performing quality control inspections.
- Construction: Handling heavy materials, assisting in building structures, and executing tasks in hazardous environments.
- Research: Conducting experiments, exploring environments inaccessible to humans, and developing new robotics technologies.

### Components of an Articulated Manipulator
- Twisting Joint: The twisting joint allows continuous rotation around an axis, enabling the manipulator to twist or rotate freely. It provides the manipulator with the ability to orient itself and adjust its position dynamically, enhancing its adaptability to different tasks and environments.
- Revolute Joint: A revolute joint facilitates rotation around a fixed axis within a limited range or angle. Similar to the hinge of a door, it enables the manipulator to bend, pivot, and articulate at specific points. This joint adds flexibility to the manipulator's movements, allowing it to reach various positions and orientations within its workspace.
- Revolute Joint: Another revolute joint further enhances the manipulator's articulation and maneuverability. Operating independently, it provides additional degrees of freedom, expanding the manipulator's dexterity and agility. With multiple revolute joints, the manipulator gains increased versatility, making it capable of performing complex tasks requiring precise positioning and manipulation.

### Historical Context
 The development of articulated manipulators traces back to the mid-20th century, with significant advancements occurring in robotics research and industrial automation. Early manipulators were primarily designed for repetitive tasks in manufacturing environments. One notable example is the "Unimate," developed by George Devol and Joseph Engelberger in the 1950s, which became the first industrial robot to be employed in production lines.

### Advancements in Robotics Technology
 Articulated manipulators have played a pivotal role in advancing robotics technology. Over the decades, advancements in materials, sensors, and control systems have led to the evolution of these manipulators into highly sophisticated and versatile robotic systems. Today, they are integral to automation across various industries, driving innovation, improving efficiency, and expanding the possibilities of robotics applications.

</div>




<br>

## III. Degrees of Freedom of Articulated Manipulator<a name="degrees-of-freedom"></a>
In general, degrees of freedom (DOF) refers to the number of independent parameters or variables that define the configuration of a system. It represents the number of ways a mechanical system can move without violating any constraints. In physics and engineering, DOF is crucial for analyzing and understanding the behavior of various systems, including mechanical structures, molecules, and robots.

In robotics, degrees of freedom play a significant role in characterizing the motion capabilities of robotic systems. For a robot, degrees of freedom refers to the number of independent movements or axes along which it can move. Each degree of freedom corresponds to a specific type of motion the robot can perform, such as translation along a linear axis or rotation around a rotational axis.

The concept of degrees of freedom is essential for designing and controlling robots effectively. It helps engineers and researchers determine the kinematic structure of a robot, understand its workspace, and develop algorithms for motion planning and control. The degrees of freedom of a robot influence its agility, versatility, and ability to perform various tasks in different environments.

The following are ideal DOF
- A point in 2D: 2 DOF; in 3D: 3 DOF
- A Rigid Body in 3D: 6 DOF
- Planar Manipulator: 3 DOF
- Spatial Manipulator: 6 DOF

<br>

**Type of Manipulator Based on the number of DOF**
| **Manipulator Type** | **DOF (f)** |
| --------------- | --------------- |
| Under-actuated Manipulator    | Spatial manipulator with less than 6 DOF or a Planar manipulator with less than 3 DOF    |
| Ideal Manipulator    | Spatial manipulator with exactly 6 DOF or a Planar manipulator with exactly 3 DOF    |
| Redundant Manipulator    | Spatial manipulator with more than 6 DOF or a Planar manipulator with more than 3 DOF    |

<br>
<br>


| **Joint Classification** | **DOF (f)** | **Constraints c between two planar rigid bodies** | **Constraints c between two spatial rigid bodies** |
| --------------- | --------------- | --------------- | --------------- |
| Revolute (R)    | 1    | 2    | 5 |
| Prismatic (P)	    | 1    | 2    | 5 |
| Helical (H)    | 1    | N/A    | 5 |
| Cylindrical (C)    | 2    | N/A    | 4 |
| Universal (U)    | 2    | N/A    | 4 |
| Spherical (S)    | 3    | N/A    | 3 |

<br>

**DOF vs Mobility**
- If the DOF of a manipulator is more than the ideal or based on the calculation indicates a Redundant Manipulator, it will be called **MOBILITY**.

<br>

**Grubler's Criterion for Mobility/DOF of Planar Manipulator**

$$
M = 3n - \sum_{i=1}^{m}(3 - C_i)
$$


**Grubler's Criterion for Mobility/DOF of Spherical Manipulator**

$$
M = 6n - \sum_{i=1}^{m}(6 - C_i)
$$
 	
<br>

ANGELO PALAGAY DITO NUNG COMPUTATION



<br>

## IV. Kinematic Diagram and D-H Frame Assignment of Articulated Manipulator<a name="kinematic-diagram"></a>

In robotics, a kinematic diagram is a schematic representation used to visualize the structure and motion of a robotic manipulator. It illustrates the arrangement of joints and links in the manipulator, as well as the direction of motion allowed at each joint.

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

The Denavit-Hartenberg (D-H) frame assignment is commonly used in robotics to define the coordinate frames associated with each joint. This assignment simplifies the kinematic analysis of robotic manipulators by providing a systematic method for describing their geometry and motion.

### D-H Notation
Jacques Denavit and Richard Hartenberg introduced this convention in 1955 to standardize the coordinate frames for spatial linkages. D-H Notation is used to solve the forward kinematics of a mechanical manipulator.

### Frames
In a mechanical manipulator a coordinate system that the manipulator uses to know where it is and where to go. There are generally 3 types of frames used on a mechanical manipulator:
- Base (World) frame
- User frame
- Tool frame

### D-H Frame Rules
The following are used to assign frames in a kinematic diagram for applying D-H Notation.<br>
Rule 1: The z-axis must be the axis of rotation for a revolute / twisting joint or the direction of translation for a prismatic joint.<br>
Rule 2: The x-axis must be perpendicular both to its z-axis and the z-axis of the frame before it.<br>
Rule 3: Each x-axis must intersect the z-axis of the frame before it.<br>
Rules for complying with Rule 3:
 - Rotate the axis until it hits the other.
 - Or translate the axis until it hits the other.<br>
Rule 4: All frames must follow the right-hand rule.
![right hand rule](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/8ec7d673-452e-4d30-ab42-0b879ae9c8d7)


### Kinematic Diagram and D-H Frame Assignment

Below is the kinematic diagram and D-H frame assignment of the articulated manipulator with a twisting joint and 2 revolute joints:

ANGELO PALAGAY DITO





<br>

## V. D-H Parametric Table of Articulated Manipulator<a name="parametric-table"></a>
Paki Fill Up



<br>

## VI. HTM of Articulated Manipulator<a name="htm"></a>
Paki Fill  up



<br>

## VII. Inverse Kinematics of Articulated Manipulator<a name="inverse-kinematics"></a>
Paki Fill Up



<br>

## VIII. Forward and Inverse Kinematics GUI calculator of Articulated Manipulator<a name="gui-calculator"></a>
Paki Fill Up



<br>

## IX. References<a name="references"></a>
Paki Fill Up
