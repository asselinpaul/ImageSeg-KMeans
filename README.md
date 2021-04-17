# Image Segmentation using [k-means clustering](https://en.wikipedia.org/wiki/K-means_clustering)

The program reads in an image, segments it using K-Means clustering and outputs the segmented image.

```python imageSegmentation.py K inputImageFilename outputImageFilename iterations```

**example:** ```python imageSegmentation.py 3 output/tshirt.ppm output/tshirt_segmented.ppm  10```

It is worth playing with the number of iterations, low numbers will run quicker.

The result is an over-segmented image. With the correct parameters, it can be used to partition an image for further processing. Here is an example of that: [Make3D](http://make3d.cs.cornell.edu/index.html)

## Output
![Burma](output/burma.jpg)
![Burma](output/burma-segmented.jpg)

![Duomo](output/duomo.jpg)
![Duoma](output/duomo-segmented.jpg)

![tunnel](output/tunnel.png)
![tunnel](output/tunnel-segmented.png)

_cv2 is used only to accept image file of types .ppm an .pgm which are not supported by Image.open(inputName), whereas **Logic behind kmeans is written in python and no library has been used.**_

If you wish you can still use ```image = Image.open(inputName)``` instead of 
```
image = cv2.imread(inputName)
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
image = Image.fromarray(image)
```
if you are not using .ppm and .pgm and only using .jpg