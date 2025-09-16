![Alt text](https://pbs.twimg.com/media/GzQ5lOFWsAAC1mc?format=jpg&name=large)

# Anoma X (formally Twitter) contributions
# 1. Medium

link to contributions 

[[https://sites.google.com/view/apexcohort/contribution-page]

# 2. ANOMA Simulated Decentralized Autonomous Service Marketplace

ANOMA-Simulated-Decentralized-Autonomous-Service-Marketplace

Anoma Intent-Centric Service Marketplace (Simulation Demo)

This project is a simulation of a decentralized autonomous service marketplace built on Anoma’s intent centric architecture.

Instead of traditional job boards or platforms (like Fiverr/Upwork), users publish intents such as:

“I want video editing services at $50/hour, delivered within 24 hours.”

Solvers continuously monitor and match these service intents with providers who can fulfill them. Once matched, agreements are executed with privacy, escrow, and automated settlement.

This demo shows how a service economy can be coordinated on Anoma’s model using simulated tokens, providers, and contracts.

Features
	•	Daily Faucet → every user receives 10,000 $XAN + 5,000 USDC test tokens.
	•	Seeded Service Listings → categories like design, video editing, compute rental, tutoring, content writing.
	•	Intent Submission Flow → clients publish service requests, providers publish offers.
	•	Solver Simulation → matches client + provider intents based on price, time, and reputation.
	•	Escrowed Payments → funds locked until service delivery confirmed.
	•	Feedback & Reputation → simple score system tracked per user.
	•	In-Memory DB → lightweight for experimentation (upgrade to Postgres later).

🛠 Tech Stack

🔷 Backend: Node.js, Express, body-parser, uuid, CORS

🔷 Data: in-memory store (planned: Postgres)

🔷 Auth: placeholder for Twitter/Discord OAuth (?user=twitter:alice)

🔷 Solver Engine: basic auto-matcher (expandable into bonded solver economy)

 # 1. Clone repo
git clone (https://github.com/Iamgetty/Iamgetty-Anoma)
cd anoma-service-market

# 2. Install dependencies
npm install

# 3. Run server
npm run start

🔗 API Endpoints

Faucet
GET /api/faucet?user=twitter:alice
Claims daily balance: 10k XAN + 5k USDC.

Get Services
GET /api/services
Lists all seeded service categories (design, compute, tutoring, etc).

Submit Intent (Client)
POST /api/intents/request

{ 
  "service_id": "video_editing", 
  "description": "Edit 2-min promo clip", 
  "budget": "200", 
  "currency": "USDC", 
  "deadline": "24h", 
  "client_pub": "twitter:alice" 
}

Submit Intent (Provider)
POST /api/intents/offer

{ 
  "service_id": "video_editing", 
  "rate": "50/hour", 
  "currency": "USDC", 
  "availability": "24h", 
  "provider_pub": "twitter:bob" 
}

Solver Match
Auto-runs every 2s: matches compatible request + offer, locks funds in escrow.

Confirm Delivery (Client)
POST /api/delivery/confirm
Releases escrow to provider, updates reputation scores.

Get Balance
GET /api/balance?user=twitter:alice

Example Flow
	1.	Alice (client) claims faucet.
	2.	Bob (provider) claims faucet.
	3.	Alice submits an intent requesting “video editing for 200 USDC, 24h.”
	4.	Bob submits an intent offering “video editing @ 50/hour, available now.”
	5.	Solver auto-matches → escrow locks funds.
	6.	Bob delivers work (simulated).
	7.	Alice confirms delivery → escrow pays Bob, both reputations updated.

Roadmap
	•	Add frontend (Next.js) for service listings & request forms.
	•	Integrate Twitter/Discord OAuth.
	•	Persist data with Postgres.
	•	Expand solver logic with bonding, arbitration, and multi-party contracts.
	•	Connect to Anoma testnet via intent adapters.
	•	Add NFT badges & leaderboards for top providers.
	•	Layer in ZK proofs for privacy-preserving reputation.

Vision

This repo isn’t just a demo it’s a sandbox for exploring how gig economies and freelance platforms could run in a decentralized way.

By simulating the intent → match → escrow → delivery → feedback pipeline, we can prototype how service marketplaces will look on Anoma’s intent-centric, privacy first infrastructure.

Think of it as Fiverr without middlemen, powered by solvers and smart contracts.

Contributions Welcome

Forks, pull requests, and experiments encouraged. Let’s co-create the future of decentralized work.

![Alt text](https://anoma.net/_next/static/media/learn-the-intent-machine.2c7611f2.png)
Gnoma
