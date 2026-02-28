# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Environment Overview

This repository is a Claude Code workspace containing agent definitions and skills for Claude Code. It is not a typical source code repository with application files, but rather a directory structure for managing Claude Code's agent capabilities.

## Directory Structure

- `.claude/agents/` - Contains agent definitions for Claude Code's specialized agents
- `.claude/skills/` - Contains skill definitions for Claude Code's specialized tools
- `project/` - Empty project directory that may be used for development tasks

## Important Guidelines

When an agent is suitable for a task, **ALWAYS** prefer using agents to do a task instead of a skill. The agent will then determine if it can use a skill.
When a skill is suitable for an agent to do a task, agents should **ALWAYS** use that skill.

## Available Agents

### 1. frontend-agent

**Purpose**: Create modern ReactJS applications with TypeScript, React Router, and Tailwind CSS v4+
**When to use**: When users want to generate complete front-end code structures, components, or implementations for React applications with routing and styling

### 2. backend-agent

**Purpose**: Create Express.js back-end applications with TypeScript
**When to use**: When implementing CORS configurations, JWT authentication, database integration (SQL and NoSQL), or building RESTful API endpoints

### 3. prd-creator

**Purpose**: Create comprehensive Product Requirements Documents (PRDs)
**When to use**: When documenting new feature requirements, product initiatives, or formalizing requirements before development cycles

### 4. prd-to-todo-converter

**Purpose**: Convert PRDs into structured to-do list format
**When to use**: When breaking down PRD requirements into actionable user stories with acceptance criteria for development teams

### 5. db-expert

**Purpose**: Database integration and data model management
**When to use**: When creating database integrations, managing data models, or optimizing database performance

### 6. general-purpose

**Purpose**: General research and complex tasks
**When to use**: For broad research, analysis, or tasks that don't fit into specialized categories

### 7. Explore

**Purpose**: Fast agent for exploring codebases
**When to use**: When needing to quickly explore and understand codebase structures or find specific information

### 8. Plan

**Purpose**: Software architect agent for designing implementation plans
**When to use**: When designing software architecture, planning implementation strategies, or creating detailed development approaches

### 9. claude-code-guide

**Purpose**: Answer questions about Claude Code CLI, API, and SDK
**When to use**: When users need information about Claude Code's interface, capabilities, or development practices

## Available Skills

### 1. create-prd

**Purpose**: Generate Product Requirements Documents for new features
**When to use**: When planning a feature, starting a new project, or creating a PRD from scratch

### 2. prd-to-tasks

**Purpose**: Convert PRDs to structured JSON format for implementation
**When to use**: When converting existing PRDs into actionable task lists for development teams

## Development Workflow

This workspace is designed for:

- Creating and managing Claude Code agents
- Developing specialized tools for Claude Code
- Supporting various development tasks through Claude Code's agent system
- Providing structured approaches to software engineering tasks

## Commands

Since this is a workspace for Claude Code agents and not a source code repository, there are no standard build, lint, or test commands. Instead, work is performed through the Claude Code interface using the available agents and skills.

## Key Files

- `.claude/agents/frontend-agent.md` - Defines the frontend agent for React development
- `.claude/agents/backend-agent.md` - Defines the backend agent for Express.js development
- `.claude/skills/create-prd/SKILL.md` - Defines the PRD creation skill
- `.claude/skills/prd-to-tasks/SKILL.md` - Defines the PRD to tasks conversion skill

## Usage Notes

This repository is meant to be used as a development environment for Claude Code agents and skills. When working with this repository, use the Claude Code interface to invoke the various agents and skills defined here to perform tasks.

The agents and skills are designed to support a comprehensive development workflow:

- Start with prd-creator to define requirements
- Use prd-to-todo-converter to break down requirements into actionable tasks
- Implement features using frontend-agent, backend-agent, or db-expert as needed
- Leverage general-purpose agents for research or complex problem-solving
