ALEXA SPEECH RECOGNITION
🚀 Excited to Announce My Latest Project: Alexa Speech Recognition using Python! 🎉

I recently completed a fascinating project where I built a speech recognition assistant similar to Alexa using Python. This project was both challenging and rewarding, and I’m thrilled to share the details with you all.

🔍 Project Overview:

In this project, I created a voice-activated assistant that can perform a variety of tasks based on spoken commands. The assistant listens for the keyword "Alexa" and responds to several types of requests, such as playing music, providing the current time, fetching information from Wikipedia, and telling jokes.

🛠 Key Features:

Voice Activation: 
The assistant listens for the keyword "Alexa" and then processes the command.
Play Music:
It can play any song on YouTube based on the user's voice command.
Tell Time:
It provides the current time upon request.
Wikipedia Integration: 
It fetches and reads out summaries of famous personalities from Wikipedia.
Tell Jokes:
It can tell jokes to lighten the mood.
📚 Technologies and Libraries Used:

speech_recognition: For capturing and recognizing spoken commands.
pyttsx3: For converting text to speech, making the assistant respond vocally.
pywhatkit: For searching and playing YouTube videos.
datetime: For retrieving the current time.
wikipedia: For fetching summaries of famous personalities.
pyjokes: For generating and telling jokes.
🔧 How It Works:

LISTENING MODE: The assistant uses the speech_recognition library to listen for voice commands through the microphone.
COMMAND PROCESSING: Once the keyword "Alexa" is detected, it processes the rest of the command.
EXECUTING TASKS: Based on the command, it can:

Play a specified song on YouTube using pywhatkit.
Provide the current time using the datetime module.
Fetch a summary from Wikipedia using the wikipedia library.
Tell a joke using the pyjokes library.

Voice Feedback: The assistant uses pyttsx3 to give spoken feedback to the user.
🎯 Project Goals:

To explore and implement voice recognition technology.
To integrate various APIs and libraries to create a multi-functional assistant.
To enhance my Python programming skills and knowledge of speech processing.
🔗 Check it Out:

Libraries Used
speech_recognition for capturing and recognizing speech.
pyttsx3 for text-to-speech conversion.
pywhatkit for playing YouTube videos.
datetime for fetching the current time.
wikipedia for retrieving information.
pyjokes for generating jokes.

python code
import speech_recognition as sr
import pyttsx3
import pywhatkit
import datetime
import wikipedia
import pyjokes

listener = sr.Recognizer()
engine = pyttsx3.init()
voices = engine.getProperty("voices")
engine.setProperty("voice", voices[1].id)

def talk(text):
    engine.say(text)
    engine.runAndWait()

def alexa_command():
    try:
        with sr.Microphone() as source:
            print("Listening...")
            voice = listener.listen(source)
            command = listener.recognize_google(voice)
            command = command.lower()
            if "alexa" in command:
                command = command.replace("alexa", "")
                print(command)
    except:
        pass
    return command

def run_alexa():
    command = alexa_command()
    print(command)
    if "play" in command:
        song = command.replace("play", "")
        talk("Playing " + song)
        pywhatkit.playonyt(song)
    elif "time" in command:
        time = datetime.datetime.now().strftime("%H:%M")
        print(time)
        talk("Current time is " + time)
    elif "superstar" in command:
        person = command.replace("superstar", "")
        info = wikipedia.summary(person, 3)
        print(info)
        talk(info)
    elif "joke" in command:
        talk(pyjokes.get_joke())

run_alexa()



        
HOW TO RUN:
Clone the repository.
Install the required libraries using pip install -r requirements.txt.
Run the script using python alexa.py.
Start giving voice commands!
Future Enhancements
Adding more commands and functionalities.
Improving the speech recognition accuracy.
Integrating with other APIs for more features.
Feel free to contribute or provide feedback!

I’m excited about the potential of this project and look forward to adding more features in the future. Thank you for reading, and I hope you find this project as exciting as I do!

#Python #SpeechRecognition #Alexa #MachineLearning #ArtificialIntelligence #Coding #Project #VoiceAssistant

