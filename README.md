# Visual Capital

**The Visualization Layer for the Agentic Era**

An AI engine that generates context-aware, interactive data visualizations on demand. Not from predefined charts, but composed dynamically by AI that understands your data.

## Overview

Visual Capital is a landing page for an AI-powered data visualization platform. The application showcases the concept of a "Visualization Engine as API" — embeddable, streaming UI components that any application can integrate to make their data views intelligent.

### Key Components

- **AI-Native**: The AI determines the right interactive experience for each data signal.
- **Embeddable SDK**: A Visualization Engine as API rendered as streaming React components
- **Context-Aware**: Every visualization is generated from your data's shape and the user's question — no configuration, no predefined templates

## Tech Stack

| Category       | Technology                      |
| -------------- | ------------------------------- |
| Framework      | Next.js 15.4 (App Router)       |
| Language       | TypeScript 5.9                  |
| Runtime        | React 19                        |
| Styling        | Tailwind CSS 4.1                |
| Animations     | Framer Motion (`motion/react`)  |
| Icons          | Lucide React                    |
| AI Integration | Google Gemini (`@google/genai`) |
| Deployment     | Vercel                          |

## Project Structure

```
visual-capital-new/
├── app/
│   ├── layout.tsx      # Root layout with fonts and metadata
│   ├── page.tsx        # Main landing page (Hero, Features, Footer)
│   └── globals.css     # Tailwind base + custom font variables
├── hooks/
│   └── use-mobile.ts   # Mobile viewport detection (768px breakpoint)
├── lib/
│   └── utils.ts        # cn() utility (clsx + tailwind-merge)
├── public/
│   └── hero-illustration.png
├── next.config.ts      # Next.js configuration (standalone output)
├── package.json
└── .env.example
```

## Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn

### Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd visual-capital-new
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Set up environment variables:

   ```bash
   cp .env.example .env.local
   ```

   Configure the following in `.env.local`:
   | Variable | Description |
   | --------------- | ------------------------------------------------ |
   | `GEMINI_API_KEY`| Google Gemini API key |
   | `APP_URL` | Hosted application URL (optional for local dev) |

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Scripts

| Command         | Description               |
| --------------- | ------------------------- |
| `npm run dev`   | Start development server  |
| `npm run build` | Create production build   |
| `npm start`     | Start production server   |
| `npm run lint`  | Run ESLint                |
| `npm run clean` | Clean Next.js build cache |

## Architecture Notes

- **App Router Only**: Pure Next.js App Router project — no `pages/` directory
- **Server Components**: Default to Server Components; `"use client"` only when hooks or browser APIs are required
- **Standalone Output**: Configured for Docker/Cloud Run deployment via `output: "standalone"`
- **HMR Handling**: Hot Module Replacement is disabled when `DISABLE_HMR=true` (AI Studio environment)
- **Path Alias**: `@/` maps to project root for clean imports

## Deployment

The app is deployed on Vercel platform.

## License

© 2026 Visual Capital. All rights reserved.

## Links

- [Twitter/X](https://x.com/visualcapital_)
