# Whispr Backend - Modern Real-time Messaging API

🚀 **Whispr Backend** is a powerful backend API for the Whispr real-time messaging application. Built with NestJS, TypeScript, and PostgreSQL, it provides authentication, user management, multi-language post management, and AWS S3 integration.

Connect users through secure and reliable RESTful APIs with WebSocket support, JWT authentication, and CQRS patterns.

## ✨ Key Features

Whispr Backend comes equipped with powerful features and modern development tools:

### 🔐 Authentication & Authorization
- **JWT Authentication** - Stateless authentication using JSON Web Tokens
- **Role-based Access Control (RBAC)** - Role-based permissions (USER, ADMIN)
- **Password Hashing** - Secure password encryption with bcrypt
- **Session Management** - Secure session handling

### 👥 User Management
- **User Registration/Login** - User registration and login
- **Profile Management** - Personal information management
- **Avatar Upload** - Avatar uploads with AWS S3
- **User Settings** - Personal user preferences

### 📝 Post Management with CQRS
- **CQRS Pattern** - Separated read/write operations for optimal performance
- **Multi-language Support** - Multi-language support with translations
- **Post CRUD Operations** - Create, read, update, delete posts
- **User-Post Relationships** - Post relationships with users

### 🛠️ Technology & Development Tools
- **🏗️ NestJS 11+** - Progressive Node.js framework with modular architecture
- **💎 TypeScript 5.8+** - Optimal type safety with strict mode
- **🗄️ PostgreSQL + TypeORM** - Powerful ORM with transaction support
- **⚡ Vite** - Fast build tool for development
- **🧪 Jest** - Testing framework with coverage reports
- **📚 Swagger/OpenAPI** - Auto-generated API documentation

### 🌐 Internationalization (i18n)
- **Multi-language API** - English and Russian support
- **Dynamic Translations** - Dynamic translation based on headers/requests
- **Translation Interpolation** - Variable interpolation in messages

### ☁️ Cloud Integration
- **AWS S3** - Secure and scalable file storage
- **File Upload** - Upload processing with validation
- **Cloud Storage** - Media file management

### 🛡️ Security & Performance
- **Rate Limiting** - Request throttling with configurable limits
- **CORS Configuration** - Secure cross-origin request handling
- **Helmet Security** - Security headers protection
- **Input Validation** - Comprehensive DTO validation
- **SQL Injection Prevention** - Query parameterization

### 🔧 Developer Experience
- **Hot Reload** - Development with instant feedback
- **Docker Support** - Complete containerization
- **Multi-runtime** - Node.js, Bun, and Deno support
- **Code Generation** - CLI tools for scaffolding
- **Linting & Formatting** - ESLint + Prettier + Biome

## 🚀 Quick Start

Get Whispr Backend running in your local environment with these simple steps:

### System Requirements

- **Node.js** 22+ (LTS version recommended)
- **Yarn** 1.22.22+ (package manager)
- **PostgreSQL** 12+ (database)
- **Git** (version control)

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/your-username/whispr-backend.git
cd whispr-backend
```

2. **Install dependencies:**
```bash
yarn install
```

3. **Configure environment variables:**
```bash
cp .env.example .env
```

Edit `.env` with your configuration:
```env
# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=postgres
DB_DATABASE=whispr_db

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key-here
JWT_EXPIRATION_TIME=3600

# Application
PORT=3001
NODE_ENV=development

# CORS
CORS_ORIGINS=http://localhost:3000

# AWS S3 (optional)
AWS_S3_ACCESS_KEY_ID=your-access-key
AWS_S3_SECRET_ACCESS_KEY=your-secret-key
AWS_S3_REGION=us-east-1
AWS_S3_BUCKET_NAME=whispr-bucket

# NATS (optional - for microservices)
NATS_ENABLED=false
NATS_HOST=localhost
NATS_PORT=4222
```

4. **Start database with Docker:**
```bash
docker-compose up -d postgres pgadmin
```

5. **Run database migrations:**
```bash
yarn migration:run
```

6. **Start development server:**
```bash
yarn start:dev
```

7. **Access the application:**
- **API**: http://localhost:3001
- **API Documentation**: http://localhost:3001/documentation
- **PgAdmin**: http://localhost:8080

### 🐳 Docker Setup (Alternative)

```bash
# Build and run with Docker
docker-compose up --build
```

## 📁 Project Structure

```
whispr-backend/
├── src/
│   ├── common/                 # Shared components and utilities
│   │   ├── dto/               # Common Data Transfer Objects
│   │   └── abstract.entity.ts # Base entity with common fields
│   ├── constants/             # Application-wide constants
│   ├── database/              # Database configuration and migrations
│   │   └── migrations/        # TypeORM migration files
│   ├── decorators/            # Custom decorators
│   ├── entity-subscribers/    # TypeORM entity subscribers
│   ├── exceptions/            # Custom exception classes
│   ├── filters/               # Exception filters
│   ├── guards/                # Authentication and authorization guards
│   ├── i18n/                  # Internationalization files
│   │   ├── en_US/            # English translations
│   │   └── ru_RU/            # Russian translations
│   ├── interceptors/          # Request/Response interceptors
│   ├── interfaces/            # TypeScript interfaces
│   ├── modules/               # Feature modules
│   │   ├── auth/             # Authentication module
│   │   ├── user/             # User management module
│   │   ├── post/             # Post management with CQRS
│   │   └── health-checker/   # Health check module
│   ├── providers/             # Custom providers
│   ├── shared/                # Shared services
│   │   └── services/         # Global services
│   ├── validators/            # Custom validators
│   ├── app.module.ts         # Root application module
│   ├── main.ts               # Application entry point
│   └── setup-swagger.ts      # Swagger configuration
├── test/                      # E2E tests
├── docs/                      # Documentation
└── docker-compose.yml         # Docker development setup
```

## 🔧 Available Scripts

### Development
```bash
# Development server with Vite
yarn start:dev

# Development server with NestJS CLI
yarn nest:start:dev

# Development with debugger
yarn nest:start:debug

# Watch mode
yarn watch:dev
```

### Production
```bash
# Build for production
yarn build:prod

# Start production server
yarn start:prod
```

### Testing
```bash
# Run unit tests
yarn test

# Tests with watch mode
yarn test:watch

# E2E tests
yarn test:e2e

# Test coverage
yarn test:cov

# Debug tests
yarn test:debug
```

### Database Operations
```bash
# Generate new migration
yarn migration:generate src/database/migrations/migration_name

# Create empty migration
yarn migration:create src/database/migrations/migration_name

# Run migrations
yarn migration:run

# Show migration status
yarn migration:show

# Revert last migration
yarn migration:revert

# Drop database schema
yarn schema:drop
```

### Code Quality
```bash
# Run ESLint
yarn lint

# Fix ESLint errors
yarn lint:fix

# Update dependencies
yarn taze
```

## 🌍 Multi-runtime Support

The backend supports multiple JavaScript runtimes for maximum flexibility:

### Node.js (Default)
Traditional runtime with full ecosystem support.

### Bun 🧅
High-performance runtime with built-in bundler.
```bash
bun start:dev:bun    # Development server
bun watch:bun        # Watch mode
bun test            # Run tests
bun build:bun       # Build
```

### Deno 🦕
Secure runtime for JavaScript and TypeScript.
```bash
deno task start     # Development server
deno task watch     # Watch mode
deno task test      # Run tests
deno task buildr    # Build
```

## 🔐 API Endpoints

### Authentication
- `POST /auth/login` - User login
- `POST /auth/register` - User registration
- `GET /auth/me` - Current user info

### Users
- `GET /users` - Get users list
- `GET /users/:id` - Get user details
- `PATCH /users/:id` - Update user
- `DELETE /users/:id` - Delete user

### Posts
- `GET /posts` - Get posts list
- `POST /posts` - Create new post
- `GET /posts/:id` - Get post details
- `PATCH /posts/:id` - Update post
- `DELETE /posts/:id` - Delete post

### Health Check
- `GET /health` - Health check endpoint

## 🔧 Environment Configuration

### Main Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `NODE_ENV` | Environment mode | `development` |
| `PORT` | Application port | `3001` |
| `DB_HOST` | Database host | `localhost` |
| `DB_PORT` | Database port | `5432` |
| `DB_USERNAME` | Database username | `postgres` |
| `DB_PASSWORD` | Database password | Required |
| `DB_DATABASE` | Database name | `whispr_db` |
| `JWT_SECRET` | JWT signing secret | Required |
| `JWT_EXPIRATION_TIME` | JWT expiration (seconds) | `3600` |
| `CORS_ORIGINS` | Allowed CORS origins | `http://localhost:3000` |
| `AWS_S3_ACCESS_KEY_ID` | AWS S3 access key | Optional |
| `AWS_S3_SECRET_ACCESS_KEY` | AWS S3 secret key | Optional |
| `AWS_S3_REGION` | AWS S3 region | `us-east-1` |
| `AWS_S3_BUCKET_NAME` | AWS S3 bucket name | Optional |

## 🤝 Contributing

We welcome contributions to Whispr Backend! Whether you're fixing bugs, adding features, or improving documentation, your help is greatly appreciated.

### How to Contribute

1. **Fork the repository** and create your feature branch:
```bash
git checkout -b feature/amazing-feature
```

2. **Follow our coding standards:**
- Use TypeScript for type safety
- Follow established patterns
- Write meaningful commit messages
- Add tests for new features

3. **Test your changes:**
```bash
yarn test
yarn lint
yarn build:prod
```

4. **Submit a pull request** with a clear description of your changes.

### Development Guidelines

- 📖 Read our [Development Rules](./RULES.md) for detailed guidelines
- 🎨 Follow established design patterns
- 🔧 Keep the codebase clean and well-documented
- 🧪 Test your changes thoroughly
- 📱 Ensure consistent API responses

## 📄 License

Whispr Backend is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more information.

## 🙏 Acknowledgments

- Built with [NestJS](https://nestjs.com/) - Progressive Node.js framework
- Database with [TypeORM](https://typeorm.io/) - Object-relational mapping
- Authentication with [Passport](http://www.passportjs.org/) - Authentication middleware
- Documentation with [Swagger](https://swagger.io/) - API documentation
- Cloud storage with [AWS S3](https://aws.amazon.com/s3/) - Scalable storage solution

---

**Whispr Backend** - Powerful API for real-time messaging. 🌟
