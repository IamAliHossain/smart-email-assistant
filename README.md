# Smart Email Assistant - Chrome Extension

A smart, AI-powered email management system built with **Spring Boot** for intelligent sorting, classification, and automation of emails.  

---
## Overview
The Smart Email Assistant is a Chrome extension that helps users generate AI-powered email replies directly within Gmail. This extension leverages a backend SpringBoot API to produce professional, casual, friendly, and formal replies based on the user's selection.

## 📷 Screenshots
*(Add your screenshots here later, e.g. dashboard, email classification view)* 

I have developed a REST API using SpringBoot that serves as a wrapper for Google's Gemini API. This API generates a reply to a specific email based on the content captured from the email and the selected tone.

One can always create a web application but when it comes to emails its best to basically integrate the reply functionality into your email application/platform/service, which is what I have done.


Gmail, launched by Google on April 1, 2004, revolutionized email with its user-friendly interface, robust search capabilities, and generous storage space. Initially available by invitation only, it quickly gained popularity due to its innovative features like conversation view and powerful spam filtering. Today, Gmail boasts over 1.8 billion users worldwide, holding a significant 28.78% share of the global email market. It remains a dominant force in the email industry, with a substantial user base in countries like the United States, India, and Indonesia2. Gmail's seamless integration with other Google services and its strong security features continue to make it a preferred choice for both personal and professional communication.

In case of a web application, one would basically be required to copy the contents of the email he has recieved and paste it into the web application created then generate the reply and copy that and paste it back to his email service. One can obviously do that but there's an easier way! You can integrate you web application into Gmail's UI by creating a Chrome extension and loading it. You can also publish this extension if you like.



Whether you're replying to an email that you recieved recently or you're in a mail trail ( chain of replies ) the extension is smart enough to understand the context and generate an appropriate reply.


## What is a Chrome Extension?
A Chrome extension is a small software program that enhances the functionality of the Google Chrome browser. Extensions allow users to customize their browsing experience by adding new features, modifying the appearance of web pages, or integrating with other services and applications. These extensions are built using web technologies such as HTML, CSS, and JavaScript, and can be easily installed from the Chrome Web Store. By leveraging the capabilities of Chrome extensions, users can streamline tasks, improve productivity, and personalize their interactions with the web.


## Steps to Create a Chrome Extension
Creating a Chrome extension involves several steps. Here’s a high-level overview of the process:
    1. Set Up Your Extension Directory:
        Create a new directory for your extension files.
        Inside this directory, create a file named manifest.json.
    2. Create the Manifest File:
  
      The manifest.json file provides essential information about your extension, such as its name, version, permissions, and background scripts.
      Example content for manifest.json:
       ```json
          {
              "manifest_version": 3,
              "name": "My Extension",
              "version": "1.0",
              "description": "A brief description of your extension.",
              "permissions": ["activeTab"],
              "background": {
                  "service_worker": "background.js"
              },
              "content_scripts": [
                  {
                      "matches": ["<all_urls>"],
                      "js": ["content-script.js"]
                  }
              ]
          }
       ```
    3. Develop the Extension's Functionality:

        Create HTML, CSS, and JavaScript files to implement the desired features of your extension.
        Example content for content-script.js:
            console.log("Content script loaded!");
    4. Load Your Extension in Chrome:

Open Chrome and navigate to chrome://extensions/.
Enable "Developer mode" by toggling the switch in the top right corner.

## Features
- Automatically categorizes emails (important, promotional, spam, etc.)
- Uses NLP to summarize and prioritize messages
- Smart reminders for unread or urgent mails
- Integration-ready REST API
- Simple dashboard to view insights

---

## 🏗️ Tech Stack
**Backend:** Spring Boot (Java)  
**AI/NLP:** Gemini API  
**Frontend (optional):** React.js  
**Build Tool:** Maven / Gradle  

---

## ⚙️ Installation & Setup

```bash
# Clone the repository
git clone https://github.com/alihoosin-cse/smart-email-assistant.git

# Navigate to project
cd smart-email-assistant

# Build & run
mvn spring-boot:run
```

---

## 🧠 How It Works
1. User sends or receives an email  
2. The backend analyzes the text using NLP  
3. The system classifies and stores emails intelligently  
4. Notifications/reminders are sent based on priority  

---

## 📷 Screenshots
*(Add your screenshots here later, e.g. dashboard, email classification view)*  

---

## 🤝 Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.  

---

## 🧑‍💻 Author
**Ali Hossain**  
📍 Dhaka, Bangladesh  
📧 alihoosin.cse.pstu@gmail.com  

---

> Developed with ❤️ by **Ali Hossain**
