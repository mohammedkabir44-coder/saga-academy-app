# Contributing to Saga Academy App

Thank you for considering contributing to the Saga Science Academy app! This document provides guidelines and instructions for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing](#testing)
- [Commit Messages](#commit-messages)

## Code of Conduct

Please be respectful and inclusive in all interactions. We are committed to providing a welcoming environment for all contributors.

## Getting Started

1. Fork the repository
2. Clone your fork: `git clone https://github.com/your-username/saga-academy-app.git`
3. Create a branch: `git checkout -b feature/your-feature-name`
4. Make your changes and commit them
5. Push to your fork and submit a Pull Request

## Development Setup

### Prerequisites

- **Flutter**: Version 3.16 or higher
- **Node.js**: Version 18 or higher
- **Neon Database**: Account at neon.tech (for production)
- **PostgreSQL**: Version 15+ (for local development, optional with Docker)
- **Git**: Latest version

### Mobile App Setup

```bash
cd mobile-app
flutter pub get
flutter run
```

### Backend Setup

```bash
cd backend
npm install
npm run dev  # Start development server with hot reload
```

Run database migrations:

```bash
npm run db:migrate
```

### Web Dashboard Setup

```bash
cd web-dashboard
npm install
npm run dev
```

## Pull Request Process

1. Ensure your code passes all tests and linting
2. Update documentation if needed
3. Add tests for new functionality
4. Ensure CI/CD pipeline passes
5. Request review from maintainers
6. Address review feedback promptly

## Coding Standards

### Flutter/Dart

- Follow [Effective Dart](https://dart.dev/guides/language/effective-dart) guidelines
- Use `flutter analyze` before committing
- Format code with `dart format .`
- Keep widgets small and focused
- Use const constructors where possible

### Backend (TypeScript/Node.js)

- Follow TypeScript best practices
- Use ESLint and Prettier configurations provided
- Write JSDoc comments for public functions
- Use async/await for asynchronous code
- Implement proper error handling

### Web Dashboard (Next.js/React)

- Follow React best practices
- Use functional components with hooks
- Implement proper TypeScript types
- Use Tailwind CSS for styling
- Optimize for performance (lazy loading, memoization)

## Testing

### Mobile App Tests

```bash
cd mobile-app
flutter test                    # Run unit tests
flutter test --coverage         # Run with coverage
flutter drive                   # Run integration tests
```

### Backend Tests

```bash
cd backend
npm test                        # Run tests
npm run test:coverage           # Run with coverage
npm run test:watch              # Watch mode
```

### Web Dashboard Tests

```bash
cd web-dashboard
npm test                        # Run tests
npm run test:coverage           # Run with coverage
```

### Test Coverage Requirements

- Minimum 80% code coverage for new features
- Unit tests for all business logic
- Integration tests for critical paths
- E2E tests for key user flows

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
feat: add new login feature
fix: resolve authentication bug
docs: update README installation steps
style: format code according to guidelines
refactor: improve database query performance
test: add unit tests for user service
chore: update dependencies
```

### Commit Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

## Branch Naming Convention

- `feature/description` - New features
- `fix/description` - Bug fixes
- `hotfix/description` - Critical production fixes
- `docs/description` - Documentation updates
- `refactor/description` - Code refactoring

## Questions?

Feel free to open an issue for any questions or concerns. We're here to help!

---

Thank you for contributing to Saga Science Academy! 🎓
