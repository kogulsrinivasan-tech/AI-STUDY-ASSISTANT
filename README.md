# AI Study Assistant

A Python-based AI study tool that explains any Computer Science topic in simple language, gives a real-world example, and generates quiz questions — powered by OpenRouter and GPT-OSS 120B.

---

## Demo

Type any topic like **"Recursion"**, **"DBMS"**, or **"Binary Search"** and get:
- A clear explanation
- A real-world example
- 3 quiz questions with answers

---

## Features

- AI-powered explanations — any CS topic explained simply
- Real-world examples — concepts mapped to practical scenarios
- Auto-generated quiz questions — test your understanding instantly
- Simple HTML UI — clean dark-themed web interface
- Runs in Google Colab — no local setup needed

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3 |
| Backend | Flask |
| AI Model | GPT-OSS 120B (via OpenRouter) |
| Frontend | HTML + CSS + JavaScript |
| Runtime | Google Colab |

---

## Project Structure

```
ai-study-assistant/
│
├── app.py          # Flask backend + HTML UI + OpenRouter API call
└── README.md       # Project documentation
```

---

## Setup and Run

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ai-study-assistant.git
cd ai-study-assistant
```

### 2. Install dependencies

```bash
pip install flask requests
```

### 3. Add your OpenRouter API key

Open `app.py` and replace:

```python
OPENROUTER_API_KEY = "your-api-key-here"
```

Get your free API key at [openrouter.ai](https://openrouter.ai)

### 4. Run the app

```bash
python app.py
```

Then open your browser and go to:

```
http://localhost:5000
```

---

## Running in Google Colab

**Cell 1 — Install dependencies:**
```python
!pip install flask requests
```

**Cell 2 — Run the app:**
```python
# Paste the full app.py code here
# Make sure to set your OPENROUTER_API_KEY
import threading
threading.Thread(target=lambda: app.run(port=5000)).start()
```

**Cell 3 — Get your URL:**
```python
from google.colab.output import eval_js
print(eval_js("google.colab.kernel.proxyPort(5000)"))
```

Click the printed URL to open the app.

---

## How It Works

1. User types a topic into the input field
2. Frontend sends a POST request to the /ask endpoint
3. Flask backend formats a structured prompt and sends it to OpenRouter API
4. GPT-OSS 120B returns an explanation, example, and quiz questions
5. Result is displayed in the UI instantly

---

## Example Output

**Input:** Recursion

```
EXPLANATION:
Recursion is a technique where a function calls itself to solve a smaller
version of the same problem. It continues until it reaches a base case,
which stops the loop. It is widely used in tree traversal, sorting, and
mathematical computations.

EXAMPLE:
Think of Russian nesting dolls — each doll contains a smaller version of
itself until you reach the smallest one. That smallest doll is your base case.

QUIZ QUESTIONS:
1. What is a base case in recursion and why is it important?
   Answer: A base case is the condition that stops the recursion. Without it,
   the function would call itself infinitely and cause a stack overflow.

2. What happens if a recursive function has no base case?
   Answer: It runs infinitely until the program crashes with a stack overflow error.

3. Write a recursive function to calculate the factorial of a number.
   Answer: def factorial(n): return 1 if n == 0 else n * factorial(n-1)
```

---

## Environment Variables

| Variable | Description |
|---|---|
| `OPENROUTER_API_KEY` | Your OpenRouter API key |
| `MODEL` | AI model to use (default: openai/gpt-oss-120b:free) |

---

## Future Improvements

- Save session history to a text file
- Add quiz scoring — track correct and wrong answers
- Support multiple topics in one session
- Add topic suggestions dropdown
- Export full study notes as PDF

---

## Built By

**Kogul Srinivasan G**
1st Year CSE Student, Velammal Engineering College, Chennai

[LinkedIn](https://linkedin.com/in/kogul-srinivasan-g-1b819b3b9)
[GitHub](https://github.com/your-username)

---

## License

This project is open source and available under the MIT License.
