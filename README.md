<img src="https://github.com/Godson-Thomas/Chris-My_Chatbot_-NLP-/blob/master/Images/1.png" width="300">  <br><br> 
# NATURAL LANGUAGE PROCESSING(NLP)
**Natural language processing**  is a subfield of linguistics, information engineering, and artificial intelligence concerned with the interactions between computers and human languages, in particular how to program computers to process and analyze large amounts of natural language data. NLP which is a branch of artificial intelligence helps computers understand, interpret and manipulate human language.
# Chatterbot-Corpus
ChatterBot is a machine-learning based conversational dialog engine build in. Python makes it possible to generate responses based on collections of known conversations. The language independent design of ChatterBot allows it to be trained to speak any language.These modules are used to quickly train ChatterBot to respond to various inputs in different languages.<br>We will use this for training out chatbot.
# Python | Text to Speech by using pyttsx3
**pyttsx3**  is a text-to-speech conversion library in Python. Unlike alternative libraries, it works offline and is compatible with both Python 2 and 3. An application invokes the pyttsx3.init() factory function to get a reference to a pyttsx3 engine instance. it is a very easy to use tool which converts the entered text into speech.<br>
we will use this library to convert text to speech for our chatbot

# Steps
## Installation
1. We will be using Jupyter Notebook for writing the code.Make sure you have Jupyter Notebook installed.<br><br>
2. Lauch your Jupyter Notebook<br><br>
3. Now we have to install the necessary libraries.Type the code in the cell of Jupyter Notebook and run it one by one.
### Note: Make sure you have python2 installed.
```
pip install chatterbot-corpus
```
```
pip install pyttsx3
```
```
pip install pywin32

     OR

pip install pypiwin32    
```
* ## Code
4. Import the modules<br><br>
<img src="https://github.com/Godson-Thomas/Chris-My_Chatbot_-NLP-/blob/master/Images/2.jpg" width="500" height="100">  <br><br> 

5. Initializing function to get an engine instance for the speech synthesis.<br>
```
engine=pyttsx3.init()
engine.setProperty("rate",128)
engine.setProperty("volume",1.4)
```
6. Create a new instance of the ChatBot class.
```
chatbot=ChatBot('chatbot')
```
7. At this point your chat bot, will learn to communicate as you talk to him. You can speed up this process by training him with examples of existing conversations.We will be raining our chatbot with conversations stored in a .txt file.[click here](https://raw.githubusercontent.com/Godson-Thomas/Chris-My_Chatbot_-NLP-/master/chats.txt)
```
trainer = ListTrainer(chatbot)
i=1
while i<=20:
    
    
    y20=open("/files/intro.txt", 'r').readlines() 
    trainer.train(y20)
    i=i+1

```

<img src="https://github.com/Godson-Thomas/Chris-My_Chatbot_-NLP-/blob/master/Images/3.jpg" width="500" >  <br><br> 

8. Now we are going to make a response from the trained chats for the input text.
```
while True:
    user=input("You:")
    if user.strip()=="Bye" or user.strip()=="bye" or user.strip()=="bye.":
        print("ChatBot: Bye")
        engine.say("bye")
        engine.runAndWait()
        break
    else:

        response=chatbot.get_response(user)
        print("chatBot:",response)
        engine.say(response)
        engine.runAndWait()
```
We will be iterating through the loop whenever the user inputs.And if the user inputs a "bye", we will exit the loop by giving a specific response. So the program control will be exited from the while loop.<br><br>

<img src="https://github.com/Godson-Thomas/Chris-My_Chatbot_-NLP-/blob/master/Images/4.png" width="2000">  <br><br> 