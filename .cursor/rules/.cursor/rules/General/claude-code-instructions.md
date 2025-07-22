claude --dangerously-skip-permissions

1. Always use /init to initialise a claude.md.
2. then run /ide
3. Use Shift tab to switch between the auto run mode and plan mode. Always start with plan mode.
4. Claude code shows you how full your context window is. run /compact to clear the claude code context windo, but keep a summary.
5. /clear removes all context window, and resets the general claude.md rules
6. Claude code's fuzzy searching / indexing is not as good. Make sure to either drag the file in or use @ to reference files
7. type in claude to start
8. Use kimi 2 using export

Temrinal commands:

Control A to go to first line, control k to delete, control W to delete words

you can use claude --dangerously-skip-permissions to bypass all permission checks and let Claude work uninterrupted until completion.

Figure this out.

https://docs.anthropic.com/en/docs/claude-code/common-workflows

Search this doc for it.

c. Use git worktrees
This approach shines for multiple independent tasks, offering a lighter-weight alternative to multiple checkouts. Git worktrees allow you to check out multiple branches from the same repository into separate directories. Each worktree has its own working directory with isolated files, while sharing the same Git history and reflog.

Using git worktrees enables you to run multiple Claude sessions simultaneously on different parts of your project, each focused on its own independent task. For instance, you might have one Claude refactoring your authentication system while another builds a completely unrelated data visualization component. Since the tasks don't overlap, each Claude can work at full speed without waiting for the other's changes or dealing with merge conflicts:

Create worktrees: git worktree add ../project-feature-a feature-a
Launch Claude in each worktree: cd ../project-feature-a && claude
Create additional worktrees as needed (repeat steps 1-2 in new terminal tabs)
Some tips:

Use consistent naming conventions
Maintain one terminal tab per worktree
If you’re using iTerm2 on Mac, set up notifications for when Claude needs attention
Use separate IDE windows for different worktrees
Clean up when finished: git worktree remove ../project-feature-a
d. Use headless mode with a custom harness
claude -p (headless mode) integrates Claude Code programmatically into larger workflows while leveraging its built-in tools and system prompt. There are two primary patterns for using headless mode:

1. Fanning out handles large migrations or analyses (e.g., analyzing sentiment in hundreds of logs or analyzing thousands of CSVs):

Have Claude write a script to generate a task list. For example, generate a list of 2k files that need to be migrated from framework A to framework B.
Loop through tasks, calling Claude programmatically for each and giving it a task and a set of tools it can use. For example: claude -p “migrate foo.py from React to Vue. When you are done, you MUST return the string OK if you succeeded, or FAIL if the task failed.” --allowedTools Edit Bash(git commit:\*)
Run the script several times and refine your prompt to get the desired outcome. 2. Pipelining integrates Claude into existing data/processing pipelines:

Call claude -p “<your prompt>” --json | your_command, where your_command is the next step of your processing pipeline
That’s it! JSON output (optional) can help provide structure for easier automated processing.
For both of these use cases, it can be helpful to use the --verbose flag for debugging the Claude invocation. We generally recommend turning verbose mode off in production for cleaner output.

What are your tips and best practices for working with Claude Code? Tag @AnthropicAI so we can see what you're building!
