The content of this file is to be placed in the main steering file (CLAUDE.md, GEMINI.md, etc)

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

<Project_Documentation>

All the project documentation is in the docs/ directory, number prefix of the documents coresponds to the step in the methodology.

**For the whole project:**
- Project Overview: `docs/1.4_concept.md`
- System Architecture: `docs/2_system_architecture.md`
- Feature Roadmap: `docs/3_feature_roadmap.md`
- Functional Design documents: `docs/5.1_functional_design.md`
- Technical Design documents (TDDoc): 
    - `docs/5.3_technical_design.md`
    - `docs/5.3_technical_design_data_models_schemas.md` (Section 3 of TDDoc)
    - `docs/5.3_technical_design_api_endpoints.md` (Section 4 of TDDoc)

- Deployment Architecture: `docs/4_deployment_architecture.md` (TBD)

**For each phase:**
- Implementation Plan: `docs/Phase<phase_number>/6.1_implementation_plan.md`
- For Each Step in 'Phase<phase_number>/<epic_number>.<step_number>' subfolder:
    - Implementation Report: `6.2_Implementation_report.md`
    - Testing Plan: `6.3_testing_plan.md`
    - Code Review Report (optional): `6.2_code_review_report.md`(TBD)
    - Testing Report: `6.3_testing_report.md`

</Project_Documentation>

<Project_Structure>
```
Root/
├── backend/                        # FastAPI backend - detailed structure in 'backend/CLAUDE.MD'                 # reference to the backend CLAUDE.md
├── frontend/                       # Next.js frontend - detailed structure in 'frontend/CLAUDE.MD'                # reference to the frontend CLAUDE.md
├── docs/                          # Comprehensive project documentation
│   ├── 1.4_concept.md             # Project concept and requirements
│   ├── 2_system_architecture.md   # System architecture overview
│   ├── 3_feature_roadmap.md       # Feature roadmap
│   ├── 5.1_functional_design.md   # Functional design specification for Phase <phase_number>  
│   ├── 5.3_technical_design*.md    # Technical implementation details for Phase <phase_number>
│   └── Phase<phase_number>/                    # Phase <phase_number> documentation
│       └── 6.1_implementation_plan.md   # Work breakdown structure and tasks for Phase <phase_number>
│       └── Step<epic_number>.<step_number>/
│           ├── 6.2_Implementation_report.md   # Implementation report for Step 
│           ├── 6.3_testing_plan.md   # Testing plan for Step 
│           ├── 6.2_code_review_report.md   # Code review report for Step 
│           └── 6.3_testing_report.md   # Testing report for Step 
│           └── 6.3_bug_fix_report.md   # Bug fix report for Step 
│   └── ... # other folders (guides, reports)
├── CLAUDE.MD                      # AI agent instructions
```
</Project_Structure>

<General_Code_Preferences>
* Always carefully read the project docs in /docs folder
* Always prefer simple solutions. It is very important!!! Do not over complicate things!
* Try to propose a solution that would introduce as few conde changes as posssible
* Pay attention to conserns separation
* Focus on the areas of code relevant to the task. Do not touch code that is unrelated to the task
* Avoid duplication of code whenever possible, which means checking for other areas of the codebase that might already have similar code and functionality  
* You are careful to only make changes that are requested or you are confident are well understood and related to the change being requested  
* When fixing an issue or bug, do not introduce a new pattern or technology without first exhausting all options for the existing implementation. And if you finally do this, make sure to remove the old implementation afterwards so we don’t have duplicate logic.  
* Keep the codebase very clean and organized  
* Avoid having files over 400–500 lines of code. Refactor at that point.  
* When you need a up to date docs on any external framework - use Context7 MCP
* When you need a icon for a ui component for some standard action, like delete, save, send, etc - DO NOT create a custom svg tag and use the external icon library (e.g. @radix-ui/react-icons) instead
* Always update the CLAUDE.md file - the Project Structure section if you make any changes to the project (add, remove, rename files or folders).
* If you hit a problem with not being able to run a command if it requires sudo, stop execution and ask me to to it manually
* Again - try not creating new code when you can reuse existing code with some updated. Avoid code duplication as much as possible. Always make minimal changes and produce minimal new code!!!! IT IS VERY IMPORTANT!!!    
</General_Code_Preferences>

<AVOID_SYCOPHANCY>
Sycophancy erodes trust. The assistant exists to help the user, not flatter them or agree with them all the time.

For objective questions, the factual aspects of your response should not differ based on how the user’s question is phrased. If the user pairs their question with their own stance on a topic, you may ask, acknowledge, or empathize with why the user might think that; however, you should not change your stance solely to agree with the user.

For subjective questions, you can articulate your interpretation and assumptions you’re making and aim to provide the user with a thoughtful rationale. For example, when the user asks you to critique their ideas or work, you should provide constructive feedback and behave more like a firm sounding board that users can bounce ideas off of — rather than a sponge that doles out praise.

So, dont agree with me all the time. Criticize my ideas and solutions and implement is only if you are sure that it is a good idea.
</AVOID_SYCOPHANCY>
