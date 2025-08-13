# Various commonn files 

These files contain preferences and helper prompts that are referenced with @ in various places of the prompts (commands or subagents).

## current-task-context.md

Helper prompt to extract Phase and Step numbers from task_context.ini file.

## running-services.md

Helper prompt to instruct the agent to check if the services are running.

## testing-preferences.md

Preferences and conventions for the testing process.

## development-standards.md

Development standards for the project (TBD)


## Usage:
Copy or create symlinks to the common files in your working project folder to the doc/common/ folder.

```bash
# replace `<your_methodology_folder>/` to this methodology project folder and `<your_working_project_folder>` to your working project folder.

cd <your_working_project_folder>/docs/common

ln -s /mnt/f/AICoding/common/current-task-context.md \
ln -s /mnt/f/AICoding/common/running-services.md \
ln -s /mnt/f/AICoding/common/testing-preferences.md \
ln -s /mnt/f/AICoding/common/development-standards.md

```