# Exam preparation Computer Vision 
-------------

## Review old exam and identify the topics. 
- Total questions 4 
### Topics 
- **Reflection Models**
    - **Lambertian** reflection model. 
    - type of surface, matte can be describe 
    - viewpoint influence the amount of reflected light 
    - maximum intensity of the reflected light obtain. 
    - shading components in terms of intrinsic image decamp 
    - Calculate the coefficient a, b, c 
    - simply dichromatic **reflection model**. 
    - how to model glossy appearance 
    - color highlight is depeended on the color of the light source. 
    - filter for human perception. 
    sketch the spectral power distribution 
    - highlights is dependent on the color of the light source
    - how that R−G only depends on the surface reflectance (albedo)H

- **Photometric Invariants** 
    - dichromatic reflection model. independent of light source. 
    - Lambertian reflections model 
    - uncertainty for color model 

- **Filter and Image Features**
    - Convolution calculation 
    - different filters and their effect and usage. 
    - convoluting different filters 
    - compute fx, fy and gradient magnitude of image pachas 
    - compute autocorrelation
    - compute eigenvalues 

- **Object Classification, detection and performance**
    - Intensity values from image patches 
    - Compute y<sub>i</sub> using softmax with given weight matrix. 
    - What is daunting challenge for NN. 
    - depth of filter with padding/no padding. output size of activation map. 
    - different layers in CNN and AlexNet 
    - What is max pooling and when is it useful?
    - basic components of pipleline used in window-based object detection. 
    - Sliding-window approach - advantages/disadvantages. 
    - Compute precision-recall. 

# Lectures 1,2,3 & Exe 2 
- camera obscura is also known as camera `pinhole`. 
- A lense focuses light on to film or censer. 
- depth of filed total distance from focus plane to photo plane. 
- Camera coordinate: pinhole camera is the imager and the optical centre is the origin. 
-  (x,y,z) -> (x f/z, y f/z): f is the focal length 
- a point in cartesian is a ray in homogeneous coordinates. 

Note: 
- create a convolution script 
- 