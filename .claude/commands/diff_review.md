# Execute each task in the order given to conduct a thorough code review. 

## Task 1: Create diff.txt
Create diff.txt under diff_review/ folder

## Task 2: git diff and append

Then run git diff and append the output to the file. 

## Task 3: just-rompt multil-llm tool call

Then use that file as the input to this just-prompt tool call. 

prompts_from_file_to_file(
    from_file = diff.md,
    models = "openai:03-mini, anthropic:claude-3.7-sonnet-20250219:4k, gemini-gemini-2.0-flash-thinking-exp"
    output_dir = diff_review
)

## Task 4: Read the output files and synthesise

Then read the output files and think hard to synthesise the results into a single files called 'diff_review/fusion_diff_review.md' following the original instructions plus any additional instructions or callouts you think are needed to create the best possible version. 

## Task 4: Present the results 