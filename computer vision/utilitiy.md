# Numpy for image processing 

value = img[i:j:k], where i,j are the coordinates and k is the color channel

## Image Slicing 
- im[i,:] = im[j,:] (set the values of row i with)   
- im[:,i] = 100 (set all values in column i to 100)
- im[:100,:50].sum() (the sum of the values of the first 100 rows and 50 columns)
- im[50:100,50:100] (rows 50-100, columns 50-100 (100th not included))
- im[i].mean()  (average of row i)
- im[:,-1] (last column)
- im[-2,:] (or im[-2]) (second to last row)
