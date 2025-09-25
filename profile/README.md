<div align="left">
    <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/storyloomr/storyloomr-assets/refs/heads/main/logo/brand/dark/full-brand.svg">
    <img alt="Storyloomr Logo" src="https://raw.githubusercontent.com/storyloomr/storyloomr-assets/refs/heads/main/logo/brand/light/full-brand.svg" width="300"    >
    </picture>
</div>

**Modern publishing made easy — customizable, robust content orchestration for teams and creators.**

Storyloomr is a composable, microservices-based open-source blogging and content platform designed with collaboration, scalability, and developer experience at its core. Built for the future of digital publishing, Storyloomr empowers content creators, developers, and organizations to build powerful, customizable content experiences.

---

## 🎯 Our Vision

We believe that modern publishing should be:

- **Accessible** to creators of all technical backgrounds
- **Scalable** from personal blogs to enterprise content operations
- **Collaborative** with seamless team workflows
- **Developer-friendly** with robust APIs and extensibility
- **Future-proof** with modern architecture and standards

## 🏗️ Architecture & Technology Stack

Storyloomr follows a microservices architecture that ensures scalability, maintainability, and flexibility:

| **Frontend**        | **Backend**    | **Infrastructure**   | **Development**      |
| ------------------- | -------------- | -------------------- | -------------------- |
| Next.js             | Python FastAPI | Docker & Kubernetes  | GitHub Actions CI/CD |
| Tailwind CSS        | PostgreSQL     | Nginx Load Balancing | Sentry Observability |
| Redux Toolkit Query | MongoDB        | Redis Caching        | ESLint & Prettier    |
| TypeScript          | Apache Kafka   | Microservices Mesh   | Automated Testing    |

### Mobile & Cross-Platform

- **Native iOS/Android** applications
- **Cross-platform** development with shared components
- **Progressive Web App** capabilities

---

## 📁 Repository Overview

Our codebase is organized into focused repositories, each serving a specific purpose in the Storyloomr ecosystem:

### 🎨 Frontend Applications

- **`storyloomr-fe-reader`** — Content consumption interface for end users
- **`storyloomr-fe-editor`** — Rich content creation and editing experience
- **`storyloomr-fe-admin`** — Administrative dashboard and site management

### 📱 Mobile Applications

- **`storyloomr-app-ios`** — Native iOS application
- **`storyloomr-app-android`** — Native Android application

### 🔧 Core Services

- **`storyloomr-svc-auth`** — Authentication and authorization service
- **`storyloomr-svc-content`** — Content management and storage
- **`storyloomr-svc-search`** — Full-text search and indexing
- **`storyloomr-svc-media`** — Media processing and CDN management
- **`storyloomr-svc-analytics`** — Usage analytics and insights
- **`storyloomr-svc-notify`** — Notification and messaging service

### 🏗️ Infrastructure & Platform

- **`storyloomr-infra-nginx`** — Load balancing and reverse proxy configuration
- **`storyloomr-infra-redis`** — Caching layer and session management
- **`storyloomr-infra-kafka`** — Event streaming and message queuing
- **`storyloomr-infra-platform`** — Core platform infrastructure as code
- **`storyloomr-api-gateway`** — API gateway and routing
- **`storyloomr-observability`** — Monitoring, logging, and observability stack

### 📚 Shared Libraries & Utilities

- **`storyloomr-lib-ui`** — Reusable UI components and design system
- **`storyloomr-lib-sdk`** — JavaScript/TypeScript SDK for developers
- **`storyloomr-schemas-event`** — Event schema definitions and validation
- **`storyloomr-flags`** — Feature flag management and A/B testing

### 🎨 Assets & Documentation

- **`storyloomr-assets`** — Brand assets, logos, and documentation images

---

## 🚀 Getting Started

### For Contributors

1. **Read our [Contributing Guide](./CONTRIBUTING.md)** to understand our development process
2. **Check our [Project Kanban](https://github.com/orgs/storyloomr/projects)** for current priorities
3. **Review the [Code of Conduct](./CODE_OF_CONDUCT.md)** for community guidelines
4. **Browse open issues** across repositories to find ways to contribute

### For Developers

1. **Explore our APIs** and microservices architecture
2. **Use our SDK** for integrating with Storyloomr
3. **Check out our [documentation](https://docs.storyloomr.com)** for detailed guides
4. **Join our [Discord community](https://discord.gg/storyloomr)** for support and discussions

### For Content Creators

1. **Visit [storyloomr.com](https://storyloomr.com)** to get started
2. **Read our [User Guide](https://docs.storyloomr.com/user-guide)** for best practices
3. **Explore templates** and customization options
4. **Connect with other creators** in our community

---

## 🤝 Contributing

We welcome contributions from the community! Our contribution process is designed to be transparent and collaborative:

### Automated Workflows

- **Organization-wide label management** ensures consistent issue categorization
- **Automated PR templates** guide contributors through the review process
- **CI/CD pipelines** automatically test and validate contributions
- **Sentry integration** monitors code quality and performance

### Development Process

1. **Fork** the relevant repository
2. **Create a feature branch** following our naming conventions
3. **Make your changes** with comprehensive tests
4. **Submit a pull request** using our automated templates
5. **Participate in code review** with the maintainer team

### Quality Standards

- **Accessibility first** — all features must meet WCAG 2.1 AA standards
- **Internationalization ready** — code should support i18n from day one
- **Comprehensive testing** — unit, integration, and end-to-end tests required
- **Documentation** — all public APIs and major features must be documented

---

## 🎨 Brand Assets & Visual Guidelines

All Storyloomr brand assets are centrally managed in the [`storyloomr-assets`](https://github.com/storyloomr/storyloomr-assets) repository to ensure consistency across all properties.

### Using Storyloomr Assets

To embed our logo in your project documentation:

```markdown
![Storyloomr Logo](https://raw.githubusercontent.com/storyloomr/storyloomr-assets/main/Brand-Logo.jpg)
```

For the full brand treatment:

```markdown
![Storyloomr Full Brand](https://raw.githubusercontent.com/storyloomr/storyloomr-assets/main/Full-Brand.jpg)
```

### Asset Versioning

- All assets are versioned and tagged for stability
- Use specific tags for production implementations: `main` for development, tagged releases for production
- Submit asset requests and updates via issues in the `storyloomr-assets` repository

---

## 🔧 Development Tools & Automation

### Observability & Monitoring

- **Sentry** for error tracking and performance monitoring
- **Structured logging** across all microservices
- **Health checks** and uptime monitoring
- **Performance metrics** and alerting

### Code Quality

- **ESLint** and **Prettier** for consistent code formatting
- **SonarQube** for code quality analysis
- **Automated security scanning** for vulnerabilities
- **Dependency management** and update automation

### Project Management

- **GitHub Projects** with Kanban boards for project tracking
- **Milestone-based planning** with clear deliverables
- **Automated issue labeling** and triage
- **Release management** with semantic versioning

---

## 🌐 Community & Support

### Communication Channels

- **GitHub Discussions** for community Q&A and feature requests
- **Discord Server** for real-time chat and support
- **Twitter [@storyloomr](https://twitter.com/storyloomr)** for updates and announcements
- **Blog** for technical deep-dives and platform updates

### Getting Help

- **Documentation**: [docs.storyloomr.com](https://docs.storyloomr.com)
- **Community Support**: [GitHub Discussions](https://github.com/storyloomr/.github/discussions)
- **Bug Reports**: Use issue templates in relevant repositories
- **Security Issues**: Follow our [Security Policy](./SECURITY.md)

### Contributing Guidelines

- All contributions must align with our [Code of Conduct](./CODE_OF_CONDUCT.md)
- Review our [Contributing Guide](./CONTRIBUTING.md) before submitting PRs
- Use our standardized [issue templates](.github/ISSUE_TEMPLATE/) for bug reports and features
- Follow our [pull request template](.github/pull_request_template.md) for submissions

---

## 📄 License & Legal

Storyloomr is open-source software licensed under the MIT License. See individual repository LICENSE files for specific terms and conditions.

### Code Ownership

- All repositories include [CODEOWNERS](./CODEOWNERS) files for maintainer assignment
- Contributions are governed by our [Contributor License Agreement](./CONTRIBUTING.md#contributor-license-agreement)
- Brand assets and trademarks are protected under separate terms

---

## 🙏 Acknowledgments

Storyloomr is built by a passionate community of developers, designers, content creators, and users who believe in the power of open, collaborative publishing platforms.

**Core Maintainers**: The Storyloomr Team  
**Contributors**: [View all contributors](https://github.com/storyloomr)  
**Sponsors**: See our [Funding page](./FUNDING.yml) to support the project

---

<div align="center">

**[📖 Documentation](https://docs.storyloomr.com) • [🌐 Website](https://storyloomr.com) • [💬 Community](https://discord.gg/storyloomr) • [🐦 Twitter](https://twitter.com/storyloomr)**

_Empowering creators, one story at a time._

</div>
