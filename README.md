# Ok__Googl
talkin computer

import speech_recognition as sr
import datetime
import wikipedia
import pyttsx3
import webbrowser
import random
import os
import chat
import wolframalpha
try:
    app = wolframalpha.Client("5L4Q6Y-HJEU3VPA4P")
except Exception:
    print("impore=t Error")
#Text To Speech

engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')
#print(voices)
engine.setProperty('voice',voices[0].id)
#################################################### done all setups for jarvish###################################


def speak(audio):
    engine.say(audio)
    engine.runAndWait()
def wish_me():
    time= int(datetime.now().hour)
    if 0 <= time >12:
        speak("good morning sir ")
    elif time >=12 and time<18:
        speak("good afternoon sir")
    else:
        speak("good evning sir")
    speak("i am your assistance sir , how can i help you")


def take_command():
    speak("write your query sir ")
    query = str(input("write your query sir"))
    return query
    
    ########################################  Function to speak ######################################################### 
    
