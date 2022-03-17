# Speech-Emotion
Speech is an interesting area in data science because there is both the words said and the tone of how they are said. In this repository, I will be using machine learning to evaluate emotion and tone in speech datasets in hope that it will be used to make more advanced chatbots.


### Data
In this project I will be using the [RAVDESS](https://zenodo.org/record/1188976) audio-only dataset. On the link provided you can download the dataset for yourself, and it shows all the necessary information on the data.

### Data Cleaning and Manipulation
First in this data I have had to reduce the sample rate to 16kHz, this was done by walking through the files with os.walk and using features from [ffmpeg](https://ffmpeg.org/) to reduce the sample rate and save to a new location. This is done in "audio_resampling.ipynb"

![image](https://user-images.githubusercontent.com/81537476/158723343-6d190c24-e578-4377-8017-370571b6143e.png)






