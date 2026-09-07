# Xeno Core

**Robotics • AI • Autonomous Systems**

Xeno Core is a robotics engineering portfolio, technical publishing platform, and future robotics/AI engineering company website.

The platform documents practical engineering work involving ROS 2, autonomous systems, computer vision, artificial intelligence, simulation, embedded systems, and physical robot development.

## Project Status

Xeno Core is in early development. The current milestone is establishing the website architecture, development workflow, content system, and production deployment foundation.

- **Domain:** [xenocoredigital.com](https://xenocoredigital.com)
- **Repository:** [D3V-KNIGHT/xeno-core](https://github.com/D3V-KNIGHT/xeno-core)

## Architecture

| Layer | Technology |
|---|---|
| Web framework | Astro |
| Language | TypeScript |
| Content | Markdown and MDX |
| Content management | Astro Content Collections |
| Styling | Native CSS |
| Source control | Git and GitHub |
| Hosting | Cloudflare Workers Static Assets (planned) |
| DNS and TLS | Cloudflare (planned) |
| Rendering | Static generation by default |

The architectural principle is:

> Static by default. Dynamic only when required.

## Local Development

### Prerequisites

- Git
- NVM
- Node.js 24
- npm

### Setup

```bash
git clone git@github.com:D3V-KNIGHT/xeno-core.git
cd xeno-core
nvm install
nvm use
npm ci
npm run dev
```

The local development server will be available at:

```text
http://localhost:4321
```

## Commands

| Command | Purpose |
|---|---|
| `npm run dev` | Start the local development server |
| `npm run build` | Generate the production site |
| `npm run preview` | Preview the production build locally |
| `npm run astro` | Run Astro CLI commands |

## Development Workflow

- `main` represents the production-ready branch.
- Changes are developed on focused branches.
- Commit messages follow Conventional Commits.
- Every change must pass a production build before merging.
- Secrets and credentials must never be committed.

Example branch names:

```text
feature/homepage
feature/project-system
content/humanoid-head
fix/mobile-navigation
chore/repository-foundation
```

## Planned Content

- Engineering projects
- Technical articles
- Research notes
- Robotics demonstrations
- Architecture diagrams
- GitHub repositories
- Videos and images
- Future products and engineering services

## License

No license has been granted at this time. All rights are reserved.
