# Compressed Sensing Image Recovery
## INTRODUCTION
Given a corrupted image with missing pixels, this project exploits the [sparsity](https://en.wikipedia.org/wiki/Sparse_matrix) in natural images to generate a prediction of the original image with the missing pixels filled in, or "recovered". Specifically, this is a signal processing technique known as [compressed sensing image reconstruction](https://en.wikipedia.org/wiki/Compressed_sensing). Median filtering is applied to the recovered image in order to smooth out the image in the interest of pursuing higher fidelity.

### Built With
- [NumPy](https://numpy.org/)
- [SciPy](https://scipy.org/)
- [SciKitLearn](https://scikit-learn.org/stable/)
- [Matplotlib](https://matplotlib.org/)

## DEMO
To first give an example of the project's capabilities before going more in depth into the methodology, our given test image of a fishing boat is 192x200 pixels. 

### Original Image
<img width="340" alt="image" src="https://github.com/elliothha/Compressed-Sensing-Image-Recovery/assets/125780179/5e97a963-b24b-4b56-9cca-0e16c5c1a0ff">

### Methodology
As a low-level overview of the methodology needed to thoroughly understand the context behind the images, in order to simulate "corruptness" in our original image for demonstration purposes, the fishing boat image was partitioned into KxK pixel blocks, where K = 8. In each of these KxK blocks, a certain number of pixels are randomly chosen and have their numerical color values set to zero in order to imitate "missing pixels". This number of pixels would depend on the value of S, where S = the amount of pixels to be retained in each block. The following images demonstrate this projects capabilities are varying levels of simulated "corruptness". Necessarily, for images that are already corrupted with missing pixels, this process is not necessary and we can simply consider the results. Each recovered image has [median filtering](https://docs.scipy.org/doc/scipy/reference/generated/scipy.signal.medfilt.html) applied to it with a kernel size of 3. A total mean squared error comparison is calculated between the two recovered images numerical color values.

### S = 50 Retained Pixels per KxK Block
<img width="1193" alt="Screenshot 2023-05-29 at 10 42 15 PM" src="https://github.com/elliothha/Compressed-Sensing-Image-Recovery/assets/125780179/3d3b6645-dcb0-4ae5-97a6-9064424ec356">

### S = 30 Retained Pixels per KxK Block
<img width="1185" alt="Screenshot 2023-05-29 at 10 45 16 PM" src="https://github.com/elliothha/Compressed-Sensing-Image-Recovery/assets/125780179/92d17b34-a0aa-4efe-9b2b-2adadd26b351">

### S = 10 Retained Pixels per KxK Block
<img width="1199" alt="Screenshot 2023-05-29 at 10 47 19 PM" src="https://github.com/elliothha/Compressed-Sensing-Image-Recovery/assets/125780179/37fc278e-4a5d-4b0a-a108-10662bb522c4">

## SETUP
1. Clone this repository using the following command:

    - `git clone https://github.com/elliothha/Compressed-Sensing-Image-Recovery.git`
    
2. Change into source directory

    - `cd src`
    
3. Upload corrupted image to directory

4. Install the following packages:

    - math
    - random
    - itertools
    - numpy
    - matplotlib
    - PIL
    - scipy
    - sklearn
    - warnings

## USAGE
### Input
1. In the main function, change the image in the following line of code to the local path of the uploaded corrupted image.
    - `originalImage = imgRead(file='C:/Users/elliot/PycharmProjects/pythonProject/fishing_boat.bmp')`
2.  Similarly, change the "k" value to either K = 8 or K = 16 depending on the size of the uploaded image.
    - `k = 8`

### Output
1. Download recovered image from the generated MatPlotLib plots.


