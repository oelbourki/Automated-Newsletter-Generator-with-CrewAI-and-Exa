## NewsletterGen Crew: An AI-Powered Newsletter Generation System

This project showcases an autonomous newsletter generation system using the crewAI framework. It utilizes multiple specialized AI agents, each playing a crucial role in the research, curation, and compilation of news into a polished HTML newsletter.

### Features

* **Automated News Gathering:** The system actively searches for the latest news on a specified topic, using the Exa API for comprehensive and up-to-date information.
* **Intelligent Content Curation:** An "Editor-in-Chief" agent analyzes the gathered news, rewrites headlines for maximum engagement, adds insightful context, and prioritizes stories for optimal reader experience.
* **Seamless HTML Generation:** A dedicated "Newsletter Compiler" agent takes the curated content and dynamically populates a user-provided HTML template, ensuring a consistent and visually appealing newsletter.
* **User-Friendly GUI:**  Built with Streamlit, the intuitive interface allows users to easily input the desired topic, personalize with a message, and trigger the newsletter generation process. 

### AI Agents and Their Roles

* **Researcher:**
    * **Role:** Scours the web for the most relevant and recent news articles on the given topic.
    * **Tools:**  Leverages the 'SearchAndContents', 'FindSimilar', and 'GetContents' tools powered by the Exa API to find, filter, and retrieve news content.

* **Editor:**
    * **Role:** Acts as the editor-in-chief, refining the raw news into a compelling narrative.
    * **Tasks:**
        * Crafts attention-grabbing headlines.
        * Provides insightful analysis and explains the significance of each news story.
        * Orders the news stories strategically for maximum impact.
        * Verifies source accuracy and relevance to the topic.

* **Designer:**
    * **Role:**  Responsible for assembling the final HTML newsletter.
    * **Tasks:**
        * Fetches the curated news from the Editor.
        * Injects the content into the designated placeholders within the HTML template.
        * Ensures the personal message from the user is seamlessly integrated.

### Architecture and Workflow

1. **User Input:** The user provides the newsletter topic and an optional personal message through the Streamlit GUI.
2. **Research Phase:** The 'researcher' agent springs into action, utilizing the Exa API tools to find and summarize relevant news articles.
3. **Editorial Process:** The 'editor' agent steps in, critically analyzing the gathered news, enhancing headlines, adding context, and prioritizing the most impactful stories.
4. **Newsletter Compilation:**  The 'designer' agent takes the curated content and carefully places it within the structure of the provided HTML template.
5. **Output:** The fully formed HTML newsletter is ready for download through the GUI, prepared to be sent to subscribers.

### Installation and Setup

1. **Prerequisites:**
   * Python 3.10 - 3.13
   * Poetry (https://python-poetry.org/) 
   * Accounts for required APIs: 
      * OpenAI (https://beta.openai.com/account/api-keys) 
      * Exa (https://exa.store/signup)
      * Google Cloud (https://cloud.google.com/api-keys) (Optional, only if using Google's LLMs)

2. **Environment Setup:**
   * Clone this repository.
   * Create a `.env` file in the root directory and populate it with your API keys:
     ```
     OPENAI_API_KEY=YOUR_OPENAI_API_KEY
     EXA_API_KEY=YOUR_EXA_API_KEY
     GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY 
     ```
   * Install project dependencies:
     ```bash
     poetry install
     ```
   
3. **Customization:**
    * **Agent Configuration (`src/newsletter_gen/config/agents.yaml`):** Fine-tune the roles, goals, and backstories of your AI agents.
    * **Task Definition (`src/newsletter_gen/config/tasks.yaml`):**  Specify the instructions and expected outputs for each task your agents perform.
    * **HTML Template (`src/newsletter_gen/config/newsletter_template.html`):** Design the structure and layout of your newsletter, including placeholders where AI-generated content will be inserted.

4. **Running the Application:**
   ```bash
   poetry run streamlit run src/gui/app.py
   ```
   Access the interactive Streamlit GUI in your web browser (usually `http://localhost:8501/`).

### Contributing

Contributions, suggestions, and feedback are always welcome! Please open an issue or submit a pull request.






