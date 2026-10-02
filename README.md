# Musical Chatbot

A music-themed chatbot built step by step in a **Jupyter notebook** with Python. It starts as a simple rule-based bot and becomes a data-driven chatbot that reads its intents from a JSON file. It uses **NLTK** to preprocess text and can detect your mood, talk about music and tell jokes.

Built as the midterm project for a Programming with Data course.

## What the chatbot can do

- Greets you by name and asks how you're feeling
- **Detects your mood** (happy, sad, angry or neutral) and replies to match
- **Talks about music**: genres, artists, albums, songs, instruments and music history
- **Gives recommendations** and responds when you say you like pop, jazz, classical or rock
- **Tells a joke** when you ask (using `pyjokes`)
- Uses **NLTK** (tokenising, stop-word removal, stemming and lemmatisation) so it understands different wordings of the same question

Example conversation:

```
Chatbot: Hello! What is your name?
You: Alizea
Chatbot: Hi, Alizea! I'm Musical Chatbot
Chatbot: Alizea! How are you feeling today?
You: I feel happy
Chatbot: Awesome, Alizea! I'm so happy you're feeling great!
You: tell me a joke
Chatbot: Here's a joke for you, Alizea: ...
You: bye
Chatbot: Come back soon, Alizea, Goodbye!
```

## How it was built (the 4 parts)

| Part | Concepts | What it adds |
|------|----------|--------------|
| **1** | Lists, conditions, string concatenation | A basic bot that matches fixed keywords to replies |
| **2** | Dictionaries, regular expressions | Regex patterns for greetings, farewells, thanks and similar, plus picking up the user's name and favourite colour |
| **3** | File handling (JSON) | Reads `intents.json` and maps patterns → intents → responses, so the bot is data-driven |
| **4** | NLTK text preprocessing | Lemmatised word-overlap matching, mood detection, personalised replies, jokes and coloured output |

## Running the Chatbot

### Quick start (one command)

**Step 1:** Run this command in the terminal first. It downloads the project from GitHub into a temporary folder, installs the required packages in a separate environment (so your main Python isn't changed), and starts Jupyter:

```bash
D=$(mktemp -d) && gh repo clone Alizea2/Musical-Chatbot "$D" && cd "$D" && python3 -m venv .venv && .venv/bin/pip install -q -r requirements.txt && .venv/bin/jupyter notebook Musical_Chatbot.ipynb
```

**Step 2:** Jupyter usually opens in your browser by itself. If it doesn't, click the link that starts with **`http://localhost:8888/`** in the terminal output. Copy the whole link, including the `?token=...` part.

**Step 3:** In the notebook, go to **Run → Run All Cells**. Each part's chatbot waits for you to type in the input box below its cell. Type **`bye`** to finish that part and move on to the next. The full Musical Chatbot is at the end, in **Part 4**.

When you're done, close the browser tab and press `Ctrl + C` in the terminal to stop Jupyter.

> This needs Python 3 and the [GitHub CLI](https://cli.github.com/) (`gh`) signed in to an account that can access this repository. The first run downloads a few small NLTK datasets automatically.

### Manual setup

From inside the project folder:

```bash
pip install -r requirements.txt
jupyter notebook Musical_Chatbot.ipynb
```

## Project Structure

| File | Purpose |
|------|---------|
| `Musical_Chatbot.ipynb` | The notebook with all four parts of the chatbot |
| `intents.json` | 17 intents (greetings, moods, genres, artists, albums, songs, instruments, history and recommendations), each with patterns and responses |
| `requirements.txt` | Python packages: `nltk`, `pyjokes`, `colorama`, `notebook` |

## Built With

- Python 3 and [Jupyter Notebook](https://jupyter.org/)
- [NLTK](https://www.nltk.org/): tokenising, stop words, Porter stemmer and WordNet lemmatiser
- [pyjokes](https://pyjok.es/): jokes
- [colorama](https://pypi.org/project/colorama/): coloured chatbot output

## Author

[@Alizea2](https://github.com/Alizea2)
