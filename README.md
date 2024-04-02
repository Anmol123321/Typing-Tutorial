# Typing-Tutorial
# This program is for those blind peoples who have interests in typing but no one have time to teach them.Through this program they can learn typing and also can do some typing jobs.
import pyttsx3
import keyboard
# Initialize the text-to-speech engine
engine = pyttsx3.init()

# Set voice properties
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[1].id)
engine.setProperty('rate', 120)
engine.setProperty('volume', 1)

def speak(audio):
    print("\nComputer: " + audio)
    engine.say(audio)
    engine.runAndWait()

def get_user_input(expected_key):
    while True:
        user_input =  keyboard.read_event(suppress=True).name
        
        if user_input.upper() == expected_key.upper():
            speak("Correct!")
            speak(f"You typed {expected_key}.")
            return True
        else:
            speak("Incorrect.")
            speak(f"You typed {user_input.upper()}.")
            speak(f"Please type {expected_key} again.")

def get_user_input1(expected_key1):
    while True:
        user_input1 =   keyboard.read_event(suppress=True).name
        
        if user_input1.upper() == expected_key1.upper():
            speak("Correct!")
            return True
        else:
            speak("Incorrect.")
            speak(f"You typed {user_input1.upper()}.")
            speak(f"Please type {expected_key1} again.")            

def introduce_key(key, landmark, direction):
    speak(f"Now,{landmark}{direction}{key}. Please Type {key}")
    get_user_input(key)
    
speak("Welcome! Let's explore the keyboard together. Feel free to touch the keys as I guide you.")
speak("First, find the two raised bars in the middle. The left one is F and the right one is J. Remember these positions.")
# Example usage
introduce_key("A", "move your hand."," to the left corner of this line. the second button of this line is ")
introduce_key("S", "the next key from A. ", "on the right side is ")
introduce_key("D", "the next key from S. ", "on the right side is ")
introduce_key("F", "the next key from D. ", "on the right side. is your left side Raised Bar ")
introduce_key("G", "the next key from F. ", "on the right side is ")
introduce_key("H", "the next key from G. ", "on the right side is ")
speak("Now lets learn. some right hand side keys  ")
introduce_key("J", "type your right hand side Raised bar", " ")
introduce_key("K", "the next key from j. ", "on the right side is ")
introduce_key("L", "the next key from K. ", "on the right side is ")

speak("Now let's practice typing the introduced keys one by one.")

speak("Type A:")
get_user_input1("A")

speak("Type S:")
get_user_input1("S")

speak("Type D:")
get_user_input1("D")

speak("Type F:")
get_user_input1('F')

speak("Type G:")
get_user_input1("G")
speak("Type H")
get_user_input1("H")

speak("Type J:")
get_user_input1("J")

speak("Type K:")
get_user_input1("K")

speak("Type L:")
get_user_input1('L')

speak("Great Job!")
speak("Lets practice some random keys of this line ")
speak("Type S:")
get_user_input1("S")

speak("Type J:")
get_user_input1("J")

speak("Type A:")
get_user_input1("A")

speak("Type F:")
get_user_input1('F')
speak("Great Job!")
speak('you have done a great job now lets explroe more keys of keyboard')
