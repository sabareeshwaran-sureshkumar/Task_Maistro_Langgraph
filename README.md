# Task mAIstro

Managing tasks effectively is a universal challenge. Task mAIstro is an AI-powered task management agent that combines natural language processing with long-term memory to create a more intuitive and adaptive experience. This repository allows you to deploy Task mAIstro and interact with it seamlessly through text!

Key features:
- Natural conversation through a text-based interface to update or add tasks
- Adaptive learning of your management style and preferences
- Persistent memory of tasks, context, and preferences
- Flexible deployment options for local or hosted environments

![task_maistro_demo](https://github.com/user-attachments/assets/170e1088-499a-4373-b724-da51e9778296)

---

## Quickstart

### 1. Set Up Your Environment
1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/task-maistro.git
   cd task-maistro
   ```

2. Create `.env` file with your API keys and configurations:
  
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Ensure [Docker Desktop](https://docs.docker.com/engine/install/) is installed and running.

---

### 2. Deployment via LangGraph CLI
The simplest way to deploy is using the **LangGraph CLI**. Follow these steps:

1. Install the LangGraph CLI (if not already installed):
   ```bash
   pip install langgraph-cli
   ```

   
- Run the following command:
   ```bash
   langgraph build -t my-image   
   ```
   Before running this command , ensure you have your 'docker compose.yml file'

- Next run this command:
   ```bash
   docker compose up 
   ```

- Use the printed endpoint to interact with Task mAIstro.


#### 2. **LangGraph Cloud**
For production deployments:
- Deploy to [LangGraph Cloud](https://langchain-ai.github.io/langgraph/concepts/langgraph_cloud/).
- Manage through your LangSmith account.
- Access via LangGraph Studio's web UI.

---



### 3. Interact with Task mAIstro
Task mAIstro can now be accessed through the **text-based interface**:

1. Open `audio_ux.ipynb`:
   ```bash
   jupyter notebook ntbk/audio_ux.ipynb
   ```

2. Connect the notebook to your deployment by providing the endpoint URL (e.g., `http://localhost:8123`).

3. Run the notebook and start managing tasks using natural language inputs!

---

## Task mAIstro Application

### Architecture

Task mAIstro leverages [LangGraph](https://langchain-ai.github.io/langgraph/) to maintain three memory types:

1. **ToDo List Memory**
   - Task descriptions, deadlines, and statuses
   - Actionable next steps

2. **User Profile Memory**
   - Personal preferences and context
   - Work/life patterns
   - Historical interactions

3. **Interaction Memory**
   - Task management style
   - Communication preferences
   - Organizational patterns

The schema for each memory type and the graph flow is defined in `task_maistro.py`. The central `task_maistro` node orchestrates interactions and decides which memory type to update based on user input.

---

## Voice Interface (Optional)

Task mAIstro also supports voice interactions using:
- [OpenAI's Whisper](https://platform.openai.com/docs/guides/speech-to-text) for speech-to-text
- [ElevenLabs](https://github.com/elevenlabs/elevenlabs-python) for text-to-speech

### Setup (Optional for Voice):
1. Install FFmpeg:
   ```bash
   # macOS
   brew install ffmpeg
   ```

2. Connect `audio_ux.ipynb` to your deployment:
   - **CLI**: Use the endpoint printed to the console (e.g., `http://localhost:8123`).


