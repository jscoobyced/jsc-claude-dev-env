---
name: scaffold
description: Scaffold skills file for the Claude Code development environment. Use as a template for creating new skills.
---

# Scaffold

This skill is to created boilerplate for new code. It will provide 2 options:

- Scaffolding of a new front-end project with Vite JS, React, and TypeScript
- Scaffolding of a new back-end project with Node.js, Express, and TypeScript

## Front-end Scaffolding

When the user selects the front-end scaffolding option, the agent will run the following command to create a new Vite JS project with React and TypeScript:

```bash
cd project && yarn create jsc-vite-react-ts "<feature name>"
```

## Back-end Scaffolding

When the user selects the back-end scaffolding option, the agent will create a new folder called `<feature name>/backend` in the `./project/` directory. The agent will then set up a basic Node.js and Express project structure with TypeScript.

# Result

Once the scaffolding process is complete, update the `./project/` CLAUDE.md file, then stop processing more task until the user asks to do so.
