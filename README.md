

# Django Ollama Chat App

This project demonstrates how to build a simple chat application using Django and Ollama, allowing you to interact with large language models (LLMs) locally.  This application uses the Llama 3 model by default, but can be configured to use other Ollama-compatible models.

## Features

* **Local LLM Interaction:**  Runs the LLM (Llama 3 by default) locally using Ollama, ensuring data privacy and low latency.
* **Streaming Responses:**  Displays the LLM's response in real-time as it's generated, providing a more interactive chat experience.
* **Simple Chat Interface:**  A basic web interface for sending messages to the LLM and viewing its responses.
* **Easy Setup:**  Uses Docker for Ollama, simplifying model management and ensuring consistency.

## Prerequisites

* **Docker:**  Required for running the Ollama container.  Install Docker Desktop (for Windows/macOS) or Docker Engine (for Linux).  See [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/) for installation instructions.
* **Python 3:**  Required for running the Django application.
* **Git:**  Optional, but recommended for cloning the repository.

## Installation

1. **Clone the repository:**

   ```bash
   git clone [https://github.com/YOUR_GITHUB_USERNAME/django-ollama.git](https://www.google.com/search?q=https://github.com/YOUR_GITHUB_USERNAME/django-ollama.git)  # Replace with your repo URL
   cd django-ollama
   
2. **Set up the Ollama container:**

   ```bash
   docker pull ollama/ollama
   docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
   docker exec -it ollama ollama run llama3  # Or any other Ollama-compatible model

Note: You can replace llama3 with the name of any other model you have downloaded using ollama pull <model_name>.

3. **Create a virtual environment:**

   ```bash
   python3 -m venv env
   source env/bin/activate  # On Linux/macOS
   env\Scripts\activate  # On Windows

4. **Install dependencies:**

   ```bash
   pip install django ollama

5. **Run the Django development server:**

   ```bash
   python manage.py runserver

6. **Access the application:**

Open your web browser and go to http://127.0.0.1:8000/chat/ to interact with the chat application.

7. **Usage:**

Type your message in the input box.
Click the "Send" button.
The LLM's response will appear in the chat history.

   
**Project Structure**
   ```bash
   django-ollama/
   ├── ollamachat/        # Django project
   │   ├── chat/        # Django app
   │   │   ├── templates/
   │   │   │   └── chat.html
   │   │   ├── views.py
   │   │   ├── urls.py
   │   │   └── ollama_api.py
   │   ├── ollamachat/
   │   │   ├── settings.py
   │   │   ├── urls.py
   │   │   └── wsgi.py
   │   └── manage.py
   └── README.md


License
MIT License

Acknowledgements
This project uses Ollama for local LLM interaction.
The Llama 3 model is used by default.

