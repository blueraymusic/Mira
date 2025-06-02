
# Mira - Multimodal Interactive Recognition Agent

**Live Demo**: [blueraymusic.github.io/Mira](https://blueraymusic.github.io/Mira)
**License**: MIT
**Author**: [blueraymusic](https://github.com/blueraymusic)

---

Mira (Multimodal Interactive Recognition Agent) is a voice-activated, vision-enhanced AI assistant that blends computer vision, speech recognition, and large language models into one seamless experience. It can see, speak, listen, understand, and respond — just like a real assistant. Perfect for desktop AI experiences and multimodal experimentation.

---

##  Features

* **LLM-Powered Chat** — Uses Gemini 2.0 Flash for intelligent, conversational interactions.
* **Visual Understanding** — Uses BLIP (Salesforce) to caption real-time webcam imagery.
* **Speech-to-Text** — Converts your voice to text with `speech_recognition`.
* **Text-to-Speech** — Replies audibly using `gTTS` and plays responses via `pygame`.
* **Multilingual Support** — Supports both English and French voice interaction.
* **Contextual Memory** — Keeps track of chat history for smarter responses.
* **Training Dataset Builder** — Saves captioned images for use in fine-tuning or ML training.
* **Secure API Access** — For fast use, an API key to parse the text into audio would be crucial. If an API key is available, it would be usable.

---

## 🧹 Tech Stack

| Component         | Tech                       |
| ----------------- | -------------------------- |
| Vision            | BLIP + OpenCV              |
| Voice Recognition | speech\_recognition        |
| TTS               | gTTS + pygame              |
| LLM               | Google Gemini 2.0 Flash    |
| Interface         | Camera                     |
| Storage           | JSON (annotations + logs)  |
| Language Support  | English 🇺🇸 / French 🇫🇷 |

---

## 🚀 Getting Started

### 🔧 Prerequisites

* Python 3.8+
* macOS (M2 GPU preferred), Windows or Linux
* Webcam
* Microphone

### 📦 Install Dependencies

```bash
pip install -r requirements.txt
```

Or manually install:

```bash
pip install opencv-python torch transformers gtts pygame SpeechRecognition google-generativeai
```

---

## 🛠️ Usage

### 🔹 Launch the Assistant

```bash
python mira.py
```

Say **"Jack"** (🇺🇸) or **"Jacques"** (🇫🇷) to wake Mira.

> Example:
> "Hey Jack, what's the weather today?"
> "Jacques, parle-moi de l’intelligence artificielle."

> "Hey Jack, What am i showing you right now?"
> "Hey Jack, What was the first object i showed you?"
> "Jacques, parle-moi de l’intelligence artificielle."

Say **"That's all"** or **Goodbye Jack** to put Mira back to sleep.

### 🔹 Launch Visual Captioning (Optional)

```bash
python vision.py
```
<img width="860" alt="vision " src="https://github.com/user-attachments/assets/75ad31be-e26a-4873-bdcf-68d1a7722f96" />
<img width="1112" alt="Capture d’écran 2025-06-01 à 20 33 52" src="https://github.com/user-attachments/assets/0bb8d69c-a503-46ba-b038-96462fabb638" />


This will:

* Continuously capture webcam frames
* Generate captions using BLIP
* Display captions on screen
* Save captioned images to `train/images`
* Log all captions in `annotations.json`

---

## 🧠 How It Works

Mira integrates three threaded systems:

1. **Listener Thread** — Captures voice input and converts it to text.
2. **LLM Thread** — Sends text input to Gemini and streams back responses.
3. **TTS Thread** — Converts responses to audio and plays them via `pygame`.

If `vision.py` is active, it:

* Captures frames every 2 seconds
* Captions them with BLIP
* Updates UI with the current description
* Saves labeled data for ML training

---

## 📁 Project Structure

```
Mira/
├── index.html              # Web interface (deployed on GitHub Pages)
├── vision.py               # Visual recognition script
├── voice.py                # Voice assistant logic
├── train/
│   ├── images/             # Saved images from webcam
│   └── annotations.json    # Captions linked to images
├── key_manager/
│   └── manager.py          
├── LICENSE
└── README.md
├── ...
```

---

## 🔒 Security Note

If you want to use an API, Key Manager would encrypted and accessed via the `key_manager` module.
**Never hardcode sensitive keys into public scripts.**

---

## 🧪 Example Use Cases

* Build your own voice assistant with LLM+vision
* Caption and label real-world images automatically
* Explore multilingual LLM interaction with speech
* Collect training data for CV/ML projects

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 📣 Credits

* [Google Generative AI](https://ai.google.dev/)
* [Salesforce BLIP](https://huggingface.co/Salesforce/blip-image-captioning-base)
* [gTTS](https://pypi.org/project/gTTS/)
* [pygame](https://www.pygame.org/)
* [SpeechRecognition](https://pypi.org/project/SpeechRecognition/)

---

## 📣 Contact

Have questions, ideas, or want to collaborate?
Reach out via [GitHub Issues](https://github.com/blueraymusic/Mira/issues)

---

🧠 *"Mira sees, hears, and speaks. The next step? She understands you."*
— *The blueraymusic Team*
