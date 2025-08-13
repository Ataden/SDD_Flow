# AI Coding Agent Prompts

This folder contains prompts for AI coding agents. Each prompt is a separate file.

## Usage

**Option 1: As prompts in LLM chats (ChatGPT, Claude, etc):**
- copy the prompt to the LLM chat
- attach the proper template file from the `templates` folder
- attach any other files that are required by the prompt

**Option 2: As custom commands in Claude Code (or similar):**
- create a symlink to the prompt file to the '.claude/commands' folder in your project
symlink creation commands:
```bash
cd .claude/commands
ln -s /path/to/prompt_template.md your_command_name.md
```

Actual ln commands:

```bash
# Create links for all prompt files
# replace `<your_methodology_folder>/` to this methodology project folder and `<your_working_project_folder>` to your working project folder.
cd <your_working_project_folder>

ln -s <your_methodology_folder>/prompts/1.1_initial_hypothesis.md .claude/commands/hypothesis.md \
ln -s <your_methodology_folder>/prompts/1.3_market_research_report.md .claude/commands/market-research.md \
ln -s <your_methodology_folder>/prompts/2_system_architecture.md .claude/commands/architecture.md \
ln -s <your_methodology_folder>/prompts/2_system_architecture_review.md .claude/commands/architecture-review.md \
ln -s <your_methodology_folder>/prompts/3_feature_roadmap.md .claude/commands/roadmap.md \
ln -s <your_methodology_folder>/prompts/5.1_functional_design.md .claude/commands/functional-design.md \
ln -s <your_methodology_folder>/prompts/5.3._technical_design_lint.md .claude/commands/TDDoc-lint.md \
ln -s <your_methodology_folder>/prompts/5.3_technical_design.md .claude/commands/TDDoc.md \
ln -s <your_methodology_folder>/prompts/5.3_technical_design_review.md .claude/commands/TDDoc-review.md \
ln -s <your_methodology_folder>/prompts/6.1_implementation_plan.md .claude/commands/plan.md \
ln -s <your_methodology_folder>/prompts/6.1_implementation_plan_review.md .claude/commands/plan-review.md \
ln -s <your_methodology_folder>/prompts/6.2_code_implementation.md .claude/commands/do.md \
ln -s <your_methodology_folder>/prompts/6.2_code_review.md .claude/commands/code-review.md \
ln -s <your_methodology_folder>/prompts/6.3_fix_bug.md .claude/commands/fix-bug.md \
ln -s <your_methodology_folder>/prompts/6.3_fix_test.md .claude/commands/fix-test.md \
ln -s <your_methodology_folder>/prompts/6.3_testing.md .claude/commands/test.md 

```

**Option 3: As a subagent in Claude Code (or similar):**
- create a symlink to the prompt file to the '.claude/agents' folder in your project (similair to the commands, see above)