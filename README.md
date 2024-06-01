# AI-FACE-DETECTION
This project focuses on developing a robust method for detecting AI-generated faces using advanced machine learning techniques. By implementing a Convolutional Neural Network (CNN) model, the system efficiently distinguishes between real and synthetic faces. The project employs custom data generators for real-time data augmentation and preprocessing, ensuring high accuracy and performance. Technologies used include Python, TensorFlow, Keras, OpenCV, NumPy, scikit-learn, and Matplotlib. This work contributes to AI security and authenticity verification, providing a reliable solution for detecting synthetic media.

## About the dataset:-
DATASET INFORMATIONS  :-
1. AI images ( Synthetic Faces High Quality (SFHQ) ) Link- https://www.kaggle.com/datasets/selfishgene/synthetic-faces-high-quality-sfhq-part-1
2. Real images ( Celebrity image dataset ) Link:- https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html
   
  Sizes of the images vary greatly through out the dataset 
  The real imgaes are taken from the Celeb face dataset which has many celebrity faces 
  The AI generated images has been taken from the Synthetic Faces High Quality (SFHQ) part 1 
  Both the datasets are open to the public and can be used for research porposes 

Note: The actual datasets contain approximately a million images. Running a model on that amount of data on local systems posed a great challenge, so a smaller sample of the same data was chosen to demonstrate the findings.
  
## Folder arrangment within the directory:-
Two separate folders were created for Real faces and AI faces. Within each folder, there are three subfolders: train, test, and val. Throughout the code, images are called from these folders and labeled appropriately based on their origin. For example, an image from AI_FACE/test indicates it is of AI origin and from the test dataset.  

## A few samples of the images in the dataset:-
![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/894fdccc-bd21-4e1c-8f34-565351cbfbf4)

## Normal classification method through CNN:-

The CNN contains 3 layers with ReLU activation functions, kept consistent throughout the process to ensure uniform results.

![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/469b4867-c5cb-44f4-b9e3-32e80af1ac3e)

  ![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/adbbc836-b40c-42c8-b0c5-89f59101275a)

## Testing the generalisability 
Despite using only 5000 images for training, 15,000 images from the dataset are available locally. Random images from the 15,000 were fed into the system to ensure the model encounters new images it has never seen before every third time (5k/15k).


![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/dde86c6f-be60-458b-9284-1e2112f11db9)

## Frequency Domain Feature Extraction

Frequency domain representation of images was employed in this project to enhance the accuracy and robustness of AI-generated versus real face detection. In the spatial domain, images are represented by pixel intensity values, which can be influenced by noise and irrelevant variations. However, the frequency domain captures image details at various levels of granularity, allowing for a more nuanced analysis of patterns and textures.Under this assumption i tried to extract these relevant informations and try andd feed it into the CNN .

AI-generated faces often exhibit subtle artifacts and inconsistencies that are not easily discernible in the spatial domain. By transforming images into the frequency domain, these artifacts become more pronounced and detectable. Techniques such as Discrete Fourier Transform (DFT) or Discrete Cosine Transform (DCT) decompose the image into its frequency components, highlighting repetitive structures and anomalies typical of synthetic images.

![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/126630d6-a631-44b7-b545-ce4db2c7d1f6)

### The output of the same :-
![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/e4a66bb4-15c2-4d6a-80c8-3f7d2f782993)
![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/8d1d9dfa-4e0f-4488-8082-5daae043dec4)

## Testing the generalisability 
Even though we had only taken 5000 images for training the model , I still had 15k images from the dataset in my local system , so i had decided to take a random input from the 15k images and feed it into the system . This would ensure that the model would be getting a new image it has never seen before every 1/3rd time .(5k/15k)

![image](https://github.com/Rahulkrishna-M/AI-FACE-DETECTION/assets/102946334/53cd688f-9acd-4a21-a7f1-fc4a4f08048c)


## Conclution:-

As evidenced by the outputs, the frequency domain excels at capturing relevant details, enabling more comprehensive feature extraction. This novel approach significantly improves detection accuracy for distinguishing AI-generated faces from real ones. While highly effective for this specific task, the applicability of frequency domain representation may vary for other image analysis tasks.


