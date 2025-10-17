# Health-Care-Chatbot-Project
# 🏥 HealthCare Chatbot (Python Project)

## 📘 Project Overview
The **HealthCare Chatbot** is a Python-based conversational assistant designed to provide users with basic health-related guidance and information.  
It interacts with users in natural language to answer health queries, suggest remedies for common ailments, and help schedule appointments or connect to doctors.


## 🎯 Objectives
- To simulate an AI-driven chatbot that provides health information.
- To demonstrate the use of Natural Language Processing (NLP) in healthcare.
- To assist users with quick, reliable health tips and triage support.

---

## 🧠 Features
- 💬 Conversational interface for health-related queries.  
- 🩺 Provides basic information about diseases, symptoms, and treatments.  
- 📅 Appointment booking simulation.  
- 🧘 Health tips and diet suggestions.  
- ❌ Warns users to consult professionals for serious conditions.  

---

## 🛠️ Technologies Used
| Component | Description |
|------------|-------------|
| **Language** | Python 3.x |
| **Libraries** | `nltk`, `numpy`, `tensorflow` / `transformers`, `flask` (for web) |
| **Interface** | CLI or Web (Flask-based UI) |
| **Dataset** | Custom intent dataset (JSON) with intents, patterns, and responses |

---

## 🗂️ Project Structure

---

## 🧩 How It Works
1. **User Input:** User types a health query (e.g., "I have a headache").  
2. **Intent Matching:** The chatbot analyzes the input using NLP techniques.  
3. **Response Generation:** Based on matched intent, the bot provides an appropriate response.  
4. **Output:** The user receives text guidance or advice.  

---

## 💻 Sample Code
```python
import json
import random
import nltk
from nltk.stem import WordNetLemmatizer

lemmatizer = WordNetLemmatizer()

# Load intents
with open('intents.json') as f:
    intents = json.load(f)

def get_response(user_input):
    user_input = user_input.lower()
    for intent in intents['intents']:
        for pattern in intent['patterns']:
            if pattern in user_input:
                return random.choice(intent['responses'])
    return "I'm not sure about that. Please consult a doctor."

# Example
while True:
    msg = input("You: ")
    if msg.lower() in ['quit', 'exit']:
        print("Chatbot: Take care! Goodbye 👋")
        break
    response = get_response(msg)
    print("Chatbot:", response)

