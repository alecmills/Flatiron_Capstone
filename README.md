# Flatiron_Capstone
Drone Detection

The purpose of this project is to Detect a drone image in a background like it would for a classifier but it will also try to locate in the image where the drone is. 

	For The first step in the project we have taken in ~900 background images and 20 images of drones on a white background. Taking the background images and resizing them to 960x540 resolution. Then creating a mask to take the drone off of the white background to then place it randomly on top of the image.

	After the The background image and the drone image is ready to place the drone on the image, I need to randomly assign when in the image it will be placed. I did this by taking the size of the background image and subtracting the size of the drone then passing it to a random function. Before I can just place the drone on the image I will be keeping track of where it is located in Kitti format. Kitti format was designed for self driving cars. So each label stands for something different.  
label of what it is tracking. 
Truncation of the object. 
the Occlusion State: Occlusion state [ 0 = fully visible, 1 = partly visible, 2 = largely occluded, 3 = unknown].
Alpha value: this is the Observation angle on the object. 
Bounding Box Coordinates (4): [xmin, ymin, xmax, ymax]
3-D dimension (3): Height, width, length of the object (in meters)
Location (3): 3-D object location x, y, z in camera coordinates (in meters)
Rotation_y : Rotation ry around the Y-axis in camera coordinates
 Ex: 
car 0.00 0 -1.58 587.01 173.33 614.12 200.12 1.65 1.67 3.64 -0.65 1.71 46.70 -1.59
For the case of this project the only thing that matters for my labels is the bounding box. 
Ex:
	Drone 0.00 0 0.00 587.01 173.33 614.12 200.12 0.00 0.00 0.00 0.00 0.00 0.00 0.00
To keep track of where the drone is being placed I took the random number that was generated and added the size of the drone to find the x_max and y_max. When placing the drone in the image It will also create a file for the labels using the same name as the image with the txt extension.

For testing purposes to make sure that I have the drone correctly placed and the label file can locate the drone I have also drawn the bounding box around the image.  
