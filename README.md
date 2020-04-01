# Basic Chat Bot using Rasa Open Source Frame Work

![Chat.png](Images/Chat.png)<br><br>
_Rasa is an open source machine learning framework for automated text and voice-based conversations. Rasa is helpful in understanding messages, holding conversations and connecting to messaging channels and APIs._

There are two main components of Rasa:
1> Rasa NLU
2> Rasa core


__Rasa NLU__ is an open-source __natural language processing__ tool for __intent classification and entity extraction__ in chatbots. Here is an example:

“I need to book flight for 4 people”

ans struture of above will look like:
{
	  "intent": "Flight_Booking",
	  "entities": {
	    "service" : "Flight",
	    "COUNT" : 4
	  }
	}
Rasa NLU is using Bag-of-word(BoW) algorithm to find intents and Conditional Random Field(CRF) to find the entities internally.

__Rasa Core__ playsessntial role in generating reply for chatbots. It consider the output of Rasa NLU (intents and entities) as an input and applies machine learning models to response with a bot reply.

Below fig shows step by step working of Rasa:
![Rasa.png](Images/Rasa.png)<br><br>

Below steps are involved in building the basic chatbot:
1> Create virtual enviorment and activate it using below commands:
python3 -m venv --system-site-packages ./rasa # Creating virtual env for rasa folder
source ./rasa/bin/activate #Activate it

2> Install dependencies for spacy using below:
 pip install "rasa[spacy]"
 python -m spacy download en_core_web_md
 python -m spacy link en_core_web_md en
 
3> Install rasa -x to your system:
pip install rasa-x --extra-index-url https://pypi.rasa.com/simple

4> Building your basic simle bot:
rasa init --no-prompt

Above command will create some configuration files in your system that we can customize as per our needs.Below files will be created:

| Column Name        | Description                                                       |
| -------------      |:-------------                                              :      | 
| __init__.py        | an empty file that helps python find your actions                 | 
| actions.py         | code for your custom actions                                      |  
| config.yml         | configuration of your NLU and Core models                         | 
| credentials.yml    | details for connecting to other services                          |    
| data/nlu.md        | Training data for NLU model                                       |
| data/stories.md    | stories                                                           |
| domain.yml         | assistant’s domain                                                |
| endpoints.yml      | details for connecting to channels like fb messenger              |
|models/tstmp.tar.gz | your initial model                                                |


Here is the last step just write __rasa x__ or __rasa shell__ in your terminal and start chatting.
