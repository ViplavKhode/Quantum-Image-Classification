# Quantum Image Classification for Alzheimer's Detection
Qualz is a quantum computing algorithm that classifies MRI scans as "with dementia" or "no dementia." By utilizing quantum computing, it aims to enhance efficiency, especially in reducing space complexity compared to classical methods. This approach offers faster, scalable analysis, improving diagnostic accuracy and decision-making in healthcare

We use the [FRQI](https://learn.qiskit.org/course/ch-applications/flexible-representation-of-quantum-images-frqi) algorithm to represent an MRI scan image into quantum states and calculate a reference image of a scan with dementia. The reference image is derived from the mean of multiple images. Test images are compared against this reference image using a quantum algorithm that converts the image to quantum states via FRQI. We then calculate the fidelity between the reference image and a test image, convert this fidelity to euclidean distance, and classify the image based on a threshold.

## How to use

### Install the necessary packages
Install the necessary packages:

* `numpy`
* `matplotlib`
* `opencv-python`
* `qiskit`

### Download the dataset

Obtain MRI images from the Alzheimer's Dataset available at https://www.kaggle.com/datasets/marcopinamonti/alzheimer-mri-4-classes-dataset

### Run the notebooks

[`Theta_Values.ipynb`](https://github.com/ViplavKhode/Quantum-Image-Classification/blob/main/Theta_Values.ipynb) - This notebook contains the preprocessing of the grayscale image to vectors of theta values.

[`Quantum_Image_Classification.ipynb`](https://github.com/ViplavKhode/Quantum-Image-Classification/blob/main/Quantum_Image_Classification.ipynb) - This notebook contains the main quantum algorithm for measuring the similarity between an image and the reference image.

Run the `Theta_Values.ipynb` notebook to preprocess the grayscale image into vectors of theta values.
Run the `Quantum_Image_Classification.ipynb` notebook, which contains the algorithm that measures the similarity of an image with the reference image.
The output will be the likelihood of Alzheimer's disease in the test images.

### Web App (Concept)
A proof-of-concept web app takes in an MRI image and converts it to a list of theta values which can then get plugged into the quantum algorithm in `Quantum_Image_Classification.ipynb`. 


## Project Value
QuAlz provides an efficient approach to MRI scan analysis in terms of space complexity. Comparing our quantum computing algorithm with classical methods, we find that both have O(n) time complexity, where n is the number of pixels in an image. However, our quantum method has a space complexity of O(log_2 n) compared to O(n) in comparable classical methods, resulting in lower memory requirements. This can be valuable in healthcare settings, where efficient resource management and accurate diagnosis are essential.
