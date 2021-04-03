# Ok__Googl
talkin computer

import speech_recognition as sr     //this is used to recognise your voice thgrough microphone in your laptop or computer . For this you have to install pyAudio to enable your 
                                    computer to listen to your voice .
import datetime                     // for date - time purpose .
import wikipedia                    // first install . it will extract data from wikipedia directly
import pyttsx                      // to convert text to speech 
import webbrowser                  // first install it . It will allow python to search anything through your default webbrowser
import random                      // to generate some random number
import os                         
import chat                        // its a oython file that i have created . and after that i just imported it another file of python.
import wolframalpha                //it is a app that will go=ive you some kind of extra latest thing like Temperature , about some of importent personalities , math stuff etc
try:
    app = wolframalpha.Client("API")                 // taking authentication from the app 
except Exception:
    print("import Error")

#Text To Speech
engine = pyttsx3.init('sapi5')                      // initialising my pyttsx3 
voices = engine.getProperty('voices')               //taking voice as its property
#print(voices)                                      // i can print voice name thats on your laptop or pc
engine.setProperty('voice',voices[0].id)             // taking first voice from my computer
#################################################### done all setups for jarvish###################################


def speak(audio):                                   // function that will take a string as an argument and speak the same string in a sound you choose.
    engine.say(audio)                               //  call speak
    engine.runAndWait()
def wish_me():                                      // it will wish me according to time now
    time= int(datetime.now().hour)
    if 0 <= time >12:
        speak("good morning sir ")
    elif time >=12 and time<18:
        speak("good afternoon sir")
    else:
        speak("good evning sir")
    speak("i am your assistance sir , how can i help you")


def take_command():                                 // taking command that you want to search or execute
    speak("write your query sir ")
    query = str(input("write your query sir"))       // taking as an input
    return query
    
    ########################################  Function to speak ######################################################### 
    
if __name__ == '__main__':
    #wish_me()                                          //wishing me
    speak(" how u doing sir ")                          //asking me how i am 
    while True:
        query = take_command().lower()
        if "wikipedia" in query:
            speak("searching wikipedia ")
            query = query.replace("wikipedia"," ")
            result = wikipedia.summary(query,sentences= 2)
            speak("According to wikipedia")
            #print(result)
            speak(result)
        elif 'youtube' in query:
            webbrowser.open("http://youtube.com")
        elif 'google' in query:
            webbrowser.open("http://google.com")
        elif "adafruit" in query:
            webbrowser.open("https://io.adafruit.com/")
        #elif "gmail" in query:
            #    speak("what should i say")
            #    content = take_command()
            #    send_mail(content)
        elif "open code " in query:
            path = "C:\\Users\\welcome\\AppData\\Local\\Programs\\Microsoft VS Code\\Code"
            os.startfile(path)
        elif "play music" in query:
            music_dir = "C:\\Users\\Public\\Music\\Sample Music"
            song = os.listdir(music_dir)
            os.startfile(os.path.join(music_dir,song[0]))
        elif "lets talk" in query:
            speak("why not ")
            chat.main()
        elif "menu" in query:
            c1 = -1
            c2=-1
            Current_day = day[date.today().weekday()]
            for i in menu['day']:
                c1+=1
                if i.lower() == Current_day.lower():
                    for j in range(len(time1)):
                        c2+=1
                        t1 = time1[j]
                       # wish_me()
                        s = menu.iat[c1,j+1]
                        print(s)
                        speak("in" + rutine[j])
                        #time.sleep(0.5)
                        speak(s)
        ################################## some more role for computer ############################# 
        elif "song" in query:
            query2 = take_command2().lower()
            if"hollywood" in query2:
                file = os.path.join(directory, query2)
                music_dir=os.listdir(file)
                m0 = -1
                while m <=len(music_dir):
                    m0+=1
                    music = random.choice(music_dir)
                    if music.endswith(".mp3"):
                        file_path = file +"\\" + music
                        pygame.mixer.music.load(str(file_path))
                        print(music)
                        pygame.mixer.music.play()
                        speak("playing Hollywood song")
                        print("playing hollywood song")
                        while pygame.mixer.music.get_busy()==True:
                            continue
                        #print(music_dir)
                        #playsound(d)
            elif "ayushman_Khurana" in query2:
                file = os.path.join(directory, query2)
                music_dir=os.listdir(file)
                m = -1
                while m <=len(music_dir):
                    m+=1
                    music = random.choice(music_dir)
                    if music.endswith(".mp3"):
                        file_path = file +"\\" + music
                        pygame.mixer.music.load(str(file_path))
                        print(music)
                        pygame.mixer.music.play()
                        speak("playing ayushman khurana song")
                        print("playing ayushman khurana song")
                        while pygame.mixer.music.get_busy()==True:
                            continue
            elif "honey_singh" in query2:
                file = os.path.join(directory, query2)
                music_dir=os.listdir(file)
                m = -1
                while m <=len(music_dir):
                    m+=1
                    music = random.choice(music_dir)
                    if music.endswith(".mp3"):
                        file_path = file +"\\" + music
                        pygame.mixer.music.load(str(file_path))
                        print(music)
                        pygame.mixer.music.play()
                        speak("playing honey singh song")
                        print("playing honey singh song")
                        while pygame.mixer.music.get_busy()==True:
                            continue
            elif "jubin_nautyal" in query2:
                file = os.path.join(directory, query2)
                music_dir=os.listdir(file)
                m = -1
                while m <=len(music_dir):
                    m+=1
                    music = random.choice(music_dir)
                    if music.endswith(".mp3"):
                        file_path = file +"\\" + music
                        pygame.mixer.music.load(str(file_path))
                        print(music)
                        pygame.mixer.music.play()
                        speak("playing jubin nautyal song")
                        print("playing jubin nautyal  song")
                        while pygame.mixer.music.get_busy()==True:
                            continue
################################################################SONG according to mood #########################################################3
          else:
            try:
                res = app.query(query)
                print(next(res.results).text)
                speak(next(res.results).text)
            except:
                print("Internet problems")
       
