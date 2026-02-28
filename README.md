# Claude Code Development Team

This repository serves as a template and development environment for Claude Code projects. It contains the necessary configuration files and tools to provide:

- Frontend development with React and TypeScript agent
- Backend development with Express.js and TypeScript agent
- Product Requirements Document (PRD) creation and task conversion agent
- Various Claude Code specific agents and skills
- Docker development environment setup

## Structure

- `.claude/` - Contains Claude-specific agent configurations and skill definitions
- `docker/` - Contains Docker configuration for development environment
- `.env.example` - Example environment variables configuration
- `CLAUDE.md` - Guidelines for Claude Code when working with this repository
- `.gitignore` - Standard git ignore patterns

## Getting Started

This repository is designed to be used with Claude Code's AI-powered development capabilities. The `.claude/` directory contains pre-configured agents that can be used to scaffold new projects, generate code, and assist with development tasks.

To begin development, you would typically:

1. Use the Claude Code agents to create new projects or components
2. Implement features using the provided tooling
3. Document requirements using the PRD tools when needed
4. Set up the development environment using the Docker configuration

## Docker Environment

The repository includes a Dockerfile that sets up a complete development environment with:

- Node.js 25 base image
- Git, sudo, vim, and Python tools
- Claude CLI installation
- Pre-configured Claude Code agents

## How to use?

### Build the image

Run this command to build the image:

```
docker build -t claude-dev-env:latest --file=./docker/Dockerfile .
```

Note you need to run this command from the root of this project.

### Use the image

To use the Docker image:

1. Copy the `.env.example` to `.env`
2. Update the `ANTHROPIC_BASE_URL` variable to your ollama instance
3. Create a volume for persistence:

```
docker volume create claude_project
```

4. Run the container with volume persistence:

```
docker run --rm -it --env-file .env --name claude-dev-env \
    --mount type=volume,source=claude_project,dst=/home/node/workspace/project \
    claude-dev-env:latest
```

### Run Claude Code

You can now run Claude Code with your ollama models

```
claude --dangerously-skip-permissions --model YOUR_CHOSEN_MODEL
```

You can then use the skills or agents to write your code.

## How to build an application

Once in Claude Code, you can follow these steps to create your application.

1. Create the Product Requirements Document (PRD)

```
Use the prd-creator agent to generate a Product Requirements Document for a website for people that want to upload their holiday pictures and generate a video automatically. It will use Image Recognition LLMs to identify the content of all uploaded images, then generate a script. THe script will be used to generate a video. The video will include the photos. Then create or update a CLAUDE.md file in the `./project/` folder to describe the content of the `./project/` folder for future usage by agents.
```

2. Convert the PRD to tasks

```
Use the prd-to-todo-converter agent to convert the PRD to tasks. Then let me know how many tasks you have created. Then update the CLAUDE.md file in the `./project/` folder to describe the content of the `./project/` folder for future usage by agents.
```

3. Execute the tasks
   Now you only need to repeat the following command until there is no more task left to do.

````
Read the first user story from `./project/tasks/prd-[some feature name].json` that is not `passes: true`. If there is one, start the relevant agent and execute the task. Update the `prd-[some feature name].json` `passes` task when the task is done. **IMPORTANT**: Do not execute more than 1 task from the task file. Update the `./project/CLAUDE.md` with the created content details. Display the summary of the tasks in this format:

```
Completed tasks: x
Remanining tasks: y
```

with `x` and `y` the correct number of relevant tasks.
````

4. Review and fix

Once all tasks are completed, you might have to review and ask Claude to fix whatever needs to.

5. Enjoy

You can now ask it to start both front-end and back-end applications. Note you might need to expose the necessary port in the docker container.
