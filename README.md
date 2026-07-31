# Saga Academy App

[![CI/CD Pipeline](https://github.com/saga-academy/saga-academy-app/actions/workflows/ci-cd.yml/badge.svg)](https://github.com/saga-academy/saga-academy-app/actions/workflows/ci-cd.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)

Production environment for Saga Science Academy's all-in-one smart app. This monorepo contains the Flutter mobile app, Neon PostgreSQL backend, and web dashboard for student/staff access.

## 📱 Features

- **Mobile App** (Flutter): iOS & Android application for students and staff
- **Backend** (Neon PostgreSQL + Express): RESTful API with PostgreSQL database
- **Web Dashboard** (Next.js): Admin panel for academy management
- **Real-time Data**: PostgreSQL with connection pooling for high performance
- **Authentication**: JWT-based secure user authentication
- **Push Notifications**: Integrated notification system
- **Payment Integration**: Stripe payment processing
- **Analytics**: Comprehensive usage analytics and monitoring

## 🏗️ Project Structure

```
saga-academy-app/
├── mobile-app/              # Flutter mobile application
│   ├── lib/
│   │   ├── screens/        # UI screens
│   │   ├── widgets/        # Reusable widgets
│   │   ├── services/       # API services
│   │   ├── models/         # Data models
│   │   └── main.dart       # App entry point
│   ├── test/               # Unit & widget tests
│   ├── android/            # Android-specific files
│   ├── ios/                # iOS-specific files
│   └── pubspec.yaml        # Flutter dependencies
│
├── backend/                 # Neon PostgreSQL + Express API
│   ├── src/
│   │   ├── controllers/    # Route controllers
│   │   ├── middleware/     # Express middleware
│   │   ├── models/         # Data models
│   │   ├── routes/         # API routes
│   │   ├── services/       # Business logic
│   │   └── database/       # Database connection & migrations
│   ├── database/           # SQL migration files
│   ├── config/             # Configuration files
│   ├── test/               # Unit tests
│   ├── tsconfig.json       # TypeScript configuration
│   └── package.json        # Node.js dependencies
│
├── web-dashboard/           # Next.js admin dashboard
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Next.js pages
│   │   ├── services/       # API services
│   │   └── styles/         # CSS/Tailwind styles
│   ├── public/             # Static assets
│   ├── test/               # Component tests
│   └── package.json        # Node.js dependencies
│
├── docs/                    # Documentation
├── scripts/                 # Build & deployment scripts
├── .github/workflows/       # CI/CD pipelines
├── docker-compose.yml       # Docker orchestration
├── .env.example             # Environment variables template
└── README.md                # This file
```

## 🚀 Quick Start

### Prerequisites

- [Flutter](https://flutter.dev/docs/get-started/install) (v3.16+)
- [Node.js](https://nodejs.org/) (v18+)
- [Neon Database](https://neon.tech/) account (for production)
- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/) (optional, for containerized deployment)

### 1. Clone the Repository

```bash
git clone https://github.com/saga-academy/saga-academy-app.git
cd saga-academy-app
```

### 2. Environment Setup

Copy the example environment file and configure your credentials:

```bash
cp .env.example .env
```

Edit `.env` with your actual Neon Database URL, Stripe, and other service credentials.

**Neon Database Setup:**
1. Create a free account at [neon.tech](https://neon.tech)
2. Create a new project
3. Copy the connection string to `DATABASE_URL` in `.env`

### 3. Mobile App Setup

```bash
cd mobile-app
flutter pub get
flutter run
```

**Note:** Update the API base URL in the app configuration to point to your backend.

### 4. Backend Setup

```bash
cd backend
npm install
npm run dev  # Start development server with hot reload
```

Run database migrations:

```bash
npm run db:migrate
```

### 5. Web Dashboard Setup

```bash
cd web-dashboard
npm install
npm run dev  # Start development server
```

Build for production:

```bash
npm run build
```

## 🐳 Docker Deployment

For containerized deployment with local PostgreSQL:

```bash
docker-compose up -d
```

This starts:
- PostgreSQL database (local development)
- Backend API service
- Web Dashboard
- Database migration job

**Production:** Use your Neon Database connection string instead of the local PostgreSQL.

## 🧪 Testing

### Run All Tests

```bash
# Mobile App
cd mobile-app && flutter test

# Backend
cd backend && npm test

# Web Dashboard
cd web-dashboard && npm test
```

### Test Coverage

```bash
# Mobile App
flutter test --coverage

# Backend
npm run test:coverage

# Web Dashboard
npm run test:coverage
```

## 📦 Deployment

### Mobile App

**Android:**
```bash
cd mobile-app
flutter build apk --release
# or for App Bundle
flutter build appbundle --release
```

**iOS:**
```bash
cd mobile-app
flutter build ios --release
```

### Backend

Deploy to your preferred platform (Heroku, Railway, Render, etc.):

```bash
cd backend
npm run build
# Set DATABASE_URL environment variable on your hosting platform
```

### Web Dashboard

```bash
cd web-dashboard
npm run build
# Deploy to Vercel, Netlify, or your preferred hosting
```

## 🔒 Security

- Never commit `.env` files or sensitive credentials
- Use parameterized queries to prevent SQL injection
- Implement proper authentication and authorization with JWT
- Regular security audits with `npm audit` and `dart pub outdated`
- Enable HTTPS in production
- Use environment variables for all secrets
- Implement rate limiting for API endpoints

## 📄 Documentation

- [Architecture Overview](docs/architecture.md)
- [API Documentation](docs/api.md)
- [Deployment Guide](docs/deployment.md)
- [Database Schema](docs/database-schema.md)
- [Contributing Guidelines](CONTRIBUTING.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details on:
- Development setup
- Coding standards
- Pull request process
- Testing requirements

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Team

- **Development Team**: Saga Science Academy
- **Contact**: tech@saga-academy.com

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- Neon Database for serverless PostgreSQL
- Next.js team for the web framework
- All contributors and supporters

---

**Built with ❤️ for Education**
