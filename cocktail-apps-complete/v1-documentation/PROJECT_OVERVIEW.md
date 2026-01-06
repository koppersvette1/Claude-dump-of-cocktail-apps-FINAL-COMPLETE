# Bar Companion AI - v1 Project Overview

> Your sophisticated, production-ready cocktail management application

---

## What is Bar Companion AI?

Bar Companion AI is a full-stack web application for intelligent home bar management with a focus on cocktail smoking techniques, personalized recommendations, and adaptive learning. This is your most advanced version, currently deployed on GitHub.

---

## Core Architecture

**Monorepo Structure:**
- `/client` - React 19 frontend
- `/server` - Node.js backend
- `/shared` - Shared TypeScript types

**Tech Stack:**
- **Frontend:** React 19, Zustand (state), React Query (server state), shadcn/ui, Tailwind CSS
- **Backend:** Node.js, Express, Passport.js (auth)
- **Database:** PostgreSQL with Drizzle ORM
- **Deployment:** Replit

---

## Core Features

### 1. Cocktail Database (1000+ recipes)
- Built-in recipes with adaptive ranking
- Search and filter capabilities
- Detailed recipe information (ingredients, steps, tips)
- Technique indicators (stirred, shaken, built)
- Difficulty ratings and prep times

### 2. Smoker Lab
- 16+ wood profiles (Cherry, Oak, Hickory, Mesquite, Apple, etc.)
- Intensity ratings (Light, Medium, Heavy, Very Heavy)
- Guided smoking timers
- Temperature monitoring
- Wood-cocktail pairing suggestions
- Safety guardrails and time limits

### 3. Inventory Management
- Bar stock tracking
- Barcode scanning support
- Quantity tracking
- Expiration date monitoring
- Cost tracking (optional per-drink)
- Low-stock alerts

### 4. Guest Taste Profiles
- Personal preference tracking
- Sweetness tolerance (1-10)
- ABV comfort level
- Flavor profile preferences
- Adaptive recommendations based on history
- Weight vector learning for taste prediction

### 5. Pairing Engine
- Food-to-drink suggestions
- Reasoning explanations for pairings
- Cocktail-to-food recommendations
- Context-aware suggestions

### 6. Flights System
- Side-by-side cocktail tasting planning
- Comparison tools
- Note-taking for each drink
- Flight history tracking

### 7. Cost Tracking
- Optional per-drink cost calculation
- Inventory cost tracking
- Cost per serving analytics

---

## Key Design Patterns

### Hybrid Intelligence
**Deterministic Rules** (`/client/src/lib/logic/rules.ts`)
- Safety guardrails
- Smoke time limits
- Ingredient validation
- Physics-based constraints

**Adaptive Learning** (`/client/src/lib/logic/learning.ts`)
- Taste weight vectors
- Wood affinity scoring
- Contextual ranking
- User preference evolution

### User Isolation
Every user-owned table includes:
```typescript
userId: varchar("user_id").notNull()
```
All queries filter: `eq(table.userId, userId)`

### Guest Mode → Authenticated Sync
- Guest data stored in Zustand (localStorage)
- After login: `POST /api/migrate-guest-data` bulk transfers
- Error handling per item with migration report

---

## Mobile-First Design Philosophy

**Bottom Navigation:**
- Primary navigation at thumb-reach
- 5-tab layout
- Icon + label for clarity

**Card-Based UI:**
- shadcn/ui components
- CardHeader, CardTitle, CardContent sections
- Consistent visual hierarchy
- Touch-friendly targets (min 44x44px)

**Responsive Breakpoints:**
- Mobile: <640px
- Tablet: 640-1024px
- Desktop: >1024px

---

## State Management

**Client State (Zustand):**
- User preferences
- UI state (modals, filters)
- Guest mode data
- Persistent: localStorage sync

**Server State (React Query):**
- API data caching
- Optimistic updates
- Background refetch
- Error retry logic

---

## Database Schema

**User Tables:**
- `users` - Authentication and profile
- `cocktails` - User-created recipes
- `inventory` - Bar stock items
- `favorites` - Saved recipes
- `people` - Guest profiles
- `smoke_sessions` - Smoking history
- `flights` - Tasting flights
- `pairings` - Food-drink combinations

**System Tables:**
- Built-in cocktails (1000+)
- Wood profiles (16+)
- Ingredient master list

---

## API Patterns

**RESTful Endpoints:**
```
GET    /api/cocktails          # List all
GET    /api/cocktails/:id      # Get one
POST   /api/cocktails          # Create
PATCH  /api/cocktails/:id      # Update
DELETE /api/cocktails/:id      # Delete
```

**Authentication:**
- Session-based auth with Passport.js
- Cookie storage
- CSRF protection
- User isolation on all routes

---

## Development Workflow

**Local Development:**
```bash
npm install        # Install dependencies
npm run dev        # Start dev server
npm run check      # TypeScript validation
npm run db:push    # Sync database schema
```

**Testing:**
- Manual testing in development
- TypeScript for type safety
- Zod for runtime validation

---

## Why This Architecture?

**Monorepo Benefits:**
- Shared types between frontend/backend
- Single dependency tree
- Unified build process
- Type safety across boundaries

**Why Zustand:**
- Minimal boilerplate
- Easy persistence
- DevTools support
- Great performance

**Why Drizzle:**
- Type-safe queries
- Automatic migrations
- PostgreSQL-first
- Great DX

**Why shadcn/ui:**
- Copy-paste components
- Full customization
- Accessible by default
- Consistent design language

---

## Key Differentiators

What makes Bar Companion AI special:

1. **Smoking Focus:** Only cocktail app with comprehensive smoking guidance
2. **Adaptive Learning:** Learns user preferences over time
3. **Full Inventory:** Track everything in your bar
4. **Guest Profiles:** Personalize for each person you serve
5. **Pairing Engine:** Smart food-drink suggestions with reasoning
6. **Hybrid Intelligence:** Combines rules with learning
7. **Professional Polish:** shadcn/ui design system throughout

---

## Current Status

**Deployed:** github.com/koppersvette1/v1-Bar-Companion-AI
**Stage:** Production-ready, actively maintained
**Users:** Personal use, ready for scaling

---

## Future Roadmap

Potential enhancements:
- Social features (share recipes)
- Community cocktail library
- AR garnish visualization
- Voice control integration
- Professional bartender mode
- Inventory auto-replenishment
- Recipe scaling calculator

---

This is your flagship application - the most sophisticated and feature-complete version of your cocktail app vision!
