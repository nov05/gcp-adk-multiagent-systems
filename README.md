# Google Skills Lab - **Build Multi-Agent Systems with ADK**   

* Lab - https://www.skills.google/paths/3273/course_templates/1275/labs/606594

  ```bash
  git clone https://github.com/nov05/gcp-adk-multiagent-systems.git
  cd gcp-adk-multiagent-systems
  export PATH=$PATH:"/home/${USER}/.local/bin"
  python3 -m pip install google-adk -r adk_multiagent_systems/requirements.txt
  ```

## 👉 Task 2. Explore transfers between parent, sub-agent, and peer agents

  ```bash
  cd ~/gcp-adk-multiagent-systems/adk_multiagent_systems
  cat << EOF > parent_and_subagents/.env
  GOOGLE_GENAI_USE_VERTEXAI=TRUE
  # GOOGLE_CLOUD_PROJECT=qwiklabs-gcp-00-c3ebf875872a  ## ⚠️ Your project ID
  GOOGLE_CLOUD_LOCATION=global
  MODEL=gemini-2.5-flash
  EOF
  ```
  ```bash
  cp parent_and_subagents/.env workflow_agents/.env
  ```
  ```bash
  adk run parent_and_subagents
  ```

## 👉 Task 3. Use session state to store and retrieve specific information

  ```bash
  adk web --allow_origins "regex:https://.*\.cloudshell\.dev"
  ```

## 👉 Task 4. Begin building a multi-agent system with a SequentialAgent  

  ```bash
  cd ~/gcp-adk-multiagent-systems/adk_multiagent_systems
  adk web --allow_origins "regex:https://.*\.cloudshell\.dev" --reload_agents
  ```

  A new browser tab will open with the ADK Dev UI.    
  From the Select an agent dropdown on the left, select `workflow_agents`.   
  Start the conversation with: `hello`. It may take a few moments for the agent to respond, but it should request you enter a historical figure to start your film plot generation.    
  When prompted to enter a historical figure, you can enter one of your choice or use one of these examples:   
  ```text
  Zhang Zhongjing - a renowned Chinese physician from the 2nd Century CE.
  Ada Lovelace - an English mathematician and writer known for her work on early computers
  Marcus Aurelius - a Roman emperor known for his philosophical writings.
  ```

## 👉 Task 5. Add a LoopAgent for iterative work

  Return to the ADK Dev UI tab and click the `+ New Session` button in the upper right to start a new session.   
  Begin a new conversation with: `hello`   
  When prompted to choose a kind of historical character, choose one that interests you. Some ideas include:    
  ```text
  an industrial designer who made products for the masses
  a cartographer (a map maker)
  that guy who made crops yield more food
  ```

## 👉 Task 6. Use a "fan out and gather" pattern for report generation with a ParallelAgent  

  In the ADK Dev UI, click `+ New Session` in the upper right.     
  Enter `hello` to start the conversation.      
  When prompted, enter a new character idea that you are interested in. Some ideas include:    
  
  ```text
  that actress who invented the technology for wifi
  an exciting chef
  key players in the worlds fair exhibitions
  ```

