# Mess-Cleaner
I have an HTML file that requires an AI API key (preferably Gemini). Please provide instructions on how to integrate the API key, grant the necessary permissions for folder access, and save the configurations so the tool functions correctly.
Mess Cleaner AI
Organize your cluttered local directories using the power of Natural Language and Google Gemini. Mess Cleaner AI is a lightweight, zero-dependency, single-file web utility that gives you an intelligent way to clean up your folders without uploading your actual files to a server.

🚀 Key Features
Natural Language Structuring: No complex rules or configurations. Just type how you want your files sorted (e.g., "Put all PDFs into an 'Invoices' folder if they contain '2026', otherwise put them in 'Guides'. Group all images by year.").

Local Processing: Utilizes the modern browser File System Access API to create directories and move your files directly on your machine.

Privacy First: Your actual file contents never leave your computer. Only the list of filenames and your prompt are sent to the Gemini API for categorization.

Live Terminal Log: Features a built-in interactive terminal UI that tracks your API calls, folder paths, and file operations in real time.

Seamless Fallback Mode: Works safely in read-only/simulation mode if opened inside restricted iframe preview spaces or unsupported browsers.

🛠️ Tech Stack
Frontend Framework: Tailwind CSS (via CDN)

LLM Integration: Google Gemini API (gemini-2.5-flash)

Core APIs: File System Access API (showDirectoryPicker)

Storage: Web LocalStorage API (for securely keeping your API key client-side)

📦 How It Works
[ Local Folder ] ──(Extracts Filenames Only)──> [ Gemini API ]
                                                       │
                                            (Applies User Prompt)
                                                       │
[ Local File Movement ] <──(Parses JSON Plan)──────────┘
API Handshake: Securely save your Google Gemini API Key directly into your browser's local storage.

Directory Analysis: Choose a local folder. The application securely indexes the filenames present in the root directory.

Intent Parsing: Provide your organizational prompt. The tool prompts gemini-2.5-flash to return a strictly formatted JSON execution layout.

Local Execution: Review the generated table mapping out your old paths to the new structure, hit confirm, and watch the app generate folders and migrate files.

💻 Getting Started
Because Mess Cleaner AI is built entirely inside a single standalone HTML file, there is no installation or package compiling required.

Prerequisites
A modern web browser supporting the File System Access API (Chrome, Edge, Opera).

A Google Gemini API Key (You can obtain one from the Google AI Studio).

Setup Instructions
Clone this repository or copy the code inside index.html.

Open the file directly in your preferred browser:

Bash
# Alternatively, double-click the index.html file in your file manager
open index.html
Paste your Gemini API key into Step 1 and click Save.

⚙️ Usage Guide
1. Select Your Directory
Click on the Click to Select Folder dashboard banner. Your browser will prompt you to grant Read and Write permissions. This permission is necessary so the script can physically move your files and clean up empty root paths locally.

2. Instruct the AI
Write your sorting logic directly inside the provided textarea.

Example Prompts:

"Move all .png and .jpg files into a directory called 'Graphics'. Put everything else into a folder named 'Miscellaneous'."

"Group files by their extension type, but if a file name contains the word 'draft', put it in a folder called 'In-Progress'."

3. Generate and Confirm
Click Generate AI Plan. Review the dynamically generated interactive preview table mapping out every file's destination path. If everything looks correct, select Confirm & Move Files.

🔒 Security & Privacy
No Backend Server: This application runs entirely inside your browser tab. There are no tracking scripts, telemetry analytics, or database backends.

Data Scoping: The application can only access the explicit folder you select through the file picker prompt. It cannot look at other system resources.

API Key Safety: Your API key is stored locally in your browser's instance memory via localStorage.setItem(). It is sent exclusively to the official endpoint: [https://generativelanguage.googleapis.com](https://generativelanguage.googleapis.com).

📜 License
This project is open-source and available under the MIT License. Feel free to customize, tweak, or expand its functionalities!
