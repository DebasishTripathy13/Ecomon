# Technology Stack

## Frontend

- **Next.js 14** - App Router, Server Components, Server Actions
- **TypeScript** - Type safety across the codebase
- **Tailwind CSS** - Utility-first styling
- **Framer Motion** - Animations (60fps target, 3-5s evolution animations)
- **Solana Wallet Adapter** - Phantom Wallet integration
- **React Query** - Data fetching and caching

## Backend

- **Node.js** with Express.js
- **Prisma ORM** - Database access layer
- **PostgreSQL** - Hosted on Supabase
- **Redis** - Caching and session management
- **WebSocket** - Real-time updates

## AI & Blockchain

- **Google Gemini Vision API** - Image verification (95% accuracy threshold)
- **Solana Web3.js** - Blockchain interactions
- **Metaplex SDK** - Compressed NFT operations
- **Anchor Framework** - Smart contract interactions
- **OpenAI Embeddings** - (Mentioned in architecture)

## Infrastructure

- **Vercel** - Frontend hosting
- **Railway/Render** - Backend hosting
- **Supabase** - Database and storage
- **Cloudflare** - CDN and DDoS protection

## Development Standards

### Performance Targets

- AI verification response: < 5 seconds
- NFT minting display: < 10 seconds
- Animations: 60fps smooth performance
- Mobile-optimized for varying device capabilities

### Code Quality

- TypeScript strict mode enabled
- Prisma for type-safe database queries
- Interface-driven design for all services
- Comprehensive error handling with user-friendly feedback

### Security

- Industry-standard encryption for sensitive data
- JWT tokens for session management
- Wallet signature verification
- Privacy controls for eco-action visibility

## Common Commands

### Database

```bash
# Generate Prisma client
npx prisma generate

# Run migrations
npx prisma migrate dev

# Open Prisma Studio
npx prisma studio

# Reset database
npx prisma migrate reset
```

### Development

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Type checking
npm run type-check

# Linting
npm run lint
```

### Testing

```bash
# Run tests
npm test

# Run tests in watch mode
npm run test:watch

# Generate coverage report
npm run test:coverage
```

### Blockchain

```bash
# Build Anchor program
anchor build

# Deploy to devnet
anchor deploy --provider.cluster devnet

# Run Anchor tests
anchor test
```

## Environment Variables

Required environment variables for local development:

```
# Database
DATABASE_URL=postgresql://...
DIRECT_URL=postgresql://...

# Supabase
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=

# AI Services
GEMINI_API_KEY=
OPENAI_API_KEY=

# Solana
SOLANA_RPC_URL=
SOLANA_NETWORK=devnet
WALLET_PRIVATE_KEY=

# Redis
REDIS_URL=

# App
NEXT_PUBLIC_APP_URL=
JWT_SECRET=
```
