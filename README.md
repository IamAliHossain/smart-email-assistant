# Smart Email Assistant 🚀

![Smart Email Assistant Banner](https://github.com/IamAliHossain/smart-email-assistant/raw/main/img/banner.png)

**Smart Email Assistant** is an AI-powered Chrome Extension + Spring Boot backend that generates professional email replies automatically in Gmail.  
It saves time and improves productivity by providing context-aware responses.

---

![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg) ![GitHub stars](https://img.shields.io/github/stars/IamAliHossain/smart-email-assistant?style=social)

---

## Features ✨

- AI-powered, context-aware email replies  
- Seamless Gmail integration  
- User-friendly interface  
- Customizable reply tone  
- Works across multiple email threads  

---

## Demo

![Smart Email Assistant Demo](https://github.com/IamAliHossain/smart-email-assistant/raw/main/img/demo.gif)

---

## Project Structure 📂

smart-email-assistant/
├── email-writer-extension/ # Chrome extension (frontend)
├── email-writer-backend/ # Spring Boot backend
└── email-writer-frontend/ # Optional web UI



---

## Installation ⚙️

### Prerequisites
- Google Chrome (latest version)  
- Node.js & npm  
- Java 11+ (for backend)  
- Gemini API Key  

### Backend Setup
```bash
cd email-writer-backend
# configure application.properties with your API key
mvn clean install
mvn spring-boot:run

## Chrome Extension Setup
cd ../email-writer-extension
npm install

1. Open Chrome → chrome://extensions
2. Enable Developer mode
3. Click Load unpacked → select email-writer-extension folder

##How It Works 🛠️

Open Gmail and trigger the extension
Extension sends email content to backend
Backend generates AI reply using Gemini model
Reply is returned and displayed in Gmail

##Tech Stack 💻

Frontend: Chrome Extension (JS, HTML, CSS)
Backend: Java, Spring Boot
AI: Gemini model
Build Tools: Maven 
