
# Chatbot Project (Spring Boot backend + Frontend)
This project includes a Java Spring Boot backend that calls OpenAI's Chat Completions API and a simple HTML/JS frontend.

## Structure
```
chatbot-project/
├─ backend/      (Maven Spring Boot app)
└─ frontend/     (index.html)
```

## Requirements
- Java 17+
- Maven
- An OpenAI API key (set as environment variable `OPENAI_API_KEY`)

## Run locally
1. Set your OpenAI API key as an environment variable:
   - macOS / Linux:
     ```bash
     export OPENAI_API_KEY=sk-...yourkey...
     ```
   - Windows (PowerShell):
     ```powershell
     $env:OPENAI_API_KEY = 'sk-...yourkey...'
     ```

2. Run the backend:
   ```bash
   cd backend
   mvn spring-boot:run
   ```

3. Open `frontend/index.html` in your browser (or serve it with a static server). The frontend sends POST requests to `http://localhost:8080/api/chat` by default.

## Deploying online
- To host backend online (Render, Railway, Fly.io, Heroku, etc.), set the `OPENAI_API_KEY` in the hosting environment's secrets settings.
- Update the frontend `API_URL` to point to your deployed backend URL.

## Notes
- The backend reads the OpenAI API key from the environment variable `OPENAI_API_KEY`.
- The controller expects the OpenAI Chat Completions format. Change the `model` field in `ChatController.java` if needed.
