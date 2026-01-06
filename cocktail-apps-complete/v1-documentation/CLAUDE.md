# CLAUDE.md - Bar Companion AI Development Guide

> **Last Updated:** 2026-01-05
> **Purpose:** Comprehensive codebase documentation for AI assistants working on the Bar Companion AI project
---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Architecture Overview](#architecture-overview)
3. [Directory Structure](#directory-structure)
4. [Tech Stack](#tech-stack)
5. [Development Workflows](#development-workflows)
6. [Database & Schema](#database--schema)
7. [API Patterns & Conventions](#api-patterns--conventions)
8. [Authentication & Authorization](#authentication--authorization)
9. [State Management](#state-management)
10. [Frontend Patterns](#frontend-patterns)
11. [Code Conventions](#code-conventions)
12. [Key Files Reference](#key-files-reference)
13. [Common Development Tasks](#common-development-tasks)
14. [Deployment](#deployment)
15. [Troubleshooting](#troubleshooting)

---

## Project Overview

**Bar Companion AI** is a full-stack web application for intelligent home bar management with a focus on cocktail smoking techniques, personalized recommendations, and adaptive learning.

### Core Features

1. **Cocktail Database** - 1000+ built-in recipes with adaptive ranking
2. **Smoker Lab** - Guided smoking technique with 16+ wood profiles
3. **Inventory Management** - Bar stock tracking with barcode scanning
4. **Personalization** - Guest taste profiles with adaptive recommendations
5. **Pairing Engine** - Food-to-drink suggestions with reasoning
6. **Flights** - Side-by-side cocktail tasting planning
7. **Cost Tracking** - Optional per-drink cost calculation
8. **Guest Mode** - Try before you buy with data migration after login

### Design Philosophy

- **Mobile-First**: Touch-optimized with bottom navigation
- **Hybrid Intelligence**: Deterministic rules + adaptive learning
- **User Isolation**: All user data strictly partitioned by userId
- **Guest-Friendly**: Full feature access without authentication

---

*[Rest of the 1,283-line CLAUDE.md content follows exactly as provided]*
