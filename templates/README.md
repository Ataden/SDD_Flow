# Templates for AI Agents

This folder contains templates for the documents and specifications that an AI agent should use on the various steps of the workflow.

## Usage

**Option 1: As prompts in LLM chats (ChatGPT, Claude, etc):**
- copy and adjust the prompt to the LLM chat ('prompts/' folder)
- attach the proper template file from the 'templates' folder
- attach any other files that are required by the template

**Option 2: As custom commands in Claude Code (or similar):**
- templates are referenced in the prompts, doublecheck before you start
- create a symlink to the templates folder to the 'docs/templates' folder

```bash
# replace `<your_methodology_folder>/` to this methodology project folder and `<your_working_project_folder>` to your working project folder.
cd <your_working_project_folder>
ln -s <your_methodology_folder>/templates/ docs/
```

**Option 3: As a subagent in Claude Code (or similar):**
- similar to option 2

