# Add tasks and agents for the flow

This project uses a multi-agent AI system powered by [crewai](https://www.crewai.com/) to write a book automatically. It uses LM Studio as the local OpenAI alternative because of the regional restrictions.

## Installation

1. **Install crewai**: Ensure you have Python >=3.10 <=3.13 installed. Run:
    ```bash
    conda create -n myenv python<3.13
    ```

    ```bash
    pip install crewai
    ```

2. **Install dependencies**: Navigate to your root folder:

    ```bash
    cd w2_create_character_in_flow
    ```

    In `sd5976\w2_create_character_in_flow`, run:

    ```bash
    crewai install
    ```

3. **Customize env var**: Create a `.env` file under the root folder, with three vars:

    ```bash
    OPENAI_API_BASE=http://localhost:1234/v1
    OPENAI_API_KEY=anyway
    ```
    For the `OPENAI_API_KEY`, because we use LM Studio instead of Remote API, it can be anything.

4. **Install LM Studio and Llama 3.2**: Download [LM Studio](https://lmstudio.ai/) and install Llama 3.2.

5. **Run Llama 3.2 in LM Studio**: Open LM Studio. Load and run `hugging-quants/Llama-3.2-1B-Instruct-Q8_0-GGUF/llama-3.2-1b-instruct-q8_0.gguf`.

6. **Run the project**: Run this from the root folder of your project:

    ```bash
    crewai flow kickoff
    ```

    The results will be shown on the terminal.

## Customization

1. Add functions in `src\w2_create_character_in_flow\crews\poem_crew\poem_crew.py`.

2. Add task in `src\w2_create_character_in_flow\crews\poem_crew\config\tasks.yaml`.

3. Add agent in `src\w2_create_character_in_flow\crews\poem_crew\config\agents.yaml`.

## Example Output

![Alt text](assets/poem_crew.py%20-%20w2_create_character_in_flow%20-%20Visual%20Studio%20Code%20[Administrator]%201_24_2025%204_17_42%20PM.png)