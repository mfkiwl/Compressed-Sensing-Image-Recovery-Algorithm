<div align="center">
    <h2>Compressed Sensing Image Recovery</h2>
    <p>
        <img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" />
        <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black" />
        <img src="https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white" />
        <img src="https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white" />
        <img src="https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white" />
    </p>
    <p>
        Algorithmically sample corruption and recover the original image via <b>compressed sensing signal processing</b>.
    <p>
        Although there is no GUI built yet, this project is available for local installation and setup. I plan to continue this project and make something user-facing after I have more free time during the semester. :)
    </p>
    <p>
        <a href="background">Background</a> · <a href="getting-started">Getting Started</a>
    </p>
</div>

<div>
    <h2 id="background">Background</h2>
    <p>
        Suppose we are given an image. ​However, due to file corruption, or data loss, or mercury being in retrograde, our image is missing
pixels. A lot of pixels. The way that we intend to “recover” these pixels is through a process known as
compressed sensing image recovery. This is a signal processing technique which exploits the sparse
representation of coefficients of the image vector in a generic transform basis in order to reconstruct
the original uncorrupted image by solving an underdetermined system of equations for the sparsest
solution via L1 regression.
    </p>
    <p>
        For our 
image, each pixel is represented by its intensity on a particular scale. For our purposes, we will be
using a grayscale colormap with values linearly mapped from 0 to 255. Let’s call our complete image the
vector, <b>x</b>, where the 2D matrix of pixel intensities is rasterized into a single column vector.
    </p>
    <p>
        Our image has a sparse representation, <b>s</b>, in some transform basis different from our image’s
regression. We can infer
what the nonzero coefficients of s are such that we get the sparse representation in the transform basis,
and from that get the original image. This is the idea behind compressed sensing.
    </p>
    <p>
        More specifically, we are looking to solve this underdetermined system of equations by solving
for the sparsest solution of <b>s</b> in the transform basis, which allows us to arrive at a particular solution given by the L1-norm.
    </p>
</div>

<div>
    <h2 id="getting-started">Getting Started</h2>
    <p>
        Currently, there is no user-facing GUI built for this program (yet!). To run the algorithm, a manual download and setup of the Python file on your local machine is required. After downloading model.py, it is necessary to manually change the variable on line 333, originalImage, to the local path of your <b>COMPLETE, UNCORRUPTED</b> image. For small images, keep the variable <b>k = 8</b> on line 331. For larger images, change to <b>k = 16</b>.  
    </p>
    <p>
        For sampling corruption levels, change the variable <b>S</b> on line 330 to be the number of pixels per KxK block to remain. For example, for S = 50, k = 8, there will be 50 pixels remaining out of every 8x8 (64 total pixels) block in the image. For S = 10, k = 8, there will be a very corrupted result of 10 pixels remaining out of every 8x8 block.
    </p>
    <p>
        Run locally and save results.
    </p>
</div>
