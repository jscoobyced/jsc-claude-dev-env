# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Claude Code development repository that serves as a template or skeleton for projects. The repository contains:

- A `.claude/` directory with agent and skill configurations
- Docker setup for development environment
- Environment configuration files

## Development Setup

This repository provides a complete development environment with:

- Frontend development with React and TypeScript agent
- Backend development with Express.js and TypeScript agent
- Product Requirements Document (PRD) creation and task conversion agent
- Various Claude Code specific agents and skills

## Available Tools and Agents

The repository includes several Claude Code agents:

- frontend-react-builder.md: For creating React frontend applications
- backend-express-ts-expert.md: For creating Express.js backend applications with TypeScript
- prd-generator.md: For creating Product Requirements Documents
- prd-to-todo-converter.md: For converting PRDs to task lists

And skills:

- create-prd: For generating PRDs
- prd-to-tasks: For converting PRDs to task formats

## Key Directories

- `.claude/` - Contains Claude-specific configuration and agent definitions
- `docker/` - Contains Docker configuration for development environment
- `.env.example` - Example environment variables configuration
- `.gitignore` - Standard git ignore patterns

## Development Approach

When working on this repository, follow these guidelines:

1. Use the provided Claude Code agents for scaffolding and development tasks
2. Create appropriate project structure following standard conventions
3. Implement features using the tools and frameworks specified in the agent configurations
4. Document new features using the PRD tools when appropriate

## Docker Environment

This repository includes a Dockerfile that sets up a development environment with:
- Node.js 25 base image
- Git, sudo, vim, and Python tools
- Claude CLI installation
- Pre-configured Claude Code agents

## Environment Variables

The repository includes `.env.example` which shows the expected environment variables:
- `ANTHROPIC_API_KEY`: API key for Anthropic services
- `ANTHROPIC_BASE_URL`: Base URL for Anthropic services (default: http://localhost:11434)
- `ANTHROPIC_AUTH_TOKEN`: Authentication token for Anthropic services (default: ollama)

## Common

For JavaScript package management, it's recommended to use either `yarn` or `pnpm` as your package manager. Both are excellent choices that offer significant advantages over npm:

- **yarn**: Offers fast installation, deterministic installs, and a rich set of features for managing dependencies
- **pnpm**: Provides faster installation, disk space savings, and better security by using a content-addressable storage system

Choose one and stick with it throughout the project to maintain consistency.
