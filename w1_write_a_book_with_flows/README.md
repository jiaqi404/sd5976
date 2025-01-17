# Write a Book Flow

This project uses a multi-agent AI system powered by [crewai](https://www.crewai.com/) to write a book automatically. It uses LM Studio as the local OpenAI alternative because of the regional restrictions. It is adapted from one of the crewai [examples](https://github.com/crewAIInc/crewAI-examples).

## Installation

1. **Install crewai**: Ensure you have Python >=3.10 <=3.13 installed. Run `pip install crewai`.

2. **Install dependencies**: Navigate to your project directory and run `crewai install`.

3. **Customize env var**: Create a `.env` file under `w1_write_a_book_with_flows`, and create three vars:

```bash
OPENAI_API_BASE=http://localhost:1234/v1
OPENAI_API_KEY=anyway
SERPER_API_KEY=
```

For the `SERPER_API_KEY`, sign in [Serper](https://serper.dev/) to get your API key and type it here.

4. **Install LM Studio and Llama 3.2**: Download [LM Studio](https://lmstudio.ai/) and install Llama 3.2.

5. **Run Llama 3.2 in LM Studio**: Press the downloads button on the bottom-left corner, choose `hugging-quants/Llama-3.2-1B-Instruct-Q8_0-GGUF/llama-3.2-1b-instruct-q8_0.gguf` and press `Load Model`. Then go the Developer bar, and switch the status from Stopped to Running.

6. **Run the project**: Run `crewai flow kickoff` from the root folder of your project. The results will be shown on the terminal.

## Understanding Your Flow

The write_a_book_with_flows Flow is composed of multiple AI agents, each with unique roles, goals, and tools. These agents collaborate on a series of tasks, defined in `config/tasks.yaml`, leveraging their collective skills to achieve complex objectives. The `config/agents.yaml` file outlines the capabilities and configurations of each agent in your flow.

### Flow Structure

1. **OutlineCrew**: This crew is responsible for generating the book outline. It defines the structure and main topics of the book based on the provided goal and topic.

2. **WriteBookChapterCrew**: For each chapter outlined by the `OutlineCrew`, a new `WriteBookChapterCrew` is created. Each of these crews is responsible for writing a specific chapter, ensuring detailed and coherent content.

3. **Join and Save**: After all chapters are written, the flow combines them into a single markdown file, creating a complete book.

By understanding the flow structure, you can see how multiple crews are orchestrated to work together, each handling a specific part of the book writing process. This modular approach allows for efficient and scalable book production.