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
