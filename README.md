# AI Code Reviewer

A full-stack web application that automatically reviews source code using Google Gemini AI. It acts as a virtual senior software engineer to analyze, review, and offer refactored fixes for your code.

---

## 🚀 Features

* **Interactive Code Editor**: A clean code editor on the frontend with live syntax highlighting.
* **Senior AI Review**: Reviews code for quality, performance bottlenecks, security flaws (like XSS or injection vulnerabilities), and SOLID design principles.
* **Side-by-Side View**: Paste your code on the left, click **Review**, and view structured feedback formatted in Markdown on the right.
* **Robust Error Handling**: Graceful error management on both backend and frontend to handle API and network issues.

---

## 🛠️ Project Structure & Components

The application is split into two primary components:

### 1. Backend (`/BackEnd`)
An Express-based API server that communicates with the Google Gemini API.
* [server.js](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/BackEnd/server.js): Entry point for the server, running on `http://localhost:3000`.
* [src/app.js](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/BackEnd/src/app.js): Configures Express middleware (CORS, JSON parsing) and mounts the API routes.
* [src/services/ai.service.js](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/BackEnd/src/services/ai.service.js): Connects to the Google Generative AI SDK, utilizes `gemini-1.5-flash`, and sets the personality instruction for a 7+ years experienced senior developer review.
* [src/controllers/ai.controller.js](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/BackEnd/src/controllers/ai.controller.js): Receives code payload, routes it to the AI service, and handles errors cleanly.
* [src/routes/ai.routes.js](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/BackEnd/src/routes/ai.routes.js): Exposes the `/ai/get-review` endpoint.

### 2. Frontend (`/Frontend`)
A modern, responsive React web application built with Vite.
* [src/App.jsx](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/Frontend/src/App.jsx): The main UI dashboard containing:
  * **Code Editor**: Powered by `react-simple-code-editor` and `prismjs`.
  * **Markdown Renderer**: Formats the AI feedback using `react-markdown` and `rehype-highlight` with syntax highlighting.
* [src/App.css](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/Frontend/src/App.css) & [src/index.css](file:///c:/Users/user/.vscode/resume-website/code-reviewer/code-review/Frontend/src/index.css): Sleek, responsive, dark-mode-first custom styling.

---

## ⚙️ Setup and Installation

### 1. Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed.

### 2. Environment Setup (Backend)
1. Go to [Google AI Studio](https://aistudio.google.com/) and create a free API Key.
2. Under `/BackEnd`, create or edit a file named `.env` and insert your key:
   ```env
   GOOGLE_GEMINI_KEY=AIzaSyYourActualAPIKey
   ```

### 3. Run the Applications

#### Start the Backend Server:
```bash
cd BackEnd
npm install
node server.js
```
The server will run on `http://localhost:3000`.

#### Start the Frontend Server:
```bash
cd Frontend
npm install
npm run dev
```
Open your browser and visit [http://localhost:5173/](http://localhost:5173/).

---

## 🔒 License
This project is open source and available under the [ISC License](https://opensource.org/licenses/ISC).
