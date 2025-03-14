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
