# AutoCrypt

**AutoCrypt** is a Bitcoin blockchain forensics tool that lets you trace the flow of funds across the network. Enter any Bitcoin address or transaction ID and AutoCrypt fetches the on-chain data live, then renders it as an interactive force-directed graph — so you can visually follow money as it moves between wallets, and click any node to keep tracing further down the chain.

🔗 **Live demo:** _add your GitHub Pages link here once deployed (see below)_

![Stack](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![Stack](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)
![Stack](https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white)
![Stack](https://img.shields.io/badge/TailwindCSS-3-06B6D4?logo=tailwindcss&logoColor=white)

## Features

- 🔍 **Address & transaction lookup** — search by a Bitcoin address or a raw 64-character transaction hash
- 🕸️ **Interactive transaction graph** — a D3-powered force-directed graph showing inputs, outputs, and value flow between addresses
- 🖱️ **Click-to-trace** — click any node in the graph to jump to that address and continue tracing the fund flow
- 📊 **Transaction details panel** — a readable breakdown of inputs/outputs and BTC values for the selected address or transaction
- ⚡ **Live blockchain data** — pulled directly from the [blockchain.info](https://www.blockchain.com/explorer/api) public API, no backend required

## Tech Stack

- **React 18** + **TypeScript** + **Vite**
- **Tailwind CSS** + **shadcn/ui** components
- **D3.js** for the transaction graph visualization
- **TanStack Query**, **React Router**, **React Hook Form** + **Zod**

## Getting Started (Run Locally)

**Prerequisites:** [Node.js](https://nodejs.org/) 18+ and npm (or an equivalent package manager).

```bash
# 1. Clone the repository
git clone https://github.com/Adhyan-25/autocrypt.git
cd autocrypt

# 2. Install dependencies
npm install

# 3. Start the dev server
npm run dev
```

The app will be running at **http://localhost:8080**.

### Other useful scripts

| Command           | Description                              |
|--------------------|------------------------------------------|
| `npm run dev`       | Start the local development server       |
| `npm run build`     | Build an optimized production bundle to `dist/` |
| `npm run preview`   | Preview the production build locally     |
| `npm run lint`      | Run ESLint over the project              |

## Try It Out

Once it's running, search for any of these to see it in action:

- `1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa` — Satoshi's genesis address
- `bc1qxy2kgdygjrsqtzq2n0yrf2493p83kkfjhx0wlh` — a modern SegWit (bech32) address
- Any 64-character transaction hash from a [block explorer](https://www.blockchain.com/explorer)

## Deploying to GitHub Pages

This repo ships with a GitHub Actions workflow (`.github/workflows/deploy.yml`) that automatically builds and deploys the site to GitHub Pages on every push to `main`. To turn it on:

1. Push this repo to GitHub (if you haven't already).
2. Go to **Settings → Pages** in your GitHub repo.
3. Under **Build and deployment → Source**, select **GitHub Actions**.
4. Push to `main` (or re-run the workflow from the **Actions** tab) — the site will build and deploy automatically.
5. Your live URL will be `https://<your-username>.github.io/autocrypt/`.

You can watch the deployment progress under the **Actions** tab of your repository.

## Project Structure

```
src/
├── api/            # Blockchain.info API client, data parsing & validation
├── components/      # Header, Footer, AddressSearch, TransactionGraph, TransactionDetails
├── components/ui/   # shadcn/ui primitives (buttons, inputs, dialogs, etc.)
├── pages/           # Route-level pages (Home, About, 404)
├── hooks/           # Shared React hooks
└── lib/             # Utility functions
```

## How It Works

1. You enter a Bitcoin address or transaction hash.
2. The input is validated and classified as either an address or a transaction (`src/api/bitcoinAPI.ts`).
3. AutoCrypt fetches the corresponding raw data from the blockchain.info API.
4. The response is parsed into a normalized set of inputs/outputs, then converted into a graph structure (`nodes` + `links`) representing the flow of BTC.
5. D3.js renders the graph as an interactive, force-directed layout inside `TransactionGraph.tsx`.
6. Clicking any node re-runs the trace starting from that address, so you can follow the money as far as you like.

## Notes

- This project relies on the free, public blockchain.info API, which is rate-limited — if lookups start failing, wait a moment before retrying.
- No API keys, environment variables, or backend server are required; everything runs client-side.

## License

This project is available for personal and educational use. Feel free to fork it and build on top of it.
