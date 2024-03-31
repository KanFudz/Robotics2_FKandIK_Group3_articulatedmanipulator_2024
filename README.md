<h1 style="font-size: xx-large; text-align: center;">FORWARD AND INVERSE KINEMATICS OF ARTICULATED MANIPULATOR</h1><hr>
<h2>
 
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
<h2>
 
## I. Abstract of the Project<a name="abstract"></a></h2>
Your abstract content goes here. Replace this text with your actual abstract.



<br>
<h2>

## II. Introduction of the Project<a name="introduction"></a></h2>

![432889743_458344376635490_3344111488579056072_n](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/4990b5fd-4de6-4f8b-9e64-4fab57a77057)

<div style="text-align: justify;">

<h3>

### Introduction to Articulated Manipulator or Anthropomorphic Manipulator</h3>
 Welcome to the introduction of the Articulated Manipulator! In this section, we'll explore the fundamental components and functionalities of an articulated manipulator with three joint variables: twisting joint, revolute joint, and revolute joint.

<h3>
 
### Purpose and Use</h3>
 Articulated manipulators are versatile robotic systems designed for precise and flexible manipulation tasks in various industries. Their primary purpose is to handle objects, perform assembly tasks, and execute complex maneuvers with accuracy and efficiency. These manipulators find applications in:

- **Manufacturing:** Assembling products on assembly lines, handling materials in production processes, and performing quality control inspections.
- **Construction:** Handling heavy materials, assisting in building structures, and executing tasks in hazardous environments.
- **Research:** Conducting experiments, exploring environments inaccessible to humans, and developing new robotics technologies.

</h3>

<h3>

### Components of an Articulated Manipulator</h3>
- **Twisting Joint:** The twisting joint allows continuous rotation around an axis, enabling the manipulator to twist or rotate freely. It provides the manipulator with the ability to orient itself and adjust its position dynamically, enhancing its adaptability to different tasks and environments.
- **Revolute Joint:** A revolute joint facilitates rotation around a fixed axis within a limited range or angle. Similar to the hinge of a door, it enables the manipulator to bend, pivot, and articulate at specific points. This joint adds flexibility to the manipulator's movements, allowing it to reach various positions and orientations within its workspace.
- **Revolute Joint:** Another revolute joint further enhances the manipulator's articulation and maneuverability. Operating independently, it provides additional degrees of freedom, expanding the manipulator's dexterity and agility. With multiple revolute joints, the manipulator gains increased versatility, making it capable of performing complex tasks requiring precise positioning and manipulation.

<h3>

### Historical Context</h3>
 The development of articulated manipulators traces back to the mid-20th century, with significant advancements occurring in robotics research and industrial automation. Early manipulators were primarily designed for repetitive tasks in manufacturing environments. One notable example is the "Unimate," developed by George Devol and Joseph Engelberger in the 1950s, which became the first industrial robot to be employed in production lines.

<h3>

### Advancements in Robotics Technology</h3>
 Articulated manipulators have played a pivotal role in advancing robotics technology. Over the decades, advancements in materials, sensors, and control systems have led to the evolution of these manipulators into highly sophisticated and versatile robotic systems. Today, they are integral to automation across various industries, driving innovation, improving efficiency, and expanding the possibilities of robotics applications.

</div>




<br>
<h2>
 
## III. Degrees of Freedom of Articulated Manipulator<a name="degrees-of-freedom"></a></h2>
In general, degrees of freedom (DOF) refers to the number of independent parameters or variables that define the configuration of a system. It represents the number of ways a mechanical system can move without violating any constraints. In physics and engineering, DOF is crucial for analyzing and understanding the behavior of various systems, including mechanical structures, molecules, and robots.

In robotics, degrees of freedom play a significant role in characterizing the motion capabilities of robotic systems. For a robot, degrees of freedom refers to the number of independent movements or axes along which it can move. Each degree of freedom corresponds to a specific type of motion the robot can perform, such as translation along a linear axis or rotation around a rotational axis.

The concept of degrees of freedom is essential for designing and controlling robots effectively. It helps engineers and researchers determine the kinematic structure of a robot, understand its workspace, and develop algorithms for motion planning and control. The degrees of freedom of a robot influence its agility, versatility, and ability to perform various tasks in different environments.


<h3>
 
The following are ideal DOF
</h3>
- A point in 2D: 2 DOF; in 3D: 3 DOF<br>
- A Rigid Body in 3D: 6 DOF<br>
- Planar Manipulator: 3 DOF<br>
- Spatial Manipulator: 6 DOF

<br>

<h3>
 
**Type of Manipulator Based on the number of DOF**
</h3>

|**Manipulator Type** | **DOF (f)** |
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


<h3>

**DOF vs Mobility** 
</h3>
- If the DOF of a manipulator is more than the ideal or based on the calculation indicates a Redundant Manipulator, it will be called **MOBILITY**.

<br>

<h3>
 
**Grubler's Criterion for Mobility/DOF of Planar Manipulator**
</h3>

$$
M = 3n - \sum_{i=1}^{m}(3 - C_i)
$$


<h3>
 
**Grubler's Criterion for Mobility/DOF of Spherical Manipulator**
</h3>

$$
M = 6n - \sum_{i=1}^{m}(6 - C_i)
$$
 	
<br>

ANGELO PALAGAY DITO NUNG COMPUTATION



<br>

<h2>

## IV. Kinematic Diagram and D-H Frame Assignment of Articulated Manipulator<a name="kinematic-diagram"></a>
</h2>

In robotics, a kinematic diagram is a schematic representation used to visualize the structure and motion of a robotic manipulator. It illustrates the arrangement of joints and links in the manipulator, as well as the direction of motion allowed at each joint.



<h3>

### Purpose of Kinematic Diagrams
</h3>

Kinematic diagrams serve several purposes in robotics:

1. **Visualization**: They provide a clear visual representation of the robotic system, aiding in understanding its structure and movement capabilities.

2. **Design**: Engineers use kinematic diagrams during the design phase to plan the layout of joints and links, ensuring that the manipulator can achieve the desired range of motion.

3. **Analysis**: Kinematic diagrams are used in kinematic analysis to study the relationship between joint motions and end-effector positions.


<h3>
### Components of a Kinematic Diagram
</h3>

A typical kinematic diagram includes the following components:

1. **Links**: Represent the rigid bodies or segments of the manipulator connected by joints. They are usually depicted as line segments.

2. **Joints**: Represent the points of connection between adjacent links where motion occurs. Different types of joints allow different degrees of freedom and types of motion.

3. **Axes**: Indicate the axes of rotation or translation associated with each joint.


<h3>
### D-H Frame Assignment
</h3>

The Denavit-Hartenberg (D-H) frame assignment is commonly used in robotics to define the coordinate frames associated with each joint. This assignment simplifies the kinematic analysis of robotic manipulators by providing a systematic method for describing their geometry and motion.


<h3>
### D-H Notation
</h3>

**Jacques Denavit** and **Richard Hartenberg** introduced this convention in 1955 to standardize the coordinate frames for spatial linkages. D-H Notation is used to solve the forward kinematics of a mechanical manipulator.


<h3>

### Frames
</h3>
In a mechanical manipulator a coordinate system that the manipulator uses to know where it is and where to go. There are generally 3 types of frames used on a mechanical manipulator:

- **Base (World) frame**
- **User frame**
- **Tool frame**


<h3>

### D-H Frame Rules
</h3>
The following are used to assign frames in a kinematic diagram for applying D-H Notation.<br>

**Rule 1:** The z-axis must be the axis of rotation for a revolute / twisting joint or the direction of translation for a prismatic joint.<br>
**Rule 2:** The x-axis must be perpendicular both to its z-axis and the z-axis of the frame before it.<br>
**Rule 3:** Each x-axis must intersect the z-axis of the frame before it.<br>
**Rules for complying with Rule 3:**
 - Rotate the axis until it hits the other.
 - Or translate the axis until it hits the other.

**Rule 4:** All frames must follow the right-hand rule. <br>
![righthandrule](https://github.com/KanFudz/Robotics2_FKandIK_Group3_articulatedmanipulator_2024/assets/157684612/239bcd4a-81ac-41cb-b37c-17f9952bfb8d)




<h3>
 
### Kinematic Diagram and D-H Frame Assignment
</h3>

Below is the kinematic diagram and D-H frame assignment of the articulated manipulator with a twisting joint and 2 revolute joints:

ANGELO PALAGAY DITO





<br>
<h2>
 
## V. D-H Parametric Table of Articulated Manipulator<a name="parametric-table"></a></h2>

The Denavit-Hartenberg (D-H) parameters are used to describe the kinematic properties of robotic manipulators. They provide a standardized method for defining the coordinate frames and transformations between adjacent links in a manipulator.

### Purpose of D-H Parametric Table

The D-H parametric table organizes the D-H parameters associated with each joint of the manipulator. These parameters include:

1. **\( α \)**: Represents the rotation around \( X_n \) required to align \( Z_{n-1} \) with \( Z_n \), where \( α \) is the rotation about \( X_n \) for the joint..
2. **\( r \)**: Represents the distance from the origin of frame \( n-1 \) to frame \( n \) along the \( X_n \) direction.
3. **\( d \)**: Represents the distance from the origin of frame \( n-1 \) to frame \( n \) along the \( Z_{n-1} \) direction. For prismatic joints, \( d \) is the joint variable.
4. **\( θ \)**: Rotation around \( Z_{i-1} \) required to align \( X_{i-1} \) with \( X_i \), with \( θ_i \) as the joint variable for revolute or twisting joints.

### Components of the D-H Parametric Table

The D-H parametric table consists of rows corresponding to each joint of the manipulator. Each row includes the D-H parameters for that joint.

### Example D-H Parametric Table

| Joint | \( α \) | \( a \) | \( d \) | \( θ \) |
|-------|--------|-------|-------|-------|
| 1     | \( α_1 \) | \( a_1 \) | \( d_1 \) | \( θ_1 \) |
| 2     | \( α_2 \) | \( a_2 \) | \( d_2 \) | \( θ_2 \) |
| 3     | \( α_3 \) | \( a_3 \) | \( d_3 \) | \( θ_3 \) |
| ...   | ...    | ...   | ...   | ...   |

In this table:
- \( α_i \): Twist angle between the \( Z_{i-1} \) and \( Z_i \) axes.
- \( a_i \): Link length between the \( X_{i-1} \) and \( X_i \) axes.
- \( d_i \): Link offset along the \( Z_{i-1} \) axis.
- \( θ_i \): Joint angle about the \( Z_{i-1} \) axis.

Each row corresponds to a joint in the manipulator, and the parameters define the geometric relationship between adjacent links.

### Notes
- The number of rows in the D-H parametric table corresponds to the number of joints in the manipulator.
- The values of \( α \), \( a \), \( d \), and \( θ \) are determined based on the physical characteristics and configuration of the manipulator.







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
