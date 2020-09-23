# Lecture 5: Neighborhood Processing, Image Filtering

**Image Processing Operations:**Point-wise operation, neighborhood operation & Geometric operations. 
## Neighborhood Image Processing 
1. **Connected Component Analysis(CCA):** connected region extraction from a binary image computer region (geometric) properties.
   - Connected components Analysis is a multi class labeling operation. 
   - It performs the change from pixels to regions. 
   - All pixels in the same region are given the same label  
**Connected Component Operations:**
   - Two pixels p and q belong to the same connected components C if there is a sequence of 1-pixels where, p(0) = p, P(n) = q then p(i-1),P(i) = 1,.,n
   - Based on Graph Theory. 
**Types:**
- 4 connected: pixel connected right, left, up and down. 
- 8 connected: all connected sides and corner pixels
- Original Images
- Connected Components
**Applications**
- Label all pixels that are connected and 
- counting elements
- Medical image processing and identifying and labeling organs.
- Region property computation: Area, perimeter, centre of gravity, circularity, Major axis, minor axis, mean and standard deviation of radial distance, bounding box, extremal axis length from bounding box, second order momement(row, column, mixed)
  - Area: Sum of all pixel, A =∑∑b(ij)
  - Centre of mass: mean value of x and y 
  - Second Momentum: a = ∑∑i^2b_ij, b = 2 ∑∑ ij • b_ij, c = ∑∑j^2 b_ij
2. **Mathematical Morphology**
   1. **Dilation:** expands the connected sets of 1s of a binary image
      1. growing features
      2. filling holes 
      3. Edge Detection:
         1. dilate input image
         2. Subtract input image from details image
         3. edge remains 
   2. Erosion: shrinks the connected sets of 1s of a binary image. 
      1. shrinking features
      2. removing bridges and branches and small protrusions.  
      3. Edge detection, contour 
      4. separate objects and counting 
   3. Opening: is the compound operation of erosion follwed by dialation with same structure element. 
      1. opening the foreground pixels with a particular structuring element 
      2. use: 
         1. spot and noise removal
         2. less destructive:

   4. Closing: is the compund operation of dilation followed by erosion with the same structure elemetn. 
      1. closing the background pixels with the same element.  
      2. use:
         1. Removing holes
         2. tends to enlarge regions, shrink background 
         3. closes samall holes in foregound 
         4. detect defects 
   - **Definitions** Morphology is a brach of biology that studies the from and structure of animals and plants. Mathematical Morphology in image processing is used to extract image components for representation and description of regions shapes, such as boundaries, skeletons etc. 
   - **Structuring Elements** A structuring element is a shape mask used in the basic morphological operations. They can be any shape and size that is digitally representable and each has an origin. 
## Image Processing 
1. Image Filtering
   1. Linear Filtering
      1. Convolution
      2. Gaussian filter
   2. Nonlinear filters
      1. Median filter
      2. bilateral filter 
   3. Frequency domain analysis
      1. 2D FFT

Motivation: Noise Reduction 
- give a camera and a still scene, how can you reduce noise?
  - take lots of images and average them. 
  - a function that transform input image to desired output image. 
    - Linear filtering: for a linear system, each output is a leaner combination of all the input values. 
    - Moving average: 
      - replace each pixel with a wighed average of its neighborhood
      - the neighborhood mark is called a filter or a kernel
      - box filter 
    - handel the boarder:
      - zero, wrap, clamp, mirror, blurrded:zero, normalized zero, clamp, mirror
