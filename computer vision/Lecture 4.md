# Lecture 4: In place image processing and Reflection model

# In Place Image processing
- points-wise operations: the operation can be highlighted applied to each pixes without actually considering other pixels. So its like points wise operation. Example: `Histogram operation`. 
- Neighborhood operations. 
  - Spatial domain 
  - Frequency domain
  - Binary image analysis 
- Geometric operations. 
  - Rotation, translation, 

Digital Image: Image is represented in an array of pixes. each pixes represent the luminous or greyscale value. Any operation on it is called in place processing. 

I = f(x,y): R<sup>2</sup> -> R (grey image); or R<sup>2</sup> ->R<sup>w</sup> (Color Image). 

#Human eyes can identify 2D surface image better than 3d surface. 

## Point Operation 
- Operation on Pixel's value, 
- Context free
- operation can be performed on the image histogram. 
- Example $g(x,y) = \alpha . f(x,y) + \beta$ liner operation. 

## Neighborhood Operations
- Operation depends on pixel's value and its spatial neighbor.
- Context dependant
- Example $g(x,y) = \sum {f(i,j)/n}$ 

## Geometric Operations
- operation depends on pixel's coordinations. 
- independent of pixels value
- context free 
- Example: translation: $g(x,y) = f(x+a, y+b)$

## Histogram Operation (Point Operation)
`Histogram` of a digital image with gray values is discrete function P(r<sub>k</sub>) = n<sub>k</sub>/n. where n<sub>k</sub> number of pixels with gray values, n total number of pixels in the image.  
- The histogram function represents the fraction of the total number of pixels with respect to gray value.
- For color images histogram is represented by different color channel (RBG).
- Histogram provides a global description of the `appearance` of the image. 
- Histogram provides an approximation to the probability density.
- if most of the values are in left mean the image is dark. 
- Hight Contrast: uniform distribution of the histogram distribution. 
- HDR Image: 

## Histogram based Image enhancement/image edition
### Histogram modification 
Given a point operation: v<sub>b</sub> = M(v<sub>a</sub>)
- M(v<sub>a</sub>) mtakes any values of v<sub>a</sub> in image A and maps it into v<sub>b</sub> in imageB
- Requirement: The mapping M is a non descending function and M<sup>-1</sup> exists. 
- the area under H<sub>a</sub> between 0 and v<sub>a</sub> is equal to the area under H<sub>b</sub> between 0 and v<sub>b<sub>
- **Monotonicity:** if it is required to map the full gray-level range to its full range while keep the gray-level order. a non-decreasing monotonic mapping function can be used. (like sigmoid function) 
- **Contrast Enhancement:** If most of the gray-levels in the image are in [u1 u2], the following mapping increases the image contrast. The values u1 and u2 can be found by using the image's accumulated histogram. [like tanh function] 
- **Power-low transformations:** $S = cr^\gamma$
  - if γ is 1 nothing happens in the image
  - if γ is less than one then contrast in low light area will be enhance. highlight area will be really contracted. 
  - if γ is hight than the contrast of the highlight area will be enhanced and low light area will be contracted. 

### Histogram Equalization 
For a better visual discrimination of an image we would like to re-assign gray-levels so that gray-level resource will be optimally assigned. 
- Visual Contrast between objects depends on the their gray-level separation. 
- Goal: finding a gray-level transformation M(v):
  - The histogram H<sub>b</sub> is as flat as possible 
  - The order of gray-levels is maintained. 
  - Histogram bars are not fragmented 

### Histogram Matching
- Histogram matching is a process where an image is modified such that its histogram matches that of another (reference) image. 
- A common application of this is to match the images from two sensors with slightly different responses, or from a sensor whose response changes over time. 

### Histogram Binarisation:
- ony while and black colored image
- good for identifying figures
- good for edges, medical images
- good for handwriting, micro images


- **Thresholding**
  - Can be used for Background subtraction of find changes. 
  - blob detection.
  - intensity-based detection 
  - color-based detection 
  - It is a pixel labeling operation. 
  - It assigns a binary value to each pixel. 
    - Binary value 1: pixels have higher intensity values. 
    - Binary value 0: pixels have higher intensity values. 
  - Histogram analysis: separate background 
  - How to select threshold 
    - by selecting different one
    - heuristic binarisation algorithm  
    - K-L algorithm Gaussian distribution. 



<code>
[ix, map] = cv2.imread('fig1.jpg)   
cv2.imshow(ix)  
figure()  
ix=double(ix)  
h= histogram(ix)  
stem(0:255,h)  
</code>  

# Reflection Model
- Two view stereo: our left and right eyes see objects little differently, which makes the object look 3d.
  - Two camera taking same object(s). 
- Although human eyes can perssive 3d from 2d image.
  - single camera with multiple light sources [**Photometric Stereo**]    

## PhotoMetric Stereo
- We can develop: albedo, normal, normals with vector, shaded 3d rendering, textured 3d rendering. 
### Modeling Image Formation
Track a 'ray' of light all the way from light source to the sensor. 
- How light interacts with the scene
- how a pixel value is related to light energy in the world 
  - N: Surface Normal
  - L: direction towards the light source: Assumption light sources are parallel. Equivalent to an infinitely distance point source. 
  - V: direction towards the sensor 

### Lambertian Reflectance 
I = N • L  
Image intensity  = Surface normal • Light direction
Image intensity approx. cos(angle between N and L)
- Materials - Three forms: 
    - Ideal diffuse (Lambertion) 
    - Ideal Specular
    - Directional Diffuse
- Lambert's Law: I<sub>diffuse</sub> = I<sub>light</sub>k<sub>d</sub>cos($\theta$)
- Reflected energy is proportional to cosine of angle between L and N (incoming)
- Measured intensity is viewpoint-independent (outgoing)
- I = k<sub>d</sub> N • L  
1. Diffuse albedo: What fraction of incoming light is reflected. 
     - Scale factor
2. Light Intensity: how much light is arriving
3. Camera response function

### Single Image: Shape from Shading 
  - Assume k<sub>d</sub> is 1
  - cos<sup>-1</sup> is the angel between N and L 
  - normals and smoothness of normals 
   - **Note:** SDS doesn't work very well in practice due to assumptions are too restrictive, too much ambiguity in nontrivial scenes. 
### Multiple Images Photometric Stereo
- same object in with different light source. 
- L non singular invertible 
- stack all the images in same pixel points 

### Depth Map from Normal Map
- we can get depth from the surface normal using integration. 
- Get a similar equation for V2
  - Each normal gives us two linear constraints on z
  - compute z values by solving a matrix equation. 

### Determining Light Directions
- Place a mirror ball in the scene
- the location of the highlight is determined by the light source direction. 

### Bidirectional Reflectace 
### Surface REflection 

## Use 
- Face Analysis 
  - Synthesis of images 
    - Shape
    - Albedo
    - Expression
    - illumination
    - pose
  - Analysis against target image
    - change age of image
    - super impose faces 
    - skin color change
- Ogmented reality 
- ConvNet: Encoder-Decoder 

### Specular Reflection and Mirror BRDF 
### Phong Model: An Empirical Approximation






















