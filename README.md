# VibeCoder

A modern React TypeScript application for collaborative coding and project management.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
  - [Code of Conduct](#code-of-conduct)
  - [Development Workflow](#development-workflow)
  - [Pull Request Process](#pull-request-process)
  - [Coding Standards](#coding-standards)
- [License](#license)

## Overview

VibeCoder is a comprehensive platform designed to streamline collaboration for development teams. It provides tools for project management, code review, document sharing, and meeting coordination in a unified interface.

## Features

- **Project Management**: Track and manage development projects
- **Code Review**: Collaborative code review system
- **Document Sharing**: Create and share project documentation
- **Meeting Coordination**: Schedule and manage team meetings
- **Interactive Game**: Built-in game for team building and relaxation

## Getting Started

### Prerequisites

- Node.js (v14.x or higher)
- npm (v7.x or higher) or yarn (v1.22.x or higher)
- Firebase account (for authentication and database)

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/vibecoder.git
   cd vibecoder
   ```

2. Install dependencies
   ```bash
   npm install
   # or
   yarn install
   ```

3. Set up environment variables
   - Create a `.env.local` file in the root directory
   - Add your Firebase configuration:
     ```
     NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
     NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_auth_domain
     NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
     NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_storage_bucket
     NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
     NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
     ```

4. Start the development server
   ```bash
   npm run dev
   # or
   yarn dev
   ```

## Usage

After starting the development server, navigate to `http://localhost:3000` in your browser. You'll need to sign in with your account to access the dashboard and its features.

## Contributing

We love your input! We want to make contributing to VibeCoder as easy and transparent as possible, whether it's:

- Reporting a bug
- Discussing the current state of the code
- Submitting a fix
- Proposing new features
- Becoming a maintainer

### Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

### Development Workflow

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Pull Request Process

1. Ensure any install or build dependencies are removed before the end of the layer when doing a build.
2. Update the README.md with details of changes to the interface, this includes new environment variables, exposed ports, useful file locations, and container parameters.
3. Increase the version numbers in any examples files and the README.md to the new version that this Pull Request would represent.
4. The Pull Request will be merged once you have the sign-off of at least one maintainer.

### Coding Standards

#### Component-Based Architecture

- Build small, focused components (< 300 lines)
- Use composition over inheritance
- One main component per file

#### Type Safety

- Define explicit interfaces for all props
- Use TypeScript features to ensure type safety
- Avoid using `any` type

#### Performance First

- Memoize expensive calculations and callbacks
- Implement virtualization for long lists
- Use React.memo for pure components

#### Maintainable Code

- Follow consistent naming conventions
- Document complex logic and component APIs
- Write tests for critical functionality

#### File Structure

```
src/
├── components/  # UI components organized by domain
├── hooks/       # Custom React hooks
├── pages/       # Route components
├── types/       # TypeScript definitions
├── utils/       # Helper functions
└── lib/         # Third-party integrations
```

#### Naming Conventions

| Item | Convention | Example |
|------|------------|---------|
| Component files | PascalCase | `Button.tsx` |
| Utility files | camelCase | `formatDate.ts` |
| CSS modules | kebab-case | `button-styles.module.css` |
| Component names | PascalCase | `UserProfile` |
| Functions | camelCase | `calculateTotal` |
| Constants | UPPER_SNAKE_CASE | `MAX_ITEMS` |

#### Component Template

```tsx
// Imports
import React from 'react';
import type { ButtonProps } from './types';

// Component interface
interface Props {
  label: string;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
}

// Component definition
export const Button: React.FC<Props> = ({ 
  label, 
  onClick, 
  variant = 'primary' 
}) => {
  // 1. Hooks
  const [isHovered, setIsHovered] = useState(false);
  
  // 2. Event handlers
  const handleMouseEnter = () => setIsHovered(true);
  const handleMouseLeave = () => setIsHovered(false);
  
  // 3. Return JSX
  return (
    <button
      className={`btn btn-${variant}`}
      onClick={onClick}
      onMouseEnter={handleMouseEnter}
      onMouseLeave={handleMouseLeave}
    >
      {label}
    </button>
  );
};
```

#### Best Practices

- **State Management**
  - Keep state as local as possible
  - Use React Query for server state
  - Use Context API sparingly

- **Performance**
  - Use `useMemo` for expensive calculations
  - Use `useCallback` for event handlers passed as props
  - Implement virtualization for long lists

- **Accessibility**
  - Use semantic HTML elements
  - Add proper ARIA attributes
  - Ensure keyboard navigation works
  - Maintain sufficient color contrast

- **Testing**
  - Write tests for critical user interactions
  - Test component props and state changes
  - Place tests next to components (`Component.test.tsx`)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.


# Contributing to CCO (Chief Cognitive Officer)

Thank you for your interest in contributing to CCO! This document provides guidelines and instructions for contributing to our project.

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). We expect all contributors to help create a positive and inclusive environment.

## Getting Started

### Prerequisites

- Node.js 18.x or later
- npm 9.x or later
- Firebase account
- OpenAI API key
- Git

### Development Environment Setup

1. **Fork the repository:**
   
   Start by forking the repository using the "Fork" button on GitHub.

2. **Clone your fork:**

   ```bash
   git clone https://github.com/YOUR-USERNAME/cco-app.git
   cd cco-app
   ```

3. **Add the upstream remote:**

   ```bash
   git remote add upstream https://github.com/cco-vibe/cco-app.git
   ```

4. **Install dependencies:**

   ```bash
   npm install
   ```

5. **Set up environment variables:**

   ```bash
   cp .env.example .env.local
   ```

   Edit `.env.local` with your API keys and configuration.

6. **Set up Firebase:**
   
   Create a Firebase project for development and update `.env.local` with your Firebase configuration.

7. **Start the development server:**

   ```bash
   npm run dev
   ```

   The application will be available at [http://localhost:3000](http://localhost:3000).

## Development Workflow

We follow a standard GitHub workflow:

1. **Create a branch:**
   
   Create a branch for your feature or bugfix. Use a descriptive name that reflects the changes you're making:

   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b bugfix/issue-description
   ```

   Follow our [branch naming convention](./docs/DEVELOPMENT_GUIDELINES.md#branch-naming-strategy).

2. **Make your changes:**
   
   Implement your changes following our [coding standards](./docs/DEVELOPMENT_GUIDELINES.md#coding-standards).

3. **Write and run tests:**

   Ensure your code has appropriate tests and all tests pass:

   ```bash
   npm run test
   ```

4. **Lint your code:**

   Ensure your code follows our linting rules:

   ```bash
   npm run lint
   ```

5. **Commit your changes:**

   We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification for commit messages:

   ```bash
   git commit -m "feat: add user preference settings"
   # or
   git commit -m "fix: resolve authentication redirect issue"
   ```

   For more details, see our [commit message conventions](./docs/DEVELOPMENT_GUIDELINES.md#commit-message-conventions).

6. **Stay updated with upstream:**

   Regularly fetch updates from the upstream repository:

   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

7. **Push your branch:**

   ```bash
   git push origin feature/your-feature-name
   ```

8. **Create a Pull Request:**
   
   Open a pull request from your fork to the main repository. Follow the PR template and provide detailed information about your changes.

## Pull Request Process

1. **Fill out the PR template** with all required information.
2. **Link any related issues** using keywords like "Fixes #123" or "Relates to #456".
3. **Ensure all CI checks pass**, including tests, linting, and type checking.
4. **Request reviews** from appropriate team members.
5. **Address review feedback** in a timely manner.
6. **Once approved**, your PR will be merged by a maintainer.

### PR Review Criteria

Pull requests are evaluated based on:

- Code quality and adherence to our [development guidelines](./docs/DEVELOPMENT_GUIDELINES.md)
- Test coverage and quality
- Documentation quality
- Performance impact
- Accessibility considerations
- Security implications

## Issue Reporting Guidelines

### Bug Reports

When reporting a bug, please include:

1. **Clear and descriptive title**
2. **Steps to reproduce the bug**
3. **Expected behavior**
4. **Actual behavior**
5. **Screenshots** if applicable
6. **Environment information**:
   - Browser and version
   - Operating system
   - Device information
7. **Additional context** that might be helpful

### Feature Requests

When suggesting a feature, please include:

1. **Clear and descriptive title**
2. **Detailed description of the proposed feature**
3. **Use cases** that would benefit from this feature
4. **Explanation of why it should be added** to the project
5. **Mock-ups or examples** if applicable

### Using Issue Templates

We provide issue templates for bug reports, feature requests, and other types of issues. Please use the appropriate template when creating a new issue.

## Documentation

Good documentation is essential for our project. When contributing:

1. **Update documentation** related to your changes.
2. **Document new features** thoroughly.
3. **Use clear, concise language**.
4. **Include code examples** where appropriate.
5. **Update READMEs** if needed.

## Testing

We prioritize testing to maintain code quality:

1. **Write unit tests** for new functionality.
2. **Write integration tests** for feature interactions.
3. **Ensure all tests pass** before submitting PRs.
4. **Maintain or improve test coverage**.

See our [Testing Strategy](./docs/TESTING_STRATEGY.md) for more details.

## Accessibility

Accessibility is a core value of our project:

1. **Ensure all UI components meet WCAG 2.1 AA standards**.
2. **Test with screen readers** and keyboard navigation.
3. **Maintain appropriate color contrast**.
4. **Provide alternative text for images**.

See our [Accessibility Guidelines](./docs/ACCESSIBILITY_GUIDELINES.md) for more information.

## Code Review Process

Our code review process aims to maintain code quality and share knowledge:

1. **Reviews are required** before merging PRs.
2. **Reviewers should provide constructive feedback**.
3. **Authors should respond to feedback** in a timely manner.
4. **Resolve all conversations** before merging.
5. **Follow our [Code Review Checklist](./docs/CODE_REVIEW_CHECKLIST.md)**.

## Community

Join our community channels to connect with other contributors:

- **Discord**: [Join our server](https://discord.gg/cco-vibe)
- **Twitter**: [@cco_vibe](https://twitter.com/cco_vibe)
- **GitHub Discussions**: [cco-vibe/cco-app/discussions](https://github.com/cco-vibe/cco-app/discussions)

## Recognition

We value and recognize all contributors:

- All contributors are listed in our [CONTRIBUTORS.md](CONTRIBUTORS.md) file.
- Significant contributions are highlighted in release notes.
- Regular contributors may be invited to join the core team.

## Additional Resources

- [Development Guidelines](./docs/DEVELOPMENT_GUIDELINES.md)
- [Code Review Checklist](./docs/CODE_REVIEW_CHECKLIST.md)
- [Testing Strategy](./docs/TESTING_STRATEGY.md)
- [Accessibility Guidelines](./docs/ACCESSIBILITY_GUIDELINES.md)
- [Project Roadmap](./docs/PROJECT_ROADMAP.md)
- [API Documentation](./docs/API_DOCUMENTATION.md)

## Questions?

If you have any questions about contributing, please:

1. Check the documentation.
2. Look for existing issues or discussions.
3. Open a new discussion if your question is not addressed.
4. Contact us at [contributors@cco-vibe.com](mailto:contributors@cco-vibe.com).

Thank you for contributing to CCO! 
