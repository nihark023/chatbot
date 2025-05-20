

# AI Chatbot Assistant

![Python](https://img.shields.io/badge/Python-Flask-blue)
![Database](https://img.shields.io/badge/Database-SQLite-lightgrey)
![AI](https://img.shields.io/badge/AI-ChatterBot-brightgreen)
![Frontend](https://img.shields.io/badge/Frontend-HTML/CSS/jQuery-orange)
![Status](https://img.shields.io/badge/Status-Operational-success)

## 📱 Project Overview

An intelligent, self-learning chatbot application built with Python Flask and ChatterBot. This web application demonstrates the integration of machine learning conversation capabilities with a responsive web interface, showcasing full-stack development skills.

A web implementation of [ChatterBot](https://github.com/gunthercox/ChatterBot) using Flask.

To set up locally:
 1. Install Python, Flask, SQLAlchemy, and ChatterBot (run `pip install -r requirements.txt`).
 2. Run *app.py* with `python app.py`.
 3. The demo will be live on your local host [http://localhost:5000/](http://localhost:5000/)

## ✨ Features

- **Self-Learning AI**: Improves responses over time by learning from conversations
- **Persistent Knowledge**: Stores conversation data and learning patterns in SQLite
- **Responsive Web Interface**: Clean, user-friendly chat UI
- **Real-Time Responses**: Asynchronous communication without page reloads
- **Trained on English Corpus**: Pre-trained with ChatterBot's English language corpus
- **Easy Deployment**: Simple Flask setup for quick deployment

## 🛠️ Technical Implementation

### Technologies Used

- **Backend**:
  - Python 3.x
  - Flask framework
  - ChatterBot library
  - SQLite database

- **Frontend**:
  - HTML5
  - CSS3
  - JavaScript
  - jQuery
  - AJAX

### Architecture

The application follows a classic client-server architecture:

1. **Flask Server**: Handles HTTP requests and manages the chatbot logic
2. **ChatterBot Engine**: Processes natural language and generates responses
3. **SQLite Database**: Stores conversation patterns and learning data
4. **Web Interface**: Provides an intuitive chat experience to users

## 💻 Code Structure

```
chatbot-assistant/
├── app.py                 # Main Flask application
├── static/
│   └── style.css          # CSS styling
├── templates/
│   └── index.html         # HTML chat interface
├── database.sqlite3       # SQLite database (auto-generated)
├── requirements.txt
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Python 3.6 or higher
- pip package manager

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/chatbot-assistant.git
cd chatbot-assistant

# Create and activate virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install flask chatterbot==1.0.4 chatterbot-corpus
```

### Running the Application

```bash
python app.py
```

Then navigate to `http://127.0.0.1:5000/` in your web browser.

## 📋 Usage

1. Open the application in your web browser
2. Type your message in the input field
3. Press Enter or click the "Send" button
4. Receive a response from the AI assistant
5. Continue the conversation naturally

The chatbot improves its responses over time as it learns from interactions.

## 💡 Code Highlights

### Flask Route for Chat Processing
```python
@app.route("/get")
def get_bot_response():
    userText = request.args.get('msg')
    return str(english_bot.get_response(userText))
```

### ChatterBot Initialization with SQLite Storage
```python
english_bot = ChatBot("Chatterbot", storage_adapter="chatterbot.storage.SQLStorageAdapter")
trainer = ChatterBotCorpusTrainer(english_bot)
trainer.train("chatterbot.corpus.english")
```

### AJAX Request for Seamless Chat Experience
```javascript
$.get("/get", { msg: rawText }).done(function(data) {
  var botHtml = '<p class="botText"><span>' + data + '</span></p>';
  $("#chatbox").append(botHtml);
  document.getElementById('userInput').scrollIntoView({block: 'start', behavior: 'smooth'});
});
```

## 🔧 Technical Challenges & Solutions

- **Challenge**: Creating a responsive chat interface without page reloads
  - **Solution**: Implemented AJAX requests with jQuery for seamless message exchange

- **Challenge**: Persistent learning across sessions
  - **Solution**: Utilized SQLite database integration with ChatterBot's storage adapter

- **Challenge**: Natural conversation flow
  - **Solution**: Pre-trained the bot with English corpus data and implemented continuous learning

## 🚀 Future Enhancements

- Custom training data integration
- User authentication for personalized chat experiences
- Rich media responses (images, links, etc.)
- Voice input/output capabilities
- Sentiment analysis for emotionally aware responses
- Integration with external APIs for enhanced functionality

## 👨‍💻 Skills Demonstrated

- **Backend Development**: Python, Flask, API design
- **Database Management**: SQLite configuration and integration
- **AI Implementation**: Natural language processing with ChatterBot
- **Frontend Development**: Responsive UI with HTML/CSS/JavaScript
- **Asynchronous Programming**: AJAX for real-time communication
- **Full-Stack Integration**: Seamless connection between all components

---

## 📬 Contact

[Nihar K](mailto:niharknihark@gmail.com) | [LinkedIn](www.linkedin.com/in/nihar-k) | [GitHub](https://github.com/nihark023)

*Note: This project uses ChatterBot which learns from user inputs. Be mindful of the training data quality for best results.*
