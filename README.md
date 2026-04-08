# Google Skills Lab - **Empower ADK agents with tools**   

* Lab - https://www.skills.google/paths/3273/course_templates/1275/labs/606590


* Task 1. Download and install ADK and code samples for this lab
  
  ```bash
  cd ~
  git clone https://github.com/nov05/gcp-adk-tools.git adk_tools
  export PATH=$PATH:"/home/${USER}/.local/bin"
  python3 -m pip install -r adk_tools/requirements.txt
  ```

* Task 2. Create a search app that will be used to ground responses on your own data

  ```bash
  export SEARCH_APP_ID=planet-search_1775604360365 ## ⚠️ Your search app ID
  ```
  
* Task 3. Use a Third-Party Tool from the LangChain Community

  ```bash
  cd ~/adk_tools
  cat << EOF > langchain_tool_agent/.env
  GOOGLE_GENAI_USE_VERTEXAI=TRUE
  # GOOGLE_CLOUD_PROJECT=qwiklabs-gcp-03-64c145f15937
  GOOGLE_CLOUD_LOCATION=global
  MODEL=gemini-2.5-flash
  EOF
  ```

  ```bash
  cp langchain_tool_agent/.env function_tool_agent/.env
  cp langchain_tool_agent/.env vertexai_search_tool_agent/.env
  ```

  In the Cloud Shell Terminal, from the adk_tools project directory, launch the Agent Development Kit Dev UI with the following commands:  
  ```bash
  adk web --allow_origins "regex:https://.*\.cloudshell\.dev"
  ```
  Or  
  ```bash
  adk web --allow_origins "regex:https://.*\.cloudshell\.dev" --reload_agents
  ```

  <img src="https://raw.githubusercontent.com/nov05/pictures/refs/heads/master/pic001/2026-04-07%2018_37_15-NVIDIA%20GeForce%20Overlay.jpg" width=800>   
  
  <img src="https://raw.githubusercontent.com/nov05/pictures/refs/heads/master/pic001/2026-04-07%2018_37_15-NVIDIA%20GeForce%20Overlay-01.gif" width=800>   
  
* Task 4. Use a function as a custom tool

  <img src="https://raw.githubusercontent.com/nov05/pictures/refs/heads/master/pic001/2026-04-07%2018_46_06-NVIDIA%20GeForce%20Overlay.jpg" width=800>  
  
* Task 5. Use Vertex AI Search as a tool to ground on your own data  
  
