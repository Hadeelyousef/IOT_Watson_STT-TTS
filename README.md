# IOT_Watson_STT&TTS

The code was written for automated conversations using voice. Some **IBM Watson** services such as **Speech to Text** and **Text to Speech** were used.
I added a part that saves the speech taken from the user as a text in a **txt file**,

````
with open('MyText.txt', 'w') as f:
          f.write(data['results'][0]['alternatives'][0]['transcript'])
````
 
and then the next part takes the text and turns it into an **audio file (mp3)**.

````
with open ('MyText.txt', 'r') as f:
        t = f.readlines()
        t = [line.replace('\n','') for line in t]
        t = ''.join(str(line)for line in t)

with open ('./speech.mp3','wb') as audio_file:
        t = tts.synthesize(t,accept='audio/mp3',voice='en-US_AllisonV3Voice').get_result()
        audio_file.write(t.content)         
playsound('speech.mp3')
````
**This repository contains...**
- a _folder in which all the files that contain the required codes are placed_.
- _an image of the output_.
- _a video showing how it works_.
