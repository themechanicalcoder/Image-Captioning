# Image-Captioning-Keras

It is a photo caption generator which generates text describing the given image .</br>

## How it works 
1) First features from the image dataset are extracted using a pretrained model (VGG16) in this case and stored in a file called 'features.pkl'.This is done in the file 'features.py'</br>
</br>
2) Then the text is cleaned so that it is easier for the model to learn . The cleaning involves removing all the punctuations ,converting all uppercase letters to lower case letters removing words having length of one letter and then the description of each image is stored in 'descriptions.txt' . This is done in 'text.py'</br>
</br>
3)  For the model to generate we need a first kick off word and for the senntence to end we need a last kickoff word therefore we add "startseq" in the beginning of the string and "endseq" at the end of string .Each and every word is assigned a number and hence every sentence is converted into a vector. This is done using keras inbuilt Tokenizer . The created tokenizer is then stored in "tokenizer.pkl". This is done in "tok.py"</br>
</br>
4)Then sequences are created because we know for the lstm to work we need to divide the sentence into prefix arrays</br>.
For eg The sentence "startseq dog is running through the grass endseq" is divided into</br>

       x1            x2                                                                  y
       photo         startseq                                                           dog
       photo         startseq dog                                                       is
       photo         startseq dog is                                                    running
       photo         startseq dog is running                                            through
       photo         startseq dog is running through                                    the                      
       photo         startseq dog is running through the                                grass
       photo         startseq dog is running through the grass                          endseq
Then it is converted into sentence vector using the previously created tokenizer and finally it is fed into the neural network</br>
The output of the VGG16 is a 4096 vector which is processed by a dense layer of size 256 to give an output of 256 . The language model expects a vector of size 34 and which are fed into Embedding layer which outputs a vector of size 256 which is fed into a decoder and a final Dense layer of size 256 is added with activation function as softmax that makes the final prediction </br>
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
1. Clone the repository</br>
2. Change directory to the directory where the file generate_caption.py is located</br>
3. Download the pretrained model and place in the current working directory.</br>
4. To generate  a caption , enter the following command:</br>

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

Trained model can be found at [model](https://drive.google.com/open?id=1sI8YyddKJqpdUIu4aTTLCcqy-gGQdY8l)</br>

# References</br>
CS 231n-http://cs231n.stanford.edu/reports/2016/pdfs/362_Report.pdf</br>
Andrej Karpathy Talk-https://cs.stanford.edu/people/karpathy/sfmltalk.pdf</br>
Machine Learning Mastery-https://machinelearningmastery.com/
