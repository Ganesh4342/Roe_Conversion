# Overview

AirlinePolicy Pro is a comprehensive airline policy management system that enables airlines to manage cancellation policies, calculate penalties, and process booking data. The application provides a unified platform for configuring airline-specific policies, tax rules, regex patterns for data validation, and generating analytical reports on penalty calculations and booking statistics.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

The frontend is built with React 18 using TypeScript and Vite as the build tool. The application follows a component-based architecture with:

- **UI Framework**: Radix UI primitives with shadcn/ui components for consistent design
- **Styling**: Tailwind CSS with CSS variables for theming support
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query for server state management and caching
- **Form Handling**: React Hook Form with Zod validation schemas

The application is structured as a single-page application with a sidebar navigation layout. Key pages include Dashboard, Import Bookings, Policies, Tax Rules, Regex Patterns, Search Bookings, and Reports.

## Backend Architecture

The backend uses a Node.js Express server with TypeScript, following a RESTful API design:

- **Framework**: Express.js with middleware for JSON parsing and request logging
- **Database Layer**: Drizzle ORM with PostgreSQL as the database
- **API Structure**: Route handlers organized in `/api` endpoints for each resource
- **Validation**: Zod schemas shared between frontend and backend for type safety
- **Error Handling**: Centralized error middleware with structured error responses

The server includes development-specific features like Vite integration for hot module replacement and static file serving.

## Data Storage Solutions

**Database**: PostgreSQL with Neon serverless connection pooling for scalability. The database schema includes:

- Airlines table for airline information and codes
- Policies table for cancellation rules with flexible JSON conditions
- Tax rules table for regional tax calculation configurations
- Regex patterns table for data validation and extraction
- Bookings table for flight booking records
- Penalty calculations table for computed penalty amounts
- Users table for legacy authentication support

**Schema Design**: Uses Drizzle ORM with generated UUID primary keys, proper foreign key relationships, and JSON fields for flexible policy conditions.

## Authentication and Authorization

The application includes infrastructure for session-based authentication using:
- PostgreSQL session storage with connect-pg-simple
- User management schema in the database
- Session middleware configuration (currently not fully implemented)

## External Dependencies

**Database Services**:
- Neon Database: Serverless PostgreSQL hosting with connection pooling
- WebSocket support for real-time database connections

**Development Tools**:
- Replit integration: Custom Vite plugins for development environment
- Drizzle Kit: Database migration and schema management
- ESBuild: Server-side code bundling for production

**UI Libraries**:
- Radix UI: Accessible component primitives for forms, dialogs, and navigation
- Lucide React: Icon library for consistent iconography
- TanStack Query: Server state management and caching
- React Hook Form: Form validation and state management

**Utility Libraries**:
- Zod: Runtime type validation and schema generation
- date-fns: Date manipulation and formatting
- clsx/tailwind-merge: Conditional CSS class management