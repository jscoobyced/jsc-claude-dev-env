---
name: react
description: React.js framework patterns including component design, state management, hooks, and React-specific APIs. Use when working with React components, hooks, or React applications.
---

# React Skill

This skill provides guidance for creating and working with React applications in this project. It enforces the use of `yarn` as the package manager.

## Overview

This skill is designed to help with React development following the project's established conventions. It ensures consistency in package management and project setup by enforcing the use of `yarn`.

## Key Requirements

### Package Management

- **Always use `yarn`** for package management
- Never use `npm` or `pnpm` for React projects in this repository
- All React project dependencies must be managed through `yarn`

### Project Structure

- All React projects should be created in the `frontend` directory
- Follow the standard Vite + React + TypeScript project structure
- Maintain consistent directory naming and file organization

### Working with Existing Projects

- Always use `yarn` for installing dependencies:
  ```bash
  yarn install
  ```
- For adding new dependencies:
  ```bash
  yarn add <package-name>
  ```
- For removing dependencies:
  ```bash
  yarn remove <package-name>
  ```

### Development Commands

- Start development server:
  ```bash
  yarn dev
  ```
- Build for production:
  ```bash
  yarn build
  ```
- Run tests:
  ```bash
  yarn test
  ```

## Best Practices

1. **Consistent Tooling**: All React projects must use the same tooling stack (Vite, React, TypeScript) to maintain consistency across the codebase.

2. **Dependency Management**: Use `yarn` exclusively for managing all React project dependencies to ensure deterministic installs and consistent environments.

3. **Project Organization**: All frontend projects should be organized under the `frontend` directory following the structure established by `create-jsc-vite-react-ts`.

4. **Version Consistency**: Ensure all React projects use compatible versions of core dependencies to prevent conflicts.

5. **Documentation**: When creating new React projects, ensure proper documentation is included following the project's conventions.

## Troubleshooting

If you encounter issues with `yarn create jsc-vite-react-ts`:

1. Ensure `yarn` is properly installed and configured
2. Check that you have internet connectivity
3. Verify that the `create-jsc-vite-react-ts` package is available in the package registry

## References

- [Vite Documentation](https://vitejs.dev/guide/)
- [React Documentation](https://react.dev/)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Yarn Documentation](https://yarnpkg.com/getting-started)
