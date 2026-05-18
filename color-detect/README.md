# RUBIK CUBE COLOR RECOGNITION

## GENERAL PROCESS
- The purpose of this python script is to detect the colors of each face of the Rubik's cube, so that the robot can decide what the sequence of moves is going to be to solve it.

- We import as an image(e.g. .jpeg) all the faces of the cube. On the photo we create a 3x3 grid to detect all the 9 stickers of the cube.

- We use an HSV range to detect each color of the cube

## CUBES ROTATIONS & SCANNING PROCESS

The robot reads each face of the cube, starting by picking the cube with its left hand. 
We scan the first three faces of the cube with the left hand, and then we continue the process with the right hand. 

1. LEFT HAND SEQUENCE 
- The process begins with the **Front face**.
- The gripper of the robot is rotated 90° to the left so it can read the **right face**. 
- For the **back face** we have to bring the hand back to its initial position (90° to the right and rotate the cube 180°).

2. RIGHT HAND SEQUENCE
- The right hand takes control to scan the remaining faces.
- With the right hand we pick the cube, and we rotate it 90° to scan the **left face**
- Next a 90° rotation is made to the left to scan the **top face**
- Finally, we flip the cube by 180° to scan the **bottom face**.

The diagram below is how we see the cube when we unwrap it, following the sequence of the motions that we are using.

```
      +-------+
      |  TOP  |
+-----+-------+-----+-----+
|FRONT| RIGHT |BACK | LEFT|
+-----+-------+-----+-----+
      | BOTTOM|
      +-------+
```

### NOTE 
We have to keep in mind, that when we scan each face, most of them are rotated. So when we create the final string with all the colors detected, we have to rotate them according to the side. 

For example, the back side is 180° rotated. So we have to rotate the colors upside down.