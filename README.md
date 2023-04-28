# Measuring-Microplastics

To assess the size variation of our microplastic samples, we used image processing techniques from OpenCV in Python. We assessed five different microplastic samples: 10mm rods, 20mm rods, small nurdles, medium nurdles, and large nurdles. Code for the 10mm rods and medium nurdles is in this repository. We used a machine vision camera with a long-focal-length lens to take images of the particles.

We converted the images to grayscale and binarized them so the particles were white, and the background was black. We binarized the images with an adaptive threshold function in OpenCV. This function determines the threshold for a pixel based on a small neighboring region. This was preferable since the corners of the images we took were darker than other parts of the image. The binarized images were eroded and dilated to remove noise and isolate individual elements that appeared to be conjoined.

We calculated the contours (collection of all continuous points along the boundary of a white object) for each particle. The contours were subsequently used to calculate the size of the particles.

To calculate the length of the rods, we found the area of each particle and used the known width of the rods to calculate the length. To calculate the diameter of the nurdles, we found the area of each particle and used the area of a circle to identify the radius.
