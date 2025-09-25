# Contributing to Storyloomr

Thank you for your interest in contributing to Storyloomr! This document provides guidelines and information for contributors.

## 🚀 Getting Started

### Prerequisites

-   Node.js 18+ (for frontend/tooling)
-   Python 3.9+ (for backend services)
-   Docker and Docker Compose
-   Git

### Development Setup

1. **Fork and Clone**:

    ```bash
    git clone https://github.com/storyloomr/[repository-name].git
    cd [repository-name]
    ```

2. **Install Dependencies**:

    ```bash
    # Frontend
    npm install

    # Backend (Python)
    pip install -r requirements.txt

    # Mobile (iOS)
    cd ios && pod install
    ```

3. **Run Tests**:
    ```bash
    npm test           # Frontend
    pytest             # Backend
    npm run test:ios   # iOS
    ```

## 🏷️ Issue and PR Guidelines

### Creating Issues

-   Use our issue templates for consistency
-   Apply appropriate labels (`type:`, `area:`, `priority:`)
-   Provide clear reproduction steps for bugs
-   Include mockups/wireframes for features

### Pull Requests

-   **Link to Issues**: All PRs must reference an issue (`Fixes #123`)
-   **Branch Naming**: Use format `type/short-description`
    -   `feat/user-authentication`
    -   `fix/media-upload-error`
    -   `chore/update-dependencies`
-   **Commit Messages**: Follow [Conventional Commits](https://conventionalcommits.org/)
    -   `feat(auth): add OAuth2 integration`
    -   `fix(media): resolve upload timeout issue`
    -   `docs(api): update authentication examples`

### Code Standards

-   **Frontend**: ESLint + Prettier configuration
-   **Backend**: Black + flake8 for Python
-   **Mobile**: SwiftLint for iOS, ktlint for Android
-   **Documentation**: All public APIs must be documented

## 🔄 Development Workflow

1. **Pick an Issue**: Choose from `status: ready` labeled issues
2. **Create Branch**: Branch from `main` using naming convention
3. **Develop**: Write code following style guidelines
4. **Test**: Ensure all tests pass and add new tests
5. **Document**: Update documentation if needed
6. **PR**: Create PR with template and link issue
7. **Review**: Address feedback from maintainers
8. **Merge**: Maintainer will merge after approval

## 🧪 Testing Guidelines

### Test Requirements

-   **Unit Tests**: Required for all new features
-   **Integration Tests**: Required for API changes
-   **E2E Tests**: Required for critical user flows
-   **Manual Testing**: Document test scenarios

### Test Coverage

-   Maintain minimum 80% code coverage
-   Critical paths require 95%+ coverage
-   Include edge cases and error scenarios

## 📋 Component Guidelines

### Frontend (React/TypeScript)

-   Use functional components with hooks
-   Implement responsive design (mobile-first)
-   Follow accessibility guidelines (WCAG 2.1)
-   Use design system components

### Backend (Python/FastAPI)

-   Follow REST API conventions
-   Implement proper error handling
-   Add request/response validation
-   Include comprehensive logging

### Mobile (React Native)

-   Support iOS 14+ and Android API 24+
-   Optimize for performance and battery life
-   Handle offline scenarios gracefully
-   Follow platform-specific design guidelines

## 🛡️ Security Guidelines

-   Never commit secrets or credentials
-   Validate all user inputs
-   Implement proper authentication checks
-   Follow OWASP security practices
-   Report security issues privately

## 📝 Documentation

### Required Documentation

-   **README**: Setup and usage instructions
-   **API Docs**: OpenAPI/Swagger specifications
-   **Architecture**: High-level design decisions
-   **Changelog**: Notable changes and migrations

### Writing Guidelines

-   Clear, concise language
-   Include code examples
-   Provide troubleshooting tips
-   Keep documentation up-to-date

## 👥 Community Guidelines

### Code of Conduct

We follow the [Contributor Covenant](CODE_OF_CONDUCT.md). Please:

-   Be respectful and inclusive
-   Welcome newcomers and help them succeed
-   Focus on constructive feedback
-   Respect different viewpoints and experiences

### Communication Channels

-   **GitHub Issues**: Bug reports and feature requests
-   **GitHub Discussions**: General questions and ideas
-   **Slack**: Real-time development chat (invite only)

## 🏆 Recognition

We appreciate all contributions! Contributors are recognized through:

-   **Contributor Graph**: GitHub contribution tracking
-   **Release Notes**: Credits for significant contributions
-   **Swag**: Storyloomr merchandise for active contributors

## 📞 Getting Help

-   **Documentation**: Check README and docs/ folder
-   **Search Issues**: Someone may have asked before
-   **Create Issue**: Use appropriate template
-   **Discussions**: For open-ended questions

## 🔧 Development Environment

### Recommended Tools

-   **IDE**: VS Code with extensions
-   **API Testing**: Postman or Insomnia
-   **Database**: pgAdmin for PostgreSQL
-   **Monitoring**: Local observability stack

### Environment Variables

Copy `.env.example` to `.env` and configure:

```bash
# Database
DATABASE_URL=postgresql://user:pass@localhost/storyloomr

# Authentication
JWT_SECRET=your-secret-key
OAUTH_CLIENT_ID=your-oauth-id

# External Services
AWS_ACCESS_KEY_ID=your-aws-key
REDIS_URL=redis://localhost:6379
```

## 📈 Performance Guidelines

-   **Frontend**: Lazy loading, code splitting, image optimization
-   **Backend**: Database indexing, caching, async processing
-   **Mobile**: Memory management, network efficiency
-   **Infrastructure**: Auto-scaling, load balancing

## 🔄 Release Process

1. **Development**: Feature branches → `main` via PR
2. **Staging**: Automated deployment to staging environment
3. **Testing**: QA validation and performance testing
4. **Production**: Tagged releases with semantic versioning
5. **Monitoring**: Post-deployment health checks

Thank you for contributing to Storyloomr! 🙏
