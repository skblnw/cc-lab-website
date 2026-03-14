# Contributing to CC Lab Website

Thank you for your interest in contributing to CC Lab Website!

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Reporting Issues](#reporting-issues)
- [Contact](#contact)

## Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to [Chun.Chan@xjtlu.edu.cn](mailto:Chun.Chan@xjtlu.edu.cn).

## Getting Started

### Prerequisites
- Node.js v18 or higher
- npm v9 or higher

### Development Setup

```bash
# Clone the repository
git clone https://github.com/colinzyang/cc.lab.xjtlu.github.io.git
cd cc.lab.xjtlu.github.io

# Install dependencies
npm install

# Start development server
npm run dev
```

### Project Structure

```
├── components/        # React page components
├── src/
│   ├── context/       # React Context providers
│   └── lib/           # Utilities and data loading
├── public/
│   ├── data/          # JSON data files (CMS-managed)
│   ├── admin/         # Decap CMS configuration
│   └── assets/        # Static images and files
└── src/index.css      # Tailwind CSS theme
```

## Development Workflow

### Branch Naming Convention

- `feature/` - New features (e.g., `feature/add-dark-mode`)
- `fix/` - Bug fixes (e.g., `fix/navbar-mobile-menu`)
- `docs/` - Documentation updates (e.g., `docs/update-readme`)
- `refactor/` - Code refactoring (e.g., `refactor/simplify-data-loader`)
- `chore/` - Maintenance tasks (e.g., `chore/update-dependencies`)

### Before Submitting a PR

1. **Ensure the build passes**
   ```bash
   npm run build
   ```

2. **Test your changes locally**
   ```bash
   npm run preview
   ```

3. **Verify responsiveness** - Test on mobile, tablet, and desktop viewports

4. **Check for TypeScript errors** - The build will fail on any type errors

## Coding Standards

### TypeScript

- **Strict mode is enabled** - All code must pass strict type checking
- **No `any` types** - Use proper type definitions or `unknown` with type guards
- **Explicit return types** - Add return type annotations for functions
- **Interface over type** - Prefer `interface` for object shapes
- **No unused variables** - Will cause build failure

### React

- **Functional components only** - Use hooks for state management
- **Props interface** - Define props as typed interfaces
- **Event handlers** - Use proper event types (e.g., `React.MouseEvent`)

```typescript
// Good example
interface ButtonProps {
  label: string;
  onClick: (e: React.MouseEvent<HTMLButtonElement>) => void;
}

export const Button: React.FC<ButtonProps> = ({ label, onClick }) => {
  return <button onClick={onClick}>{label}</button>;
};
```

### Styling

- **Tailwind CSS only** - No inline styles or CSS modules
- **Dark mode support** - Add `dark:` variants for new UI components
- **Responsive design** - Use Tailwind breakpoints (`md:`, `lg:`, etc.)
- **Theme colors** - Use `primary` and custom theme colors defined in `src/index.css`

### File Organization

- One component per file
- Named exports preferred over default exports
- Keep components in the appropriate directory:
  - Page components → `components/`
  - Shared utilities → `src/lib/`

## Commit Guidelines

### Commit Message Format

```
<type>(<scope>): <subject>

<body>(optional)

<footer>(optional)
```

### Types

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Code style (formatting, semicolons) |
| `refactor` | Code change without fix or feature |
| `perf` | Performance improvement |
| `test` | Adding or updating tests |
| `chore` | Build process or auxiliary tools |

### Examples

```
feat(member): add alumni section to member page

fix(navbar): resolve mobile menu animation issue

docs(readme): update installation instructions
```

### Rules

- Use imperative mood ("add feature" not "added feature")
- Lowercase subject line
- No period at end of subject
- Subject line under 50 characters
- Body explains what and why, not how

## Pull Request Process

### PR Checklist

- [ ] Branch follows naming convention
- [ ] Commit messages follow guidelines
- [ ] Build passes (`npm run build`)
- [ ] TypeScript has no errors
- [ ] Changes tested locally
- [ ] Responsive design verified
- [ ] Dark mode tested (if applicable)

### PR Title Format

Same as commit message format:
```
<type>(<scope>): <subject>
```

### PR Description Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
How were these changes tested?

## Screenshots
(If applicable)
```

### Review Process

1. At least one approval required
2. All conversations must be resolved
3. Build must pass
4. Squash and merge preferred for feature branches

## Reporting Issues

### Bug Reports

Use [GitHub Issues](https://github.com/colinzyang/cc.lab.xjtlu.github.io/issues) and include:

- **Description** - Clear description of the bug
- **Steps to reproduce** - Numbered list of steps
- **Expected behavior** - What should happen
- **Actual behavior** - What actually happens
- **Screenshots** - If applicable
- **Environment** - OS, browser, Node.js version

### Feature Requests

- **Description** - Clear description of the feature
- **Use case** - Why is this feature needed?
- **Alternatives** - Have you considered alternatives?

## Contact

For questions or discussions:

- **Kevin Chan (Principal Investigator)**: [Chun.Chan@xjtlu.edu.cn](mailto:Chun.Chan@xjtlu.edu.cn)
- **GitHub Issues**: For bugs and feature requests

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
