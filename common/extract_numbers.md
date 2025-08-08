Extract the current phase and step number from #ARGUMENTS and use it as <phase_number> and <step_number> in the file paths below. 
The <phase_number> is the first number of the step number (e.g. phase 2 for Step 2.1) 
The <step_number> consists both of the phase and a sequence of the step numbers (e.g. 2.1 for Step 2.1).

If you have managed to parse and extract the numbers, you must print it explicitly in the output as:
Current phase: <phase_number>
Current step: <step_number>

If you have not managed to parse and extract the pahse and step numbers, you must print that you could not parse and retry 2 times. Stop execution of the whole task after the second failed attempt and notify me.