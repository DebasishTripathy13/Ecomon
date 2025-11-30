# Requirements Document

## Introduction

Verdleaf is an AI-Verified Eco-Companion platform built on Solana that transforms climate anxiety into verifiable, rewarding action. The platform addresses three critical barriers to sustained eco-action: invisible impact, trust deficit, and isolation. By combining AI verification (Gemini Vision), dynamic NFTs (EcoMon evolution), and real rewards (EcoPoints marketplace), Verdleaf creates a gamified ecosystem that turns eco-intentions into verified, on-chain impact.

Target users are Gen Z and Millennial digital natives who value sustainability, gamification, and social signaling. The platform aims to achieve 1M+ verified actions, 50k trees planted, 100t CO2 offset, and $500k in eco-sales by 2026.

## Glossary

- **Verdleaf**: The AI-Verified Eco-Companion platform on Solana
- **EcoMon**: Dynamic NFT companion that evolves based on user eco-actions
- **AI Verification Engine**: Gemini Vision-powered system that validates eco-actions with 95% accuracy
- **EcoPoints**: On-chain reward tokens earned through verified eco-actions
- **Evolution Stages**: Five progressive EcoMon forms (Sproutling → Bloomkin → Florazen → Terravine → Gaiabloom)
- **Eco-Action**: User-submitted sustainable activity requiring AI verification
- **Collectible Badges**: Achievement NFTs earned at milestones (First Steps, Eco Warrior, Carbon Crusher, Green Guardian, Legendary Leaf)
- **Verified Marketplace**: Platform for spending EcoPoints on authenticated sustainable goods
- **Phantom Wallet**: Solana wallet adapter for Web3 authentication
- **Metaplex**: Solana NFT standard used for compressed NFTs
- **Impact Dashboard**: User interface displaying verified actions, CO2 offset, and environmental metrics

## Requirements

### Requirement 1

**User Story:** As an eco-conscious user, I want to submit photos of my sustainable actions for AI verification, so that my environmental impact is validated and recorded on-chain.

#### Acceptance Criteria

1. WHEN a user uploads a photo of an eco-action, THE AI Verification Engine SHALL analyze the image using Gemini Vision API
2. WHEN the AI Verification Engine processes an image, THE system SHALL return a verification result with confidence score within 5 seconds
3. WHEN the verification confidence score exceeds 95%, THE system SHALL approve the eco-action and record it on-chain
4. IF the verification confidence score falls below 95%, THEN THE system SHALL reject the action and provide feedback to the user
5. WHEN an eco-action is verified, THE system SHALL calculate and assign EcoPoints based on action type and impact level

### Requirement 2

**User Story:** As a new user, I want to receive a unique EcoMon NFT companion when I join Verdleaf, so that I have a personalized digital representation of my eco-journey.

#### Acceptance Criteria

1. WHEN a user connects their Phantom Wallet for the first time, THE system SHALL mint a unique Sproutling EcoMon NFT to their wallet address
2. WHEN minting an EcoMon, THE system SHALL use Metaplex compressed NFT standard to minimize transaction costs
3. WHEN an EcoMon is created, THE system SHALL generate unique visual attributes and metadata stored on-chain
4. WHEN the minting transaction completes, THE system SHALL display the new EcoMon in the user's profile within 10 seconds
5. THE system SHALL ensure each user wallet address receives exactly one initial EcoMon NFT

### Requirement 3

**User Story:** As an active user, I want my EcoMon to evolve through five stages as I complete verified eco-actions, so that I can visualize my growing environmental impact.

#### Acceptance Criteria

1. WHEN a user accumulates sufficient verified actions, THE system SHALL trigger an evolution from current stage to next stage
2. WHEN an evolution is triggered, THE system SHALL update the EcoMon NFT metadata on-chain to reflect the new form
3. THE system SHALL define five evolution stages with specific thresholds: Sproutling (0-10 actions), Bloomkin (11-30 actions), Florazen (31-75 actions), Terravine (76-150 actions), Gaiabloom (151+ actions)
4. WHEN an EcoMon evolves, THE system SHALL update the visual representation and notify the user with an animation
5. WHEN querying an EcoMon, THE system SHALL return current evolution stage, total verified actions, and progress to next stage

### Requirement 4

**User Story:** As a motivated user, I want to earn collectible badge NFTs for reaching milestones, so that I can showcase my achievements and feel recognized for my efforts.

#### Acceptance Criteria

1. WHEN a user reaches a predefined milestone, THE system SHALL mint a collectible badge NFT to their wallet
2. THE system SHALL define five badge types with specific unlock criteria: First Steps (1 action), Eco Warrior (25 actions), Carbon Crusher (100 actions), Green Guardian (250 actions), Legendary Leaf (500 actions)
3. WHEN a badge is earned, THE system SHALL display a celebration animation and add the badge to the user's collection
4. WHEN viewing a user profile, THE system SHALL display all earned badges with unlock dates
5. THE system SHALL prevent duplicate badge minting for the same milestone

### Requirement 5

**User Story:** As a user earning EcoPoints, I want to spend them on verified sustainable products in a marketplace, so that my virtual rewards translate into real-world environmental impact.

#### Acceptance Criteria

1. WHEN a user accesses the marketplace, THE system SHALL display available sustainable products with EcoPoint prices
2. WHEN a user purchases a product, THE system SHALL deduct the corresponding EcoPoints from their balance
3. WHEN a purchase is completed, THE system SHALL record the transaction on-chain and initiate product fulfillment
4. THE system SHALL verify all marketplace vendors and products meet sustainability criteria before listing
5. WHEN displaying products, THE system SHALL show verification status, environmental impact metrics, and user reviews

### Requirement 6

**User Story:** As a user, I want to view my comprehensive impact dashboard showing verified actions, CO2 offset, trees planted, and EcoPoints earned, so that I can track my environmental contribution over time.

#### Acceptance Criteria

1. WHEN a user accesses their dashboard, THE system SHALL display total verified actions, cumulative CO2 offset, trees planted equivalent, and current EcoPoints balance
2. WHEN calculating environmental metrics, THE system SHALL use standardized conversion rates for each action type
3. WHEN displaying historical data, THE system SHALL provide time-series visualizations showing progress over days, weeks, and months
4. WHEN a user completes a new verified action, THE system SHALL update all dashboard metrics in real-time
5. THE system SHALL allow users to share their impact statistics on social media platforms

### Requirement 7

**User Story:** As a user, I want to authenticate securely using my Phantom Wallet, so that my identity and NFTs are protected while maintaining Web3 principles.

#### Acceptance Criteria

1. WHEN a user clicks connect wallet, THE system SHALL initiate Phantom Wallet connection using Solana wallet adapter
2. WHEN wallet connection is established, THE system SHALL retrieve the user's public key and verify ownership
3. WHEN a user signs a transaction, THE system SHALL request signature through Phantom Wallet interface
4. IF a user's wallet is not connected, THEN THE system SHALL restrict access to protected features and prompt authentication
5. WHEN a user disconnects their wallet, THE system SHALL clear session data and return to unauthenticated state

### Requirement 8

**User Story:** As a user, I want to see real-time feedback and animations when I submit actions, earn rewards, or achieve milestones, so that the experience feels engaging and responsive.

#### Acceptance Criteria

1. WHEN a user submits an eco-action, THE system SHALL display a loading animation during AI verification
2. WHEN verification completes successfully, THE system SHALL show a success animation with earned EcoPoints
3. WHEN an EcoMon evolves, THE system SHALL play a transformation animation lasting 3-5 seconds
4. WHEN a badge is unlocked, THE system SHALL display a celebration animation with confetti effects
5. THE system SHALL use Framer Motion for all animations to ensure smooth 60fps performance

### Requirement 9

**User Story:** As a platform administrator, I want to monitor system health, verification accuracy, and user engagement metrics, so that I can ensure platform reliability and optimize user experience.

#### Acceptance Criteria

1. WHEN an administrator accesses the admin dashboard, THE system SHALL display real-time metrics for active users, verification requests, and system uptime
2. WHEN monitoring AI verification, THE system SHALL track accuracy rates, false positive rates, and average processing time
3. WHEN analyzing user engagement, THE system SHALL provide metrics on daily active users, retention rates, and average actions per user
4. WHEN system errors occur, THE system SHALL log detailed error information and send alerts to administrators
5. THE system SHALL generate weekly reports summarizing platform growth, environmental impact, and technical performance

### Requirement 10

**User Story:** As a user, I want the platform to handle errors gracefully and provide clear feedback, so that I understand what went wrong and how to proceed.

#### Acceptance Criteria

1. WHEN an image upload fails, THE system SHALL display an error message explaining the issue and suggesting corrective actions
2. WHEN AI verification is uncertain, THE system SHALL provide specific feedback on why the action could not be verified
3. WHEN a blockchain transaction fails, THE system SHALL explain the failure reason and offer retry options
4. WHEN network connectivity is lost, THE system SHALL display an offline indicator and queue actions for later submission
5. THE system SHALL log all errors with sufficient context for debugging while maintaining user privacy

### Requirement 11

**User Story:** As a mobile user, I want to access Verdleaf on my smartphone with full functionality, so that I can submit eco-actions and track progress on the go.

#### Acceptance Criteria

1. WHEN a user accesses Verdleaf on a mobile device, THE system SHALL render a responsive interface optimized for touch interaction
2. WHEN using mobile camera, THE system SHALL allow direct photo capture for eco-action submission
3. WHEN viewing the dashboard on mobile, THE system SHALL adapt visualizations to smaller screen sizes while maintaining readability
4. WHEN interacting with wallet on mobile, THE system SHALL integrate with Phantom mobile app for seamless authentication
5. THE system SHALL ensure all animations and transitions perform smoothly on mobile devices with varying capabilities

### Requirement 12

**User Story:** As a user concerned about data privacy, I want my personal information and eco-actions to be stored securely with transparent data practices, so that I can trust the platform with my information.

#### Acceptance Criteria

1. WHEN a user creates an account, THE system SHALL encrypt sensitive personal information using industry-standard encryption
2. WHEN storing eco-action images, THE system SHALL allow users to choose between public and private visibility
3. WHEN processing images with AI, THE system SHALL not retain images longer than necessary for verification
4. THE system SHALL provide a privacy policy clearly explaining data collection, usage, and retention practices
5. WHEN a user requests data deletion, THE system SHALL remove all personal information while preserving anonymized impact statistics
