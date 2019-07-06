# Image-Captioning-Keras

It is a photo caption generator which generates text describing the given image .</br>

## How it works 



## Requirements
Python 3</br>
Keras(2.2.4)(Gpu-Version with Cuda and CuDnn installed)</br>
Tensorflow(1.9.0)</br>
Numpy</br>
Graphics Card( GE-Force 1050 Ti 4gb)</br>
RAM-16gb</br>


## Network Structure
![model;jpg](https://user-images.githubusercontent.com/34737471/60752799-77579100-9fe7-11e9-9654-a9cc6a5c1936.png)



## Using the Caption generator
1. Clone the repository
2. Change directory to the directory where the file generate_caption.py is located
3. To generate  a caption , enter the following command:

        python generate_caption.py /path/to/image/

## Result

### Image</br>
   ![390671130_09fdccd52f](https://user-images.githubusercontent.com/34737471/60752034-aa952280-9fdd-11e9-88f5-a795e56e4c6e.jpg)</br>
### Generated Text-startseq dog is running through the grass endseq</br>

### Image</br>
![bike](https://user-images.githubusercontent.com/34737471/60752269-217fea80-9fe1-11e9-9bdf-33f813cfd5b5.jpg)

### Generated Text-startseq man in red helmet is riding bike endseq</br>

### Image</br>
![fight](https://user-images.githubusercontent.com/34737471/60752296-483e2100-9fe1-11e9-846b-627064fc7a2d.jpg)
### Generated Text-startseq two men are playing soccer on the grass endseq</br>

### Image</br>
![play](https://user-images.githubusercontent.com/34737471/60752508-49bd1880-9fe4-11e9-9ea9-225fe6bb6b2d.jpg)
### Generated text - startseq two girls are playing instruments endseq</br>

Trained model can be fouond at {model}(https://drive.google.com/open?id=1sI8YyddKJqpdUIu4aTTLCcqy-gGQdY8l)<\br>

# References</br>
CS 231n-http://cs231n.stanford.edu/reports/2016/pdfs/362_Report.pdf</br>
Andrej Karpathy Talk-https://cs.stanford.edu/people/karpathy/sfmltalk.pdf</br>
Machine Learning Mastery-https://machinelearningmastery.com/
