# Windbreaker Token Airdrop Platform

## Overview

This is a full-stack web application for a Solana-based cryptocurrency airdrop platform called "Windbreaker" ($WB). The application allows users to submit their Solana wallet addresses, complete social media tasks, earn tokens through mining mechanics, and participate in a referral system to earn additional rewards.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a modern full-stack architecture with a clear separation between frontend and backend concerns:

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **UI Components**: Radix UI components with shadcn/ui styling system
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL (configured for Neon serverless)
- **API Pattern**: RESTful API with JSON responses

### Database Schema
The application uses a PostgreSQL database with the following core tables:
- **users**: Stores wallet addresses, balances, and mining timestamps
- **referrals**: Tracks referral relationships and bonus awards
- **tasks**: Records user task completions (Twitter, Discord, Telegram, reposts)
- **mining_logs**: Logs mining claims and amounts

## Key Components

### Authentication & User Management
- Wallet-based authentication using Solana wallet addresses
- No traditional password-based authentication
- User identification through wallet address validation

### Core Features
1. **Wallet Submission**: Users submit Solana wallet addresses to join
2. **Task System**: Social media engagement tasks (Twitter follow, Discord join, etc.)
3. **Mining Mechanism**: Daily token claiming with 24-hour cooldowns
4. **Referral System**: Users earn bonuses for referring new participants

### UI Components
- Responsive design with mobile-first approach
- Dark theme with purple/cyan accent colors
- Modular component architecture using shadcn/ui
- Toast notifications for user feedback
- Progress indicators for mining cooldowns

## Data Flow

1. **User Onboarding**: 
   - User submits wallet address on home page
   - System validates address and creates user record
   - Referral bonuses applied if applicable
   - User redirected to dashboard

2. **Task Completion**:
   - User views available tasks on dashboard
   - Completes external actions (social media follows/joins)
   - Claims task completion through API
   - Token balance updated automatically

3. **Mining System**:
   - Users can claim mining rewards every 24 hours
   - Progress bar shows countdown to next claim
   - Automatic balance updates upon successful claims

4. **Referral Flow**:
   - Users share referral links with their wallet address
   - New users get bonus tokens for using referral
   - Referrers earn additional tokens for successful referrals

## External Dependencies

### Frontend Dependencies
- **@tanstack/react-query**: Server state management and caching
- **@radix-ui/***: Accessible UI primitives
- **wouter**: Lightweight client-side routing
- **tailwindcss**: Utility-first CSS framework
- **lucide-react**: Icon library

### Backend Dependencies
- **drizzle-orm**: Type-safe ORM for database operations
- **@neondatabase/serverless**: Serverless PostgreSQL driver
- **express**: Web application framework
- **zod**: Runtime type validation

### Development Tools
- **vite**: Build tool and development server
- **typescript**: Type safety and development experience
- **esbuild**: Fast JavaScript bundler for production

## Deployment Strategy

### Development Environment
- Vite development server for frontend hot reloading
- Express server with TypeScript compilation via tsx
- Database migrations handled through Drizzle Kit
- Environment variables for database connection

### Production Build
- Frontend built to static assets via Vite
- Backend bundled with esbuild for Node.js deployment
- Serves static frontend files from Express server
- PostgreSQL database hosted on Neon (serverless)

### Environment Configuration
- **DATABASE_URL**: PostgreSQL connection string (required)
- **NODE_ENV**: Environment mode (development/production)
- Drizzle configured for PostgreSQL dialect with migration support

### Scalability Considerations
- Serverless-ready architecture with Neon PostgreSQL
- Stateless Express server suitable for horizontal scaling
- Client-side routing reduces server load
- Optimistic UI updates with React Query caching

## Recent Changes

### July 22, 2025 - Crypto Airdrop Website Completed
- Successfully built full-stack $WB (Windbreaker) token airdrop website
- Implemented wallet submission system (500 $WB reward)
- Added referral system (700 $WB for referred users, +100 $WB for referrer)
- Created task completion system (4 tasks x 50 $WB each)
- Built daily mining feature (50 $WB every 24 hours)
- Fixed navigation and dashboard access issues
- Website fully functional with real-time updates
- Using temporary in-memory storage (data resets on server restart)
- Database connection ready for Supabase when proper PostgreSQL URL is configured