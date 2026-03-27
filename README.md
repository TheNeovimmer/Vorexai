# Vorex - Smart Logistics & Delivery Platform

<p align="center">
  <strong>A comprehensive logistics and delivery management platform built with modern technologies</strong>
</p>

<p align="center">
  <strong>Author:</strong> TheNeovimmer
</p>

---

## Overview

Vorex is an all-in-one logistics and delivery management platform that connects drivers, sellers, warehouses, and customers through a modern web interface and AI-powered assistance. The platform streamlines delivery operations with real-time tracking, inventory management, order processing, and intelligent voice assistance.

---

## Tech Stack

### Frontend
- **React 18** - UI framework
- **TypeScript** - Type safety
- **Vite** - Build tool
- **Tailwind CSS** - Styling
- **Zustand** - State management
- **React Query** - Server state management
- **React Router** - Routing
- **Recharts** - Data visualization
- **Leaflet** - Maps and tracking
- **Radix UI** - UI components

### Backend Services
- **Python (Flask)** - Voice AI assistant backend
- **PostgreSQL** - Database
- **Prisma** - ORM
- **LiveKit** - Real-time voice communication

### AI & Intelligence
- **Gemini API** - AI-powered vehicle assistant
- **Voice AI** - Real-time speech interaction

---

## Features

### For Drivers
- Driver application and onboarding
- Available routes and delivery assignments
- Active delivery tracking with live map
- Delivery history and earnings
- Vehicle management
- AI voice assistant for vehicle queries

### For Sellers
- Product catalog management
- Order creation and tracking
- Invoice generation
- Sales dashboard and analytics
- API access for integrations

### For Warehouse
- Inventory management
- Incoming and outgoing orders
- Stock levels monitoring
- Warehouse sections organization

### Core Features
- Real-time order tracking with map timeline
- Multi-role authentication (Driver, Seller, Warehouse)
- AI-powered chat assistant for vehicle information
- Voice AI for hands-free assistance
- Notification system
- Invoice generation with PDF export

---

## Architecture

```
Vorex/
├── apps/
│   └── web/                 # React frontend application
│       ├── src/
│       │   ├── pages/       # Page components
│       │   ├── components/  # Reusable UI components
│       │   ├── routes/      # Route definitions
│       │   ├── services/    # API services
│       │   ├── stores/      # Zustand stores
│       │   └── types/       # TypeScript types
│       └── ...
├── vehicle-ai-assistant/    # Python Flask AI assistant
│   ├── api/                # API modules
│   │   ├── ai_assistant.py
│   │   ├── voice_ai.py
│   │   └── database.py
│   ├── templates/
│   ├── static/
│   └── app.py
└── ...
```

---

## Prerequisites

- **Node.js** (v18+)
- **Bun** (recommended) or npm/yarn
- **Python** (v3.10+)
- **PostgreSQL** (v14+)
- **Gemini API Key** (for AI features)
- **LiveKit Credentials** (for voice AI)

---

## Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd Vorexai
```

### 2. Install frontend dependencies

```bash
bun install
```

### 3. Install web app dependencies

```bash
cd apps/web
bun install
```

### 4. Set up Python backend

```bash
cd vehicle-ai-assistant
pip install -r requirements.txt
```

### 5. Configure environment variables

Create `.env` files with required credentials:

#### Root `.env`
```
DATABASE_URL=postgresql://admin:admin@localhost:5432/vorex_db
```

#### Vehicle AI Assistant `.env`
```
GEMINI_API_KEY=your_gemini_api_key
LIVEKIT_URL=ws://localhost:7880
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_secret
PORT=5000
```

### 6. Set up PostgreSQL

```bash
docker run --name vorex-postgres \
  -e POSTGRES_USER=admin \
  -e POSTGRES_PASSWORD=admin \
  -e POSTGRES_DB=vorex_db \
  -p 5432:5432 \
  -d postgres
```

---

## Running the Application

### Development Mode

#### Start the web application
```bash
cd apps/web
bun run dev
```
Access at: `http://localhost:5173`

#### Start the voice AI assistant
```bash
cd vehicle-ai-assistant
python app.py
```
API available at: `http://localhost:5000`

### Production Build

```bash
cd apps/web
bun run build
```

---

## Docker Deployment

### Using Docker Compose

```bash
docker-compose up -d
```

---

## Available Scripts

### Root
- `bun run index.ts` - Run main entry point

### Web App
- `bun run dev` - Start development server
- `bun run build` - Build for production
- `bun run lint` - Run ESLint
- `bun run preview` - Preview production build

---

## API Documentation

### Voice AI Assistant Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Home page |
| `/api/assistant/chat` | POST | Chat with AI assistant |
| `/api/assistant/health-check` | GET | Health check |

### Request Format

```json
POST /api/assistant/chat
{
  "driver_id": "driver_123",
  "message": "What's my vehicle status?"
}
```

---

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `DATABASE_URL` | PostgreSQL connection string | Yes |
| `GEMINI_API_KEY` | Google Gemini API key | No (mock mode) |
| `LIVEKIT_URL` | LiveKit WebSocket URL | For voice AI |
| `LIVEKIT_API_KEY` | LiveKit API key | For voice AI |
| `LIVEKIT_API_SECRET` | LiveKit API secret | For voice AI |

---

## License

This project is proprietary and all rights reserved.

---

## Contact

For questions or support, please contact the author.

---

<p align="center">
  Built with passion by <strong>TheNeovimmer</strong>
</p>
