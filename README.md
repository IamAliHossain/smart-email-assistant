# Smart Email Assistant - Chrome Extension

## Overview
The Smart Email Assistant is a Chrome extension that helps users generate AI-powered email replies directly within Gmail. This extension leverages a backend SpringBoot API to produce professional, casual, friendly, and formal replies based on the user's selection.



I have developed a REST API using SpringBoot that serves as a wrapper for Google's Gemini API. This API generates a reply to a specific email based on the content captured from the email and the selected tone.

One can always create a web application but when it comes to emails its best to basically integrate the reply functionality into your email application/platform/service, which is what I have done.



Gmail, launched by Google on April 1, 2004, revolutionized email with its user-friendly interface, robust search capabilities, and generous storage space. 
Initially available by invitation only, it quickly gained popularity due to its innovative features like conversation view and powerful spam filtering. Today, Gmail boasts over 1.8 billion users worldwide, holding a significant 28.78% share of the global email market. It remains a dominant force in the email industry, with a substantial user base in countries like the United States, India, and Indonesia2.
Gmail's seamless integration with other Google services and its strong security features continue to make it a preferred choice for both personal and professional communication.

In case of a web application, one would basically be required to copy the contents of the email he has recieved and paste it into the web application created then generate the reply and copy that and paste it back to his email service. One can obviously do that but there's an easier way!

You can integrate you web application into Gmail's UI by creating a Chrome extension and loading it.
You can also publish this extension if you like.



## What is a Chrome extension?
A Chrome extension is a small software program that enhances the functionality of the Google Chrome browser. It allows you to add new features or modify the behavior of websites you visit.

## How to create a Chrome extension?
Here's a step-by-step guide to creating your first Chrome extension:
1. **Set Up Your Project**:
   * Create a new directory for your extension.
2. **Create the Manifest File**:
   * Inside the directory, create a file named `manifest.json`. This file contains metadata about your extension.
   * Example `manifest.json`:
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
3. **Develop the Extension's Functionality**:
   * Create HTML, CSS, and JavaScript files to implement the desired features of your extension.
   * Example content for `content-script.js`:
     ```javascript
     console.log("Content script loaded!");
     ```
4. **Load Your Extension in Chrome**:
   * Open Chrome and navigate to `chrome://extensions/`.
   * Enable "Developer mode" by toggling the switch in the top right corner.
   * Click "Load unpacked" and select the directory containing your extension files.

5. **Test and Debug Your Extension**:
   * Ensure that your extension works as expected by testing it in different scenarios.
   * Use the Chrome Developer Tools to debug and refine your code.
6. **Publish Your Extension (Optional)**:
   * If you wish to share your extension with others, you can publish it to the Chrome Web Store.

For more detailed information and documentation, please refer to the official [Chrome Extension Documentation](https://developer.chrome.com/docs/extensions/).
For free sample code for Chrome extensions, check out this [GitHub repository](https://github.com/GoogleChrome/chrome-extensions-samples/tree/main/functional-samples/tutorial.hello-world).

## Recent Updates

This section details the latest enhancements and modifications made to the Smart Email Assistant extension.
### Gemini 2.0 Flash Integration
* **Description:** The extension now utilizes Google's Gemini 2.0 Flash model, replacing the previous Gemini 1.5 Flash version. This update improves the quality and efficiency of AI-generated email replies.
* **Backend Changes:**
  + Updated the backend service to interact with the Gemini 2.0 Flash API.
  + Modified the DTO (Data Transfer Object) to include `Length` and `instructions` fields, allowing users to specify the desired reply length and provide custom instructions for the AI.
  + Adjusted the service layer logic to incorporate these new fields when generating replies.
### User Interface Enhancements
* **Description:** The user interface within Gmail has been significantly enhanced to provide a more intuitive and efficient user experience.
* **Changes:**
  + **Sidebar Panel:** The extension now features a dedicated sidebar panel for AI reply generation, offering a persistent and integrated interface within Gmail.
  + **Visual Theme:** A new purple-themed design has been implemented for the sidebar, improving the visual appeal and consistency of the extension.
  + **Input Fields:** Users can now specify the desired reply length(in words), using a dedicated input field and provide custom instructions to the AI using a text area within the sidebar.
  + **Close Button:** A close button has been added to the sidebar, allowing users to manually control its visibility.
  + **CSS Refactoring:** Inline CSS styles have been consolidated into the `content.css` file, resulting in cleaner and more maintainable code.
### Functionality Improvements
* **Description:** The core functionality of the extension has been improved to ensure seamless integration with Gmail and provide more control to the user.
* **Changes:**
  + **Toolbar Button Compatibility:** The sidebar's AI reply button now triggers the click event of the original AI reply button injected into the Gmail compose toolbar. This ensures that any previously injected functionality remains operational.

## Features
* Extracts email content from the Gmail interface.
* Provides a dropdown to select the tone of the reply (Professional, Casual, Friendly, Formal).
* Generates AI-based email replies using a backend API.
* **Allows users to specify the desired reply length.**
* **Integrates a user-friendly sidebar panel, enabling custom AI reply instructions.**
* Inserts the generated reply into the Gmail compose window.

## Comparison with alternatives
>
>
> | Feature | Smart Email Assistant | Gemini Gem(External Tool) | Emily AI(Browsing Assistant) |
> |---|---|---|---|
> | Integration with Gmail | Primarily toolbar button + sidebar injection; relies on DOM manipulation. | No direct Gmail integration; Requires opening a separate window, copy-pasting email content, and copy-pasting replies back into Gmail. | Deep integration; appears native to Gmail; often includes features like smart snippets and reply summaries integrated into the compose view. |
> | AI Capabilities | Relies on a separate backend server (http://localhost:8080); simple email context extraction and tone adjustment | Integrates directly with Gemini; potentially higher quality responses; greater contextual understanding and instruction following; potentially supports more advanced features like summarization, sentiment analysis, etc. | Varies, but often focuses on conversation history; provides summarized key points and suggests replies based on that history; often has a focus on brevity and time efficiency. |
> | Customization | Tone selection, reply length, and custom instructions; basic; UI customization is also basic. | Potentially more granular customization; user profiles to set preferences for default tones and styles; more complex reply structure customization and may be personalized to individual writing patterns. | Often includes tone adjustment, message length controls and sometimes additional features that may change how an e-mail should be addressed. |
> | Speed and Performance | Dependent on the performance of the backend server and network latency. | Depends on the Gemini API response time and the user's internet connection. | Typically very fast; designed for quick interactions and on-the-fly suggestions. |
> | Privacy and Security | Data is sent to a custom backend server; potential privacy concerns depending on the server's security measures. | Data is sent to Google's servers; generally high security, but users should be aware of Google's data policies. | Varies by provider; some assistants may process data locally, while others send it to the cloud. |

## Installation
1. Clone the repository to your local machine.
2. Open Chrome and navigate to `chrome://extensions/`.
3. Enable "Developer mode" in the top right corner.
4. Click "Load unpacked" and select the extension directory.

## Backend Setup
1. Set up the backend server to handle email generation requests.
2. Update the `gemini.api.url` and `gemini.api.key` values in the backedn configuration.

## Usage
1. Open Gmail in your Chrome browser.
2. Compose a new email or reply to an existing one.
3. Select the desired tone from the dropdown.
4. Click the "AI Reply" button to generate a response.
5. The generated reply will be inserted into the compose window.

## Contact
For questions or support, please reach out to me at [alihossain.cse.pstu@gmail.com](mailto:alihossain.cse.pstu@gmail.com) .
