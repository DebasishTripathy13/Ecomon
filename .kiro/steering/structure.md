# Project Structure

## Architecture Pattern

Verdleaf follows a **microservices-inspired monorepo** architecture with clear separation of concerns:

- **Client Layer** - Next.js frontend + Phantom Wallet
- **API Layer** - REST API + WebSocket server
- **Service Layer** - Business logic services
- **External Services** - Gemini Vision, Solana, Metaplex
- **Data Layer** - PostgreSQL, Redis, Image Storage

## Expected Folder Organization

```
verdleaf/
├── .kiro/                      # Kiro configuration
│   ├── hooks/                  # Agent hooks
│   ├── specs/                  # Feature specifications
│   └── steering/               # Project guidelines
│
├── src/
│   ├── app/                    # Next.js 14 App Router
│   │   ├── (auth)/            # Auth-protected routes
│   │   ├── (public)/          # Public routes
│   │   ├── api/               # API routes
│   │   └── layout.tsx         # Root layout
│   │
│   ├── components/            # React components
│   │   ├── ui/               # Reusable UI components
│   │   ├── eco-mon/          # EcoMon display components
│   │   ├── dashboard/        # Dashboard widgets
│   │   └── animations/       # Framer Motion animations
│   │
│   ├── services/              # Business logic services
│   │   ├── auth.service.ts
│   │   ├── verification.service.ts
│   │   ├── nft.service.ts
│   │   ├── reward.service.ts
│   │   └── marketplace.service.ts
│   │
│   ├── lib/                   # Utilities and configurations
│   │   ├── prisma.ts         # Prisma client
│   │   ├── redis.ts          # Redis client
│   │   ├── solana.ts         # Solana connection
│   │   ├── gemini.ts         # Gemini API client
│   │   └── utils.ts          # Helper functions
│   │
│   ├── types/                 # TypeScript type definitions
│   │   ├── user.ts
│   │   ├── eco-action.ts
│   │   ├── nft.ts
│   │   └── marketplace.ts
│   │
│   ├── hooks/                 # React hooks
│   │   ├── useWallet.ts
│   │   ├── useEcoMon.ts
│   │   └── useImpactMetrics.ts
│   │
│   └── styles/                # Global styles
│       └── globals.css
│
├── prisma/
│   ├── schema.prisma          # Database schema
│   ├── migrations/            # Database migrations
│   └── seed.ts                # Seed data
│
├── programs/                   # Solana programs (Anchor)
│   └── verdleaf/
│       ├── src/
│       └── Cargo.toml
│
├── public/                     # Static assets
│   ├── images/
│   │   ├── eco-mon/          # EcoMon evolution images
│   │   └── badges/           # Badge images
│   └── animations/
│
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
│
├── scripts/                    # Utility scripts
│   ├── deploy.ts
│   └── generate-nft-metadata.ts
│
├── .env.local                  # Environment variables
├── .env.example               # Example environment variables
├── next.config.js             # Next.js configuration
├── tailwind.config.ts         # Tailwind configuration
├── tsconfig.json              # TypeScript configuration
├── package.json
└── README.md
```

## Key Conventions

### Service Layer Pattern

All business logic is encapsulated in services with clear interfaces:

- `AuthService` - Wallet authentication and session management
- `VerificationService` - AI image verification and EcoPoints calculation
- `NFTService` - EcoMon and badge NFT operations
- `RewardService` - EcoPoints tracking and impact metrics
- `MarketplaceService` - Product listings and purchases

### Data Models

Database models follow Prisma schema conventions:
- `User` - Wallet-based user accounts
- `EcoAction` - Verified eco-actions with images
- `EcoMon` - Dynamic NFT companions
- `Badge` - Achievement NFTs
- `Transaction` - EcoPoints transactions
- `Product` - Marketplace items
- `Order` - Purchase records

### Component Organization

- **UI Components** - Atomic, reusable components (buttons, cards, modals)
- **Feature Components** - Domain-specific components (EcoMonDisplay, ActionSubmissionForm)
- **Layout Components** - Page structure components (DashboardLayout, MarketplaceLayout)
- **Animation Components** - Framer Motion wrappers for transitions

### API Routes

Next.js API routes organized by domain:
- `/api/auth/*` - Authentication endpoints
- `/api/actions/*` - Eco-action submission and verification
- `/api/nft/*` - NFT minting and evolution
- `/api/marketplace/*` - Product and order management
- `/api/metrics/*` - Impact statistics

### Evolution Stages

EcoMon evolution thresholds:
- **Sproutling**: 0-10 actions
- **Bloomkin**: 11-30 actions
- **Florazen**: 31-75 actions
- **Terravine**: 76-150 actions
- **Gaiabloom**: 151+ actions

### Badge Milestones

- **First Steps**: 1 action
- **Eco Warrior**: 25 actions
- **Carbon Crusher**: 100 actions
- **Green Guardian**: 250 actions
- **Legendary Leaf**: 500 actions

## Design Principles

1. **Verifiable First** - All eco-actions must pass AI verification (95% confidence)
2. **On-Chain Proof** - NFTs and key transactions recorded on Solana
3. **Gamified Experience** - Animations, evolution, and rewards drive engagement
4. **Mobile-Responsive** - Touch-optimized for on-the-go eco-action submission
5. **Privacy-Conscious** - User control over data visibility and retention
6. **Performance-Focused** - Sub-5s verification, 60fps animations, optimized mobile
