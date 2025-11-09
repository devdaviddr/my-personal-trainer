
# My Personal Trainer 💪

> An AI-powered Progressive Web App for personalized fitness training and workout planning

![App Screenshot](docs/app.png)

## 🚀 Technology Stack

| **Frontend** | **Backend** | **Database** | **Authentication** |
|-------------|------------|--------------|-------------------|
| ⚛️ React (latest) | 🔥 HonoJS | �️ Cloudflare D1 | 🔐 Auth0 |
| 📘 TypeScript | ☁️ Cloudflare Workers | | |
| ⚡ Vite PWA | | | |

## 🌟 Features

✅ **PWA Capabilities**
- 📱 Installable on any device
- 🔄 Offline support
- 🔔 Push notifications
- 📳 Add to Home Screen

✅ **Smart Training**
- 🤖 AI-powered workout recommendations
- 📊 Progress tracking & analytics
- 📋 Personalized workout plans
- 📱 Responsive design across all devices

## 🛠️ Getting Started

### Prerequisites
```bash
Node.js v18+
npm or yarn
Cloudflare account
Auth0 account
```

### 📦 Installation
```bash
git clone https://github.com/devdaviddr/my-personal-trainer.git
cd my-personal-trainer
npm install
```

### 🚀 Local Development
```bash
# Start development server
npm run dev

# Open browser at
http://localhost:5173
```

### 🏗️ Local Production Build
```bash
npm run build
npm run preview
```

### 🐳 Cloudflare Development
```bash
# Install Wrangler CLI
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Start local development with Cloudflare Workers
npm run dev:cf

# Access at
http://localhost:8787
```

## 📱 PWA Features

| Feature | Description |
|---------|-------------|
| 🔧 **Service Worker** | Intelligent caching for offline functionality |
| 📋 **Web Manifest** | App metadata for native-like installation |
| 🔒 **HTTPS Ready** | Secure connection for full PWA capabilities |

## 🌐 Deployment

### ☁️ Cloudflare Pages + D1 Database

#### Setup D1 Database
```bash
# Create D1 database
wrangler d1 create personal-trainer-db

# Run migrations
wrangler d1 migrations apply personal-trainer-db --local
wrangler d1 migrations apply personal-trainer-db
```

#### Environment Variables
Create a `.env` file:
```bash
# Auth0 Configuration
AUTH0_DOMAIN=your-domain.auth0.com
AUTH0_CLIENT_ID=your-client-id
AUTH0_CLIENT_SECRET=your-client-secret

# Cloudflare D1
DATABASE_ID=your-d1-database-id

# Application
NODE_ENV=production
```

#### Deploy to Cloudflare Pages
```bash
# Build for production
npm run build

# Deploy with Wrangler
wrangler pages deploy dist

# Or connect GitHub repository for automatic deployments
```

#### Configure wrangler.toml
```toml
name = "my-personal-trainer"
compatibility_date = "2024-11-10"

[[d1_databases]]
binding = "DB"
database_name = "personal-trainer-db"
database_id = "your-database-id"

[vars]
AUTH0_DOMAIN = "your-domain.auth0.com"
AUTH0_CLIENT_ID = "your-client-id"
```

### 🔐 Auth0 Setup

#### Configure Auth0 Application
1. Create new **Single Page Application** in Auth0
2. Set **Allowed Callback URLs**: `https://your-app.pages.dev/callback`
3. Set **Allowed Logout URLs**: `https://your-app.pages.dev`
4. Set **Allowed Web Origins**: `https://your-app.pages.dev`

#### Add Environment Variables to Cloudflare Pages
```bash
# In Cloudflare Pages dashboard, add:
AUTH0_DOMAIN=your-domain.auth0.com
AUTH0_CLIENT_ID=your-client-id
AUTH0_CLIENT_SECRET=your-client-secret
DATABASE_ID=your-d1-database-id
```

### 🔧 Local Testing
For local development and testing:
```bash
npm run dev       # Development server
npm run dev:cf    # Cloudflare Workers development
npm run build     # Production build
npm run preview   # Preview production build
```

## 🤝 Contributing

We welcome contributions! Here's how:

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit your changes (`git commit -m 'Add amazing feature'`)
4. 📤 Push to branch (`git push origin feature/amazing-feature`)
5. 🔃 Open a Pull Request

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.
