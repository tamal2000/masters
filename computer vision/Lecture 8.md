# Lecture 8: 
- Global / Geometric Operation
    - Global translations 
    - Image warping 
    - Image morphing 
- Image Sticking

# Global Operation 
## Transformation 
- Transformation: p<sup>'</sup> = **T**(p). This is call global operation because T is same for any point p. 
- Common linear Transformation: 
    - Translation: move the coordinate to new location. 
        - transformation on 3x3 matrix 
            - x<sup>'</sup> = x + t<sub>x</sub>
            - y<sup>'</sup> = y + t<sub>y</sub>
        - transformation is addition operation which is resource hungry. hence we want to change it to product operation. for doing so we can transform homogeneous coordination. 
            - represent 2 dim with 3 vectors 
            - [x, y] --homogeneous-coordination--> [x, y, 1]
    - Rotation: 
        - 2D operation: 
            - x<sup>'</sup> = x cos(𝜃) - y sin(𝜃)
            - y<sup>'</sup> = x sin(𝜃) + y cos(𝜃)
            - anchor point (0,0) default 
            - to rotate in different location, make the new location as the centre point. and after rotation transform change the center back. 
    - Scaling: multiplying each of image components with a scaler. 
        - Uniform: means the scaler is same in all components.
        - non uniform: means the scalers are different per component. 
        - scaling operation, x<sup>'</sup> = ax, y<sup>'</sup> = by. 
    - Shear: Skew towards x or y axis 
        - shear transformation in both direction is not done simultaneously . Because one of the shear function will be zero. we can do a QR decomposition. shear two direction will be rotation. 
    - Affine: linear transformation and translation
        - origian may or may not be the centre. 
        - lines maps to lines
        - ration is preserved. 
    - Perspective: 3d obj to 2d
        - origin may not be same
        - lines maps to lines
        - ration not maintain 
    - Ternsformation combination: combine the opeartions. 

## Warping 
- why?
    - texture mapping 
    - image processing 
    - image morphing/blending 
    - image mosaic 
    - image base modeling 
- coordinates of the reference image is mapped with coordinate of the target image. 
- control points: unique points on the reference and target image. 
- types:
    - rotation: 
    - similarity: 
    - Affine mapping 
- how to compute warping: 
    - Forward warping: changing reference image pixel based on target image. 
        - problem: 
            1. change may change value from int to float. round up to closest integer (splatting)
            2. holes: pixel may not have corresponding space. by inverse warping and interpolate color. 
    - Inverse warping: mapping from target image.  
    Note: Inverse warping is better as there is less chance of holes. but sometime its irreversible. 
- image morphing: 
