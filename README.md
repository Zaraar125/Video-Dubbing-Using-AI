# Video Dubbing

## Project Overview
This project includes a custom pipeline that will help a user to dub a video in their desired language.
The project will not only allow the user to dub the video simply by changing the language but the newly generated
audio will also be properly mapped on the video character using Lip sync .

## Pipeline 
This project contains multiple pre-trained models and multiple libraries that are being used .
### Libraries
1. moviepy
2. librosa
3. numpy
4. IPython 
### Pre-trained Models
1. OpeaAI's Whisper
2. Coqui TTS
3. Tortoise TTS
4. Wav2Lip
### Approach
Following is a summarized version of the entire approach of the pipeline:
1. Upload your desired video (Should be less than 10 seconds )
2. **Audio** will extracted from the video
3. The audio will **transcribed** into the desired **language** selected by the user
4. The **transcribed text** and the **extracted audio** will be given to the TTS to generate a new audio in the desired language with the original audio as **referrenced audio**
5. This **newly generated audio** and the original **video** will be given to a pre-trained Lip Sync Model
6. Lip Sync Model will result in the same video translated into a new language selected by the user

### Deep Dub Updated
The previous file might some have some issues since i did this project last year. I have made a new notebook in which i changed from Tortoise TTS to Coqui TTS. There is a slight improvement in the execution time of the overall notebook.
Simply, you would have to change some file paths which are listed below: 
1. Video File Path
2. Muted Video File Path
3. Extracted Audio File Path
4. Translated Audio File Path
5. MAKE SURE TO ENABLE GPU IN GOOGLE COLLAB (THIS NOTEBOOK HAS NOT BEEN TESTED ON KAGGLE AND IT MAY OR MAY NOT WORK ON KAGGLE)
# Conclusion
There are some drawbacks in this notebook. It takes some time to even process a small video. It cant run without a GPU. New Text should'nt be too much long.
I was not able to find a direct Speech-to-Speech approach but will try to do it in the future.

## Referrences
1. The entire approach has been beautifully explained on Hugging Face in the Audio Procesing course. Following is the link : https://huggingface.co/learn/audio-course/en/chapter7/speech-to-speech
2. Following is the link to the Coqui TTS : https://github.com/coqui-ai/TTS
3. Follwing is the link for OpenAI's Whisper : https://github.com/openai/whisper
