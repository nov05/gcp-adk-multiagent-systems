# Google Skills Lab - **Build Multi-Agent Systems with ADK**   

* Lab - https://www.skills.google/paths/3273/course_templates/1275/labs/606594

  ```bash
  git clone https://github.com/nov05/gcp-adk-multiagent-systems.git
  cd gcp-adk-multiagent-systems
  export PATH=$PATH:"/home/${USER}/.local/bin"
  python3 -m pip install google-adk -r adk_multiagent_systems/requirements.txt
  ```

Task 2. Explore transfers between parent, sub-agent, and peer agents

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

Task 3. Use session state to store and retrieve specific information

  ```bash
  adk web --allow_origins "regex:https://.*\.cloudshell\.dev"
  ```

Task 4. Begin building a multi-agent system with a SequentialAgent  

