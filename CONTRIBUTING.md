# Contributing to Your Email Validator

Thank you for your interest in contributing to Your Email Validator! This document provides guidelines and instructions for contributing to the project. We welcome all contributions that help improve the service.

## Code of Conduct

By participating in this project, you agree to abide by our Code of Conduct. We expect all contributors to:
- Be respectful and inclusive
- Exercise consideration and empathy in communications
- Focus on what is best for the community
- Show courtesy and respect towards other community members

## How to Contribute

### Reporting Bugs

1. Check the [GitHub Issues](https://github.com/youremailvalidator/docs/issues) to ensure the bug hasn't already been reported
2. If not found, create a new issue with:
   - A clear, descriptive title
   - Detailed steps to reproduce the bug
   - Expected vs actual behavior
   - Screenshots if applicable
   - Your environment details (OS, browser, etc.)

### Suggesting Enhancements

1. Review existing issues to avoid duplicates
2. Create a new issue that:
   - Clearly describes the enhancement
   - Explains why this would be useful
   - Outlines possible implementation approaches
   - Includes any relevant examples or mockups

### Pull Requests

1. Fork the repository
2. Create a new branch from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make your changes following our coding standards
4. Write clear, concise commit messages:
   ```bash
   git commit -m "Add: brief description of changes"
   ```
5. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
6. Open a Pull Request (PR) with:
   - A clear title and description
   - References to any related issues
   - Documentation updates if needed

## Development Setup

1. Clone your fork:
   ```bash
   git clone https://github.com/yourusername/youremailvalidator.git
   cd youremailvalidator
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your development environment:
   ```bash
   cp .env.example .env
   # Edit .env with your settings
   ```

## Coding Standards

- Follow PEP 8 style guide for Python code
- Write docstrings for all functions and classes
- Include type hints where appropriate
- Add unit tests for new features
- Ensure all tests pass before submitting PRs
- Keep code modular and maintainable

## Testing

1. Run the test suite:
   ```bash
   pytest
   ```

2. Ensure test coverage remains high:
   ```bash
   pytest --cov=youremailvalidator
   ```

## Documentation

- Update documentation for any changed functionality
- Use clear, concise language
- Include code examples where helpful
- Follow markdown best practices
- Test documentation changes locally

## Review Process

1. All PRs require review from at least one maintainer
2. Address any feedback promptly
3. Keep PRs focused and reasonable in size
4. Be patient and respectful during the review process

## Community

- Join our community discussions
- Help answer questions from other contributors
- Share your experiences and learnings
- Participate in code reviews
- Support fellow contributors

## License

By contributing to Your Email Validator, you agree that your contributions will be licensed under the same terms as the main project.

## Questions?

If you have any questions or need clarification:
- Check our [FAQ](https://youremailvalidator.com/#faq)
- Email us at fathin@youremailvalidator.com
- Open a discussion on GitHub

Thank you for contributing to Your Email Validator! Your efforts help make email validation better for everyone.
