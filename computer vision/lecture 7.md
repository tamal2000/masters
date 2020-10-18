# Optical Flow, Motion and Tracking

**Mid-level vision** 

## 1. Optical Flow and Motion
## 2. Tracking 

# Optical Flow and Motion 

## Optical Flow
start by estimating motion of each pixel separately and then will consider motion of entire image.  

### Why estimate motion: 
- track object behavior
- Correct for camera jitter (stabilization)
- Align images (mosaics)
- 3D shape reconstruction 
- Special effects 

### Problem definition of optical flow
- how to estimate pixel motion form image H to image P?
    - Solve pixel correspondence problem [nearby pixels of same color in I]
    - Color constancy
    - small motion
- Optical flow constraints (gray scale images)
    - brightness constancy: H(x,y) = I(x+u, y + v)
    - small motion: I(x-u, y_v) ≈ I(x,y) + dI/dy•u +dI/dy•v 
- Combining equations fro brightness and motion 
    - 0 = I<sub>t</sub> ▽I • [u v], u = dx/dt, v = dy/dt
    - the component fo the flow in the gradient direction 
    the component of the flow parallel to an edge is unknown
- **Aperture Problem** 
    - we can see only a small part at a time. 
    - solve: impose additional constraints: 
        - flow fields is smooth locally,
        - one meth0 ; small window 
- RGB version of solution
    - impose additional constraints
    - most common is the flow field is smooth locally
    oen method: pretend the pixel's neighbor have the same (u,v)
#### Lukas-Kanade flow
- prob: we have more equations than unknown 
- A d = b -> minimize `||Ad - b||^2`
- solution: Least squares problem: 
- minimize (A<sup>T</sup>A)d = A<sup>T</sup>b

- Aperture problem and Normal Flow 
     - A<sup>T</sup>A should be invertible
     - A<sup>T</sup>A should not be too small due to noise
     A<sup>T</sup>A should be well-conditioned 

- Local Patch Analysis    
- Observations: 
    - Can measure sensitivity by the just looking 
    - this tells us which pixels are easy to track 
- Challenges in Lukas - Kanade
    - Suppose A<sup>T</sup>A is easily invertible
    - Suppose there is not much noise in the image  
    When this two is now fllowd
    - brightness constancy is not satisfied
    - the motion in not small
    - a point doesnt not move like its neighbors: window size 
- Iterative Refinement
    1. Estimate velocity as each pixel by solving Lucas-Kandade equations
    2. Warp H towards I usin gthe estimate flow field
    3. repeat until convergence   
    Problems:
    - wraping is not easy
    - warp one images, takes derivative of the other
    - often useful to low-pass filter the images before motion estimation. 
- Optical flow: Aliasing: Temporal aliasing causes ambiguities in optical flow becauses images can have many pixels with the same intensity. 
    - Solve large motion first [coarse-to-fine] by lower the resolution. 
    - calculate to small motion
    - done few times 
- Summary: 
    - Break image up into squre blocks
    - Estimate translation for each block
    - use this to predict next frame, code difference 

# Tracking 
Template based tracking  
- tracking consists in searching from the target object in a frame comparing with a template image 
- we assume the template is fixed and given in advance. 
- Search Space:
    - aligh the tempalte with everypossible candidate region in the image. similarity measure 
    - search the target only in an area
- SSD and correlate
    - SSD is short for sum of squred 
    - corelation is measure is the cross-correlatins 
    - CAluculate SSD fro every y in a search window
    - Gradient descent 
- Mean shift tracking 




