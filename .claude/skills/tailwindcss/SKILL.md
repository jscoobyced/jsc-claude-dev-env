---
name: tailwindcss
description: Tailwind CSS framework patterns including utility-first styling, configuration, and version 4.x+ usage. Use when working with Tailwind CSS v4+ for styling React applications.
---

# Tailwind CSS Skill

This skill provides guidance for working with Tailwind CSS v4.x+ in React applications. It ensures consistent usage of the latest Tailwind CSS features and best practices.

## Overview

This skill is designed to help with Tailwind CSS development following the project's established conventions. It enforces the use of Tailwind CSS v4.x+ and ensures consistent styling practices across all React projects.

## Key Requirements

### Version Enforcement

- **Always use Tailwind CSS v4.x+** for all projects
- Never use older versions of Tailwind CSS
- Ensure all projects are configured with the latest Tailwind CSS features

### Configuration

- Use `tailwind.config.js` or `tailwind.config.ts` for configuration
- Configure `content` paths to include all relevant files
- Enable necessary plugins and features for v4.x+ compatibility

### Usage Guidelines

- Use utility-first approach for styling
- Leverage Tailwind's dark mode support
- Utilize custom variants and plugins where appropriate
- Follow consistent naming conventions for classes

## Best Practices

1. **Utility-First Approach**: Use Tailwind's utility classes directly in your JSX rather than creating custom CSS classes.

2. **Configuration Consistency**:
   - Ensure all projects use the same Tailwind configuration structure
   - Use `content` paths that include all relevant source files
   - Configure `theme` extensions consistently across projects

3. **Dark Mode Support**:
   - Implement dark mode using Tailwind's built-in dark mode features
   - Use `dark:` prefix for dark mode variants
   - Configure `darkMode` strategy in `tailwind.config.js`

4. **Performance Optimization**:
   - Use `purge` or `content` configuration to remove unused styles
   - Minimize custom CSS to maintain utility-first approach
   - Leverage Tailwind's JIT compiler for better performance

5. **Version Compatibility**:
   - All projects must use Tailwind CSS v4.x+
   - Ensure plugins and features are compatible with v4.x+
   - Keep dependencies updated to latest versions

## Configuration Example

```javascript
// tailwind.config.js
module.exports = {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
  darkMode: "class", // or 'media'
};
```

## Sample CSS Usage

- app.css

```css
@import "tailwindcss";
@import "./colors.css";

@variant dark (&:where(.dark, .dark *));

@theme {
  --font-family-sans: "Inter";
}
```

- colors.css

```css
@theme {
  /* Primary colors */
  --color-primary: #ffffff;
  --color-primary-foreground: #111827;

  /* Secondary colors */
  --color-secondary: #f3f4f6;
  --color-secondary-foreground: #4b5563;

  /* Button colors */
  --color-button-primary: #3b82f6;
  --color-button-primary-hover: #2563eb;
  --color-button-primary-active: #1d4ed8;
  --color-button-secondary: #e5e7eb;
  --color-button-secondary-hover: #d1d5db;
  --color-button-secondary-active: #9ca3af;
}

.dark {
  /* Primary colors */
  --color-primary: #111827;
  --color-primary-foreground: #ffffff;

  /* Secondary colors */
  --color-secondary: #1f2937;
  --color-secondary-foreground: #d1d5db;

  /* Button colors for dark mode */
  --color-button-secondary: #374151;
  --color-button-secondary-hover: #4b5563;
  --color-button-secondary-active: #6b7280;
}
```

## Troubleshooting

If you encounter issues with Tailwind CSS v4.x+:

1. Ensure all dependencies are properly installed with `yarn`
2. Check that `tailwind.config.js` is correctly configured
3. Verify that the `content` paths include all relevant source files
4. Make sure you're using compatible versions of plugins and dependencies

## References

- [Tailwind CSS v4 Documentation](https://tailwindcss.com/docs)
- [Tailwind CSS v4 Release Notes](https://tailwindcss.com/blog/tailwind-css-v4)
- [React Documentation](https://react.dev/)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
