# Smart Email Assistant - Chrome Extension

**Smart Email Assistant** is an AI-powered Chrome Extension + Spring Boot backend that helps you generate professional email replies automatically.  
It analyzes email context and drafts replies instantly, saving time and boosting productivity.

---

## Features

- AI-generated, context-aware email replies  
- Seamless Gmail integration  
- Easy-to-use interface  
- Customizable response tone  
- Supports multiple email threads  

---

## Project Structure



smart-email-assistant/
├── email-writer-extension/ # Chrome extension (frontend)
├── email-writer-backend/ # Spring Boot backend
└── email-writer-frontend/ # Optional web UI


---

## Installation

### Prerequisites
- Java 11+  
- Maven or Gradle  
- Node.js & npm  
- OpenAI API Key  

---

### Backend Setup (Spring Boot)

```bash
cd email-writer-backend
# configure application.properties with your API key and port
mvn clean install
mvn spring-boot:run

Chrome Extension Setup
cd ../email-writer-extension
npm install


Open Chrome → chrome://extensions

Enable Developer mode

Click Load unpacked → select email-writer-extension folder

Configuration
Parameter	Description	Example
OPENAI_API_KEY	Your OpenAI API key	sk-xxxxxxxx
server.port	Backend port	8080
extension.apiUrl	Backend API URL for extension	http://localhost:8080
How It Works

Open Gmail and activate the extension

Compose or open an email thread

Extension sends content to backend

Backend calls AI model to generate reply

Reply is returned and displayed in Gmail

Tech Stack

Frontend: Chrome Extension (JavaScript, HTML, CSS)

Backend: Java, Spring Boot

AI Integration: OpenAI API / GPT model

Build Tools: Maven / Gradle

Future Enhancements

Tone selection (formal/casual)

Multi-language support

Email template library

Web dashboard for settings/history

Author

Ali Hossain

GitHub: IamAliHossain

Email: alihoosin.cse.pstu@gmail.com

License

MIT License

