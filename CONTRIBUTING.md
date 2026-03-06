# Contributing to ext-background-jobs

Thank you for your interest in contributing. This project follows a simple workflow for contributions.

## REPORTING ISSUES

If you encounter a bug or have a feature request:

1. Search existing issues to avoid duplicates
2. For bugs: Include steps to reproduce, expected vs actual behavior
3. For features: Describe the use case and proposed implementation
4. Use the appropriate issue template

## DEVELOPMENT WORKFLOW

1. Fork the repository
2. Clone your fork locally
3. Create a feature branch from main
4. Make your changes
5. Ensure the build passes
6. Push to your fork and submit a pull request

```bash
git clone https://github.com/theluckystrike/ext-background-jobs.git
cd ext-background-jobs
git checkout -b feature/your-feature
npm install
npm run build
git add -A
git commit -m "Describe your changes"
git push origin feature/your-feature
```

## CODE STYLE

- Use TypeScript for all new code
- Follow the existing code formatting
- Keep functions small and focused
- Add JSDoc comments for public APIs
- Ensure type safety

## TESTING

Run the build and test commands before submitting:

```bash
npm run build
npm test
```

## LICENSE

By contributing, you agree that your contributions will be licensed under the MIT License.
