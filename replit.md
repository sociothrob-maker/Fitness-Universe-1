# Retry - Full-Stack Fitness App

## Overview

Retry is a modern fitness application designed for Gen Z and power users, featuring AI-powered workout plans, daily challenges, social features, and a marketplace. The app combines fitness tracking with social engagement, rewards systems, and professional trainer connections to create a comprehensive fitness ecosystem.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**React SPA with TypeScript**: The client is built as a single-page application using React 18 with TypeScript for type safety. The application uses Wouter for client-side routing instead of React Router for a lighter footprint.

**Component Structure**: Follows a modular component architecture with:
- Pages in `/pages` directory for route components
- Reusable UI components using Radix UI primitives with custom styling
- Shared components for common functionality like navigation and modals

**State Management**: Uses TanStack Query (React Query) for server state management, providing caching, synchronization, and optimistic updates. Local state is managed with React hooks.

**Styling System**: Implements a design system using:
- Tailwind CSS for utility-first styling
- CSS custom properties for theming (dark theme by default)
- Shadcn/ui components for consistent UI patterns
- Class Variance Authority for component variants

### Backend Architecture

**Express.js Server**: RESTful API server with TypeScript, featuring:
- Middleware for request logging and error handling
- Route organization with proper separation of concerns
- Session-based authentication integration

**Database Layer**: Uses Drizzle ORM with PostgreSQL:
- Type-safe database operations
- Schema-first approach with shared types
- Migration support through Drizzle Kit
- Connection pooling with Neon serverless driver

**Authentication System**: Integrated with Replit's OpenID Connect authentication:
- Passport.js strategy for OIDC
- Session management with PostgreSQL store
- User profile synchronization with external auth provider

### Data Storage Solutions

**PostgreSQL Database**: Primary data store with tables for:
- User profiles and authentication sessions
- Workout plans, exercises, and fitness content
- Social features (posts, likes, comments)
- E-commerce products and marketplace items
- Progress tracking and rewards system

**Schema Design**: Relational database design with proper foreign key relationships, indexing for performance, and JSON columns for flexible metadata storage.

### External Dependencies

**Authentication**: Replit's OpenID Connect service for user authentication and authorization, eliminating the need for custom auth implementation.

**Database Hosting**: Neon PostgreSQL for serverless database hosting with automatic scaling and connection pooling.

**UI Framework**: Radix UI primitives provide accessible, unstyled components that serve as the foundation for the custom design system.

**Development Tools**: 
- Vite for fast development builds and hot module replacement
- ESBuild for production bundling
- TypeScript for static type checking across the full stack

**Real-time Features**: Architecture supports future WebSocket integration for real-time social features and live workout sessions.

**Third-party Integrations**: Prepared for fitness API integrations, payment processing for the marketplace, and external trainer platforms through the modular service layer.