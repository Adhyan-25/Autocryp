# AutoCrypt

> **Release status: incomplete source snapshot.** The current `main` branch does not contain the `src/` application tree or the `src/main.tsx` entry point referenced by `index.html`. As checked in, the project is not buildable or ready for deployment. Restore the application source before treating the features below as a runnable release.

**AutoCrypt** is intended to be a Bitcoin blockchain forensics tool for tracing the flow of funds across the network. The planned experience lets users enter a Bitcoin address or transaction ID and explore transaction flow in an interactive graph.

![Stack](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![Stack](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript)
![Stack](https://img.shields.io/badge/Vite-5-646CFF?logo=vite)
![Stack](https://img.shields.io/badge/TailwindCSS-3-06B6D4?logo=tailwindcss)

## Intended features

- Address and transaction lookup
- Interactive D3-powered transaction graph
- Click-to-trace address exploration
- Transaction details for inputs, outputs, and BTC values
- Live blockchain data via the public Blockchain.com API

These features are documented as the project goal; they have not been verified against the incomplete source snapshot currently committed to `main`.

## Intended tech stack

- React 18, TypeScript, Vite
- Tailwind CSS and shadcn/ui
- D3.js for transaction graph visualization
- TanStack Query, React Router, React Hook Form, and Zod

## Run locally

After restoring the missing `src/` application files:

```bash
npm ci
npm run dev
```

To verify a production build:

```bash
npm run build
npm run lint
```

The project uses Vite. The CI workflow runs the Vite build and lint commands; the checks will remain unsuccessful until the missing application source is restored.

## Notes

- The intended implementation uses the free public Blockchain.com API, which may be rate-limited.
- Do not commit credentials, environment files, generated database snapshots, or other local data.

## License

This repository currently states personal and educational use in its project history. Add a formal license file if you want to define redistribution and reuse permissions clearly.
