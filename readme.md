# 🧠 Character Chatbot CLI with Ollama

A customizable command-line chatbot using [Ollama](https://ollama.com/) with character profiles, language settings, and memory persistence via `.env`. Ideal for roleplay, AI simulation, or language practice.

---

## 📦 Features

- 🗣️ Custom user and model characters
- 🌐 Multilingual support (e.g., English, Korean)
- 💾 Memory persistence using `.env`
- 🤝 Define relationships between user and model
- 📂 Load personalities from JSON character files
- 🔁 Real-time streaming chat from Ollama

---

## 📂 Project Structure

.
├── chars/
│ └── [character].json # Character personality definitions
├── .env # Optional memory file
├── chatbot.js # Main chatbot CLI script
└── README.md

---

## 🛠️ Requirements

- Node.js v18+
- [Ollama](https://ollama.com) installed locally
- Local model available (e.g., `llama3:8b`)
- `.env` file (optional, for memory persistence)

---

## 📄 .env File Example

```env
USER_CHAR=Alex
MODEL_CHAR=Luna
CHAR_LANG=en
RELATION=friend
MODEL_NAME=llama3:8b
START_MSG=Hey there! Ready to chat?
Use --memory to enable reading/writing .env.
```
🚀 How to Run
```bash
node index.js --memory
```
If --memory is not provided, the session runs without saving/loading settings.

## 🧪 Command Reference
Command	Description: ``
/setchar [name]	Set the model's character name
/setchar --me [name]	Set your (user) character name
/lang [code]	Change conversation language (en, ko, etc.)
/relation [text]	Set relationship context between user and model
/setmodel [name]	Set Ollama model to use (e.g., llama3:8b)
/setstartmsg [msg]	Define initial system message
/outputinfo	Print current configuration info
/exit	Exit the chatbot
``

💬 Character JSON Format
Place in ./chars/<name>.json

```json
{
  "description": "You are Luna, a cheerful and caring AI friend who always listens and responds warmly."
}
```
## 🧠 System Message Logic
The system messages include:

Loaded character description

Optional [START_MSG]

Language instruction based on CHAR_LANG

## 📌 Notes
The chatbot resets system messages upon each change in character or language.

Without --memory, no persistent config is saved.

Ensure the model specified in .env exists (ollama list).

## 📃 License
MIT License – free for personal and commercial use.
