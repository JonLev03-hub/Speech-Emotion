# Speech-Emotion
Speech is an interesting area in data science because there is both the words said and the tone of how they are said. In this repository, I will be using machine learning to evaluate emotion and tone in speech datasets in hope that it will be used to make more advanced chatbots.


### Data
In this project I will be using the [RAVDESS](https://zenodo.org/record/1188976) audio-only dataset. On the link provided you can download the dataset for yourself, and it shows all the necessary information on the data.

### Data Cleaning and Manipulation
First in this data I have had to reduce the sample rate to 16kHz, this was done by walking through the files with os.walk and using features from [ffmpeg](https://ffmpeg.org/) to reduce the sample rate and save to a new location. This is done in "audio_resampling.ipynb"

![image](https://user-images.githubusercontent.com/81537476/160051501-f4f48fa6-570e-48d5-8ba8-88992f38abc8.png)

### Loading Data Features

I have created one function that can go through a data file and load our target features (mel, croma, mfccs) shown below.
  ![image](https://user-images.githubusercontent.com/81537476/160049903-be69b1e3-e30c-4a92-9c2c-2a46b5dcb408.png)

  To effectively use this I then created another function that is able to go through all of the files in an os.walk and then save the features to a numpy array. In this same step I had also added a few lines to sort through the emotions so that you would be able to choose what emotions can be displayed, and then save that to another numpy array for machine learning. This function is shown below. 
  
  ![image](https://user-images.githubusercontent.com/81537476/160050122-b704960f-a8d6-4f71-aab0-9fca0629ba9b.png)
  
 ### Machine Learning Model
The final step in this process was to create a machine learning model that could precict the emotion from speech and then test the accuracy. To make a simple model with MLPClassifier it just takes three lines so I first did this.
  
  ![image](https://user-images.githubusercontent.com/81537476/160050391-8416f812-8010-45b9-88d8-80607e2940e6.png)

  Because this first model didnt get the performance I was looking for in a model I then created a loop to go through a random assortment of combinations, saving the best models to a models file. 

![image](https://user-images.githubusercontent.com/81537476/160050443-cf1256bb-ada0-400d-8ed9-e831e5d7a38f.png)
  
 Its obvious that this isn't the most ideal way to test models. I could have gone with a more evolution based design with the fuction, or simply had enough experience with NLP to know how different models perform in this situation but with a 5 minute test this was able to achieve 82% accuracy predicting 4 emotions. For this experiment that is a high enough accuracy for this to be considered a success. 
  
  ### Future improvement
  
  In the fututre you would easily be able to gather more datasets to improve performance. With more data it may not be a bad idea to impliment a more concrete solution to the model testing such as an evolution based system compared to something that is completely random. 
  
  Another fun idea that could be done with this project is to pair it with live audio recordings to predict the emotion over the last three seconds of audio.

  
