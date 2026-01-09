# Depayit Payment Platform

## Overview

Depayit is a secure peer-to-peer payment mediation platform that provides soft escrow services for online transactions. The platform acts as a trusted intermediary, holding payments temporarily until both buyers and sellers confirm transaction completion, reducing fraud risk in online marketplaces. Built with a modern full-stack architecture using React, Express, and PostgreSQL, the application supports PromptPay QR code payments and provides a complete transaction lifecycle management system.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side application is built with React 18 and TypeScript, using Vite as the build tool and development server. The UI framework leverages shadcn/ui components built on top of Radix UI primitives, styled with Tailwind CSS for consistent design. The application uses Wouter for lightweight client-side routing and TanStack Query for server state management and API caching. Form handling is implemented with React Hook Form and Zod for validation.

### Backend Architecture
The server is built with Express.js and TypeScript, following a RESTful API design pattern. The application uses a modular architecture with separate route handlers, storage abstractions, and middleware layers. The server includes request/response logging middleware and error handling for robust API operations. The storage layer uses an abstraction pattern with both in-memory and database implementations for flexibility during development and production deployment.

### Database Design
The system uses PostgreSQL as the primary database with Drizzle ORM for type-safe database operations. The schema includes a transactions table that tracks the complete lifecycle of payments, storing item details, amounts, seller PromptPay information, buyer data, payment status, and timestamps. The database is configured to work with Neon Database's serverless PostgreSQL offering for cloud deployment.

### Payment Integration
The platform integrates with Thailand's PromptPay system for QR code-based payments. While the current implementation includes mock payment processing for development, the architecture supports real PromptPay integration through QR code generation and payment verification systems.

### Session Management
The application is configured to support PostgreSQL-backed session storage using connect-pg-simple, providing persistent user sessions across server restarts and supporting horizontal scaling.

### Build and Deployment
The build system uses Vite for frontend compilation and esbuild for backend bundling. The application supports both development and production environments with appropriate optimizations. Static assets are served efficiently, and the build process generates optimized bundles for deployment.

## External Dependencies

### UI and Styling
- Radix UI components for accessible, unstyled UI primitives
- Tailwind CSS for utility-first styling with custom design tokens
- shadcn/ui component library for consistent design patterns
- Lucide React for iconography

### Database and ORM
- PostgreSQL database (configured for Neon Database)
- Drizzle ORM for type-safe database operations
- Drizzle Kit for database migrations and schema management

### State Management and Data Fetching
- TanStack React Query for server state management and caching
- React Hook Form with Zod resolver for form handling and validation

### Development and Build Tools
- Vite for frontend development and building
- TypeScript for type safety across the entire stack
- esbuild for backend bundling
- Replit-specific plugins for development environment integration

### Payment and Financial Services
- PromptPay integration (Thailand's national payment system)
- QR code generation for payment links
- Currency formatting utilities for Thai Baht

### Utility Libraries
- date-fns for date manipulation and formatting
- clsx and tailwind-merge for conditional CSS classes
- nanoid for unique ID generation
- Wouter for lightweight client-side routing