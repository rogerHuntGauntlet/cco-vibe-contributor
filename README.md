# CCO-VIBE

A modern React TypeScript application for collaborative coding and project management, powered by the Morpheus Network.

## Overview

CCO-VIBE is a comprehensive platform designed to streamline collaboration for development teams. It provides tools for project management, code review, document sharing, and meeting coordination in a unified interface. As a participant in the [Morpheus Network](https://mor.org), CCO-VIBE leverages decentralized AI infrastructure for enhanced capabilities.

## Documentation

- [Architecture Documentation](docs/ARCHITECTURE.md)
- [API Documentation](docs/API.md)
- [Contributing Guidelines](.github/CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [License Information](LICENSE.md)
- [Morpheus Integration](docs/MORPHEUS_INTEGRATION.md)

## Project Status

The project is currently in the planning and documentation phase. The actual implementation will be available in the [COMING_SOON](COMING_SOON) directory.

## Features (Planned)

- **Project Management**: Track and manage development projects
- **Code Review**: Collaborative code review system
- **Document Sharing**: Create and share project documentation
- **Meeting Coordination**: Schedule and manage team meetings
- **Analytics**: Track project and team performance metrics

## Getting Started

### Prerequisites

- Node.js (v16.x or higher)
- npm (v8.x or higher) or yarn (v1.22.x or higher)
- Git
- Morpheus CLI tools (optional, for AI features)

### Development Setup

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/cco-vibe.git
   cd cco-vibe
   ```

2. Install dependencies
   ```bash
   npm install
   # or
   yarn install
   ```

3. Set up environment variables
   ```bash
   cp .env.example .env.local
   ```
   Edit `.env.local` with your configuration.

4. (Optional) Set up Morpheus integration
   ```bash
   npm run setup-morpheus
   # or
   yarn setup-morpheus
   ```

5. Start the development server
   ```bash
   npm run dev
   # or
   yarn dev
   ```

## Contributing

We welcome contributions! Please read our [Contributing Guidelines](.github/CONTRIBUTING.md) before submitting any changes.

### Development Process

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Testing

```bash
# Run unit tests
npm run test

# Run E2E tests
npm run test:e2e

# Run linting
npm run lint

# Run type checking
npm run type-check
```

## Deployment

The project uses GitHub Actions for CI/CD. See the [workflow configuration](.github/workflows/ci.yml) for details.

### Environments

- **Development**: Local development environment
- **Preview**: Automatically deployed for pull requests
- **Production**: Deployed from the main branch

## Community

- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Issue Tracker](https://github.com/yourusername/cco-vibe/issues)
- [Discussions](https://github.com/yourusername/cco-vibe/discussions)

## License

CCO-VIBE is licensed under the GNU Affero General Public License version 3 (AGPLv3) with additional terms restricting commercial use. This means you can:

✅ Use the software for non-commercial purposes
✅ Modify the software
✅ Distribute the software
✅ Create derivative works

❌ Use for commercial purposes without permission
❌ Remove attribution requirements
❌ Modify the license terms

For more details, see:
- [LICENSE](LICENSE) - Full license text
- [LICENSE.md](LICENSE.md) - Detailed explanation and FAQs
- [NOTICE](NOTICE) - Third-party attributions

### Commercial Licensing

For commercial use inquiries, please contact:
- Email: [Your Email]
- Website: [Your Website]

## Acknowledgments

- [React](https://reactjs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Morpheus Network](https://mor.org)
- [All Contributors](CONTRIBUTORS.md)
