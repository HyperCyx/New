# New One Receiver - Web Application

A complete web application replicating the "New One Receiver" mobile app functionality with modern React frontend and Node.js backend.

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- Docker and Docker Compose
- Git

### Setup Instructions

1. **Create Repository**
```bash
# Create repository on GitHub first, then:
git clone https://github.com/new-one-receiver/main-app.git
cd main-app
```

2. **Environment Setup**
```bash
cp .env.example .env
# Edit .env with your configuration
```

3. **Start with Docker (Recommended)**
```bash
docker-compose up --build
```

4. **Manual Setup (Alternative)**
```bash
# Backend setup
cd backend
npm install
npx prisma generate
npx prisma db push
npm run dev

# Frontend setup (new terminal)
cd frontend
npm install
npm run dev
```

### Access the Application
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000
- **Database**: PostgreSQL on port 5432

## 📱 Features

### 🎯 Dashboard
- User profile display ("Hyper Red", ID: "1211362365")
- Balance overview (2.50 USDT)
- Account statistics (5 available)
- Orders summary (0)
- Channel updates section

### 📞 Phone Management
- Add/manage phone numbers
- Status tracking (Pending/Accepted/Rejected)
- Search functionality
- Real-time status updates
- Status badges (ACCEPTED, FREE, SUCCESS)

### 🔐 Authentication
- Phone number-based login
- JWT token security
- Session management

### 📊 Real-time Updates
- WebSocket connections
- Live status changes
- Balance updates

## 🛠 Technology Stack

### Frontend
- **React 18** with TypeScript
- **Tailwind CSS** for styling
- **Zustand** for state management
- **React Router** for navigation
- **Axios** for API calls
- **React Hook Form** for forms
- **Vite** for build tool

### Backend
- **Node.js** with Express
- **TypeScript** for type safety
- **PostgreSQL** database
- **Prisma** ORM
- **JWT** authentication
- **WebSocket** for real-time

### DevOps
- **Docker** containerization
- **ESLint** & **Prettier**
- **Environment** configurations

## 📁 Project Structure

```
main-app/
├── frontend/                 # React TypeScript frontend
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/           # Page components
│   │   ├── hooks/           # Custom React hooks
│   │   ├── store/           # Zustand stores
│   │   ├── services/        # API services
│   │   ├── types/           # TypeScript definitions
│   │   └── styles/          # CSS styles
│   ├── public/              # Static assets
│   └── package.json
├── backend/                  # Node.js Express backend
│   ├── src/
│   │   ├── controllers/     # Route controllers
│   │   ├── models/          # Database models
│   │   ├── middleware/      # Express middleware
│   │   ├── routes/          # API routes
│   │   ├── services/        # Business logic
│   │   └── utils/           # Utility functions
│   ├── prisma/              # Database schema
│   └── package.json
├── docker-compose.yml        # Docker setup
├── .env.example             # Environment template
└── README.md
```

## 🔧 Development

### Available Scripts

**Frontend:**
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint
npm run type-check   # TypeScript check
```

**Backend:**
```bash
npm run dev          # Start with nodemon
npm run build        # Build TypeScript
npm run start        # Start production server
npm run db:generate  # Generate Prisma client
npm run db:push      # Push schema to database
npm run db:seed      # Seed database
```

### Environment Variables

Create `.env` file in root directory:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/new_one_receiver"

# JWT
JWT_SECRET="your-super-secret-jwt-key"
JWT_EXPIRES_IN="7d"

# API
API_URL="http://localhost:5000"
FRONTEND_URL="http://localhost:3000"

# Development
NODE_ENV="development"
```

## 🔒 Security Features

- JWT token authentication
- Input validation with Zod
- SQL injection prevention
- XSS protection
- CORS configuration
- Rate limiting
- Helmet security headers

## 📱 Mobile-First Design

The application is designed mobile-first to match the original mobile app:
- Responsive layout
- Touch-friendly interactions
- Optimized for mobile browsers
- Progressive Web App features

## 🚀 Deployment

### Docker Production
```bash
docker-compose -f docker-compose.prod.yml up -d
```

### Manual Deployment
1. Build frontend: `npm run build`
2. Build backend: `npm run build`
3. Set production environment variables
4. Start with process manager (PM2)

## 📄 API Documentation

### Authentication
- `POST /api/auth/login` - Login with phone number
- `POST /api/auth/logout` - Logout user
- `GET /api/auth/verify` - Verify JWT token

### User Management
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile
- `GET /api/user/balance` - Get user balance

### Phone Accounts
- `GET /api/accounts` - List phone accounts
- `POST /api/accounts` - Add phone account
- `PUT /api/accounts/:id` - Update account status
- `DELETE /api/accounts/:id` - Remove account

### Orders & Transactions
- `GET /api/orders` - List orders
- `POST /api/orders` - Create order
- `GET /api/transactions` - Transaction history

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -am 'Add new feature'`
4. Push to branch: `git push origin feature/new-feature`
5. Submit pull request

## 📝 License

This project is licensed under the MIT License.

---

**Version**: v0.8.0  
**Created**: July 30, 2025  
**Last Updated**: July 30, 2025