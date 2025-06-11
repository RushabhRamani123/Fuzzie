# Fuzzie - Automate Your Work With AI

Fuzzie is a powerful workflow automation platform that helps you connect your favorite tools and automate repetitive tasks. Built with modern web technologies, Fuzzie provides an intuitive visual interface for creating complex automation workflows.

![Fuzzie Platform](public/fuzzieLogo.png)

## 🚀 Features

- **Visual Workflow Builder**: Create automation workflows with an intuitive drag-and-drop interface
- **Multi-Platform Integrations**: Connect with Discord, Notion, Slack, Google Drive, and more
- **Real-time Collaboration**: Work together with your team on automation projects
- **AI-Powered Suggestions**: Get intelligent recommendations for workflow optimization
- **Secure OAuth Integration**: Safe and secure connections to your favorite platforms

## 🛠️ Tech Stack

- **Frontend**: Next.js 14 with App Router
- **Styling**: Tailwind CSS + shadcn/ui components
- **Database**: Prisma ORM
- **Authentication**: OAuth integrations
- **Package Manager**: Bun
- **Language**: TypeScript

## 📁 Project Structure

```
fuzzie-production/
├── .env                          # Environment variables (private)
├── .env.example                  # Environment variables template
├── .eslintrc.json               # ESLint configuration for code linting
├── .gitignore                   # Git ignore patterns
├── bun.lockb                    # Bun package manager lock file
├── components.json              # shadcn/ui components configuration
├── next-env.d.ts               # Next.js TypeScript declarations
├── next.config.mjs             # Next.js configuration
├── package.json                # Project dependencies and scripts
├── postcss.config.js           # PostCSS configuration for CSS processing
├── README.md                   # Project documentation and setup instructions
├── tailwind.config.ts          # Tailwind CSS configuration
├── tsconfig.json              # TypeScript configuration
│
├── .next/                     # Next.js build output (auto-generated)
├── prisma/                   # Database schema and migrations
│   └── schema.prisma         # Database schema definition
│
├── public/                   # Static assets served publicly
│   ├── 1.png - 10.png       # Numbered image assets
│   ├── discord.png          # Discord integration icon
│   ├── fuzzieLogo.png       # Application logo
│   ├── googleDrive.png      # Google Drive integration icon
│   ├── notion.png           # Notion integration icon
│   └── ...                  # Other static assets
│
└── src/                     # Source code directory
    ├── app/                 # Next.js App Router directory
    │   ├── (main)/         # Route group for main application
    │   │   └── (pages)/    # Nested route group for pages
    │   │       └── connections/  # Connections management feature
    │   │           ├── page.tsx           # Main connections page
    │   │           ├── _actions/          # Server actions
    │   │           │   ├── discord-connection.tsx   # Discord integration logic
    │   │           │   ├── notion-connection.tsx    # Notion integration logic
    │   │           │   ├── slack-connection.tsx     # Slack integration logic
    │   │           │   └── get-user.tsx             # User data fetching
    │   │           └── _components/       # Page-specific components
    │   │               └── connection-card.tsx      # Connection card UI
    │   │
    │   └── api/            # API routes
    │       └── auth/       # Authentication endpoints
    │           └── callback/  # OAuth callback handlers
    │               └── notion/
    │                   └── route.ts      # Notion OAuth callback
    │
    └── lib/                # Shared utilities and configurations
        ├── db.ts          # Database connection/client
        └── constant.ts    # Application constants including connection definitions
```

## 🔗 Supported Integrations

- **Discord**: Automate server management and notifications
- **Notion**: Sync databases and create automated workflows
- **Slack**: Send messages and manage team communications
- **Google Drive**: File management and document automation
- **And many more coming soon!**

## 🚦 Getting Started

### Prerequisites

- Node.js 18+ or Bun
- A database (PostgreSQL recommended)
- OAuth credentials for integrations you want to use
### Environment Variables

Copy the `.env.example` file and configure the following environment variables:

```bash
# Clerk Authentication
export NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
export NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
export NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard
export NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard
export NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
export CLERK_SECRET_KEY=your_clerk_secret_key

# Database Configuration
export DATABASE_URL=your_postgresql_database_url

# Application URLs
export NEXT_PUBLIC_URL=https://localhost:3000
export NEXT_PUBLIC_DOMAIN=localhost:3000
export NEXT_PUBLIC_SCHEME=https://

# Google Drive Integration
export NEXT_PUBLIC_GOOGLE_SCOPES=https://www.googleapis.com/auth/drive
export NEXT_PUBLIC_OAUTH2_ENDPOINT=https://accounts.google.com/o/oauth2/v2/auth
export GOOGLE_CLIENT_ID=your_google_client_id
export GOOGLE_CLIENT_SECRET=your_google_client_secret
export OAUTH2_REDIRECT_URI=https://electric-grizzly-7.clerk.accounts.dev/v1/oauth_callback

# Upload Care Configuration
export NEXT_PUBLIC_UPLOAD_CARE_CSS_SRC=https://cdn.jsdelivr.net/npm/@uploadcare/blocks@
export NEXT_PUBLIC_UPLOAD_CARE_SRC_PACKAGE=/web/lr-file-uploader-regular.min.css

# Discord Integration
export DISCORD_CLIENT_ID=your_discord_client_id
export DISCORD_CLIENT_SECRET=your_discord_client_secret
export DISCORD_TOKEN=your_discord_bot_token
export DISCORD_PUBLICK_KEY=your_discord_public_key
export NEXT_PUBLIC_DISCORD_REDIRECT=https://discord.com/oauth2/authorize?client_id=*CLIENTID*&response_type=code&redirect_uri=https%3A%2F%2Flocalhost%3A3000%2Fapi%2Fauth%2Fcallback%2Fdiscord&scope=identify+guilds+connections+guilds.members.read+email+webhook.incoming

# Notion Integration
export NOTION_API_SECRET=your_notion_api_secret
export NOTION_CLIENT_ID=your_notion_client_id
export NOTION_REDIRECT_URI=https://localhost:3000/api/auth/callback/notion
export NEXT_PUBLIC_NOTION_AUTH_URL=https://api.notion.com/v1/oauth/authorize?client_id=*CLIENTID*&response_type=code&owner=user&redirect_uri=https%3A%2F%2Flocalhost%3A3000%2Fapi%2Fauth%2Fcallback%2Fnotion

# Slack Integration
export SLACK_SIGNING_SECRET=your_slack_signing_secret
export SLACK_BOT_TOKEN=your_slack_bot_token
export SLACK_APP_TOKEN=your_slack_app_token
export SLACK_CLIENT_ID=your_slack_client_id
export SLACK_CLIENT_SECRET=your_slack_client_secret
export SLACK_REDIRECT_URI=https://localhost:3000/api/auth/callback/slack
export NEXT_PUBLIC_SLACK_REDIRECT=https://slack.com/oauth/v2/authorize?client_id=*CLIENTID*&scope=chat:write,channels:read,groups:read,mpim:read,im:read&user_scope=chat:write,channels:read,groups:read,mpim:read,im:read&redirect_uri=https%3A%2F%2Flocalhost%3A3000%2Fapi%2Fauth%2Fcallback%2Fslack

# Additional Services
export NGROK_URI=your_ngrok_tunnel_url
export CRON_JOB_KEY=your_cron_job_secret_key
export STRIPE_SECRET=your_stripe_secret_key
```

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd fuzzie-production
   ```

2. **Install dependencies**
   ```bash
   bun install
   # or
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   Edit the `.env` file and fill in your specific values for the environment variables listed above.

4. **Set up the database**
   ```bash
   bun prisma generate
   bun prisma db push
   ```

5. **Run the development server**
   ```bash
   bun dev
   # or
   npm run dev
   ```

6. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000) to see Fuzzie in action!

## 🔧 Development

### Available Scripts

- `bun dev` - Start development server
- `bun build` - Build for production
- `bun start` - Start production server
- `bun lint` - Run ESLint
- `bun prisma studio` - Open Prisma Studio

### Code Style

This project uses:
- ESLint for code linting
- Prettier for code formatting
- TypeScript for type safety
- Tailwind CSS for styling

## 🤝 Contributing

We welcome contributions! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License.

## 🔒 Security

If you discover a security vulnerability, please send an e-mail to security@fuzzie.com. All security vulnerabilities will be promptly addressed.

---

**Built with ❤️ by the Fuzzie Team**
