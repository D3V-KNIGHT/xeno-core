# ADR-001: Xeno Core Web Platform Architecture

- **Status:** Accepted
- **Decision date:** 2026-09-02
- **Project:** Xeno Core
- **Domain:** xenocoredigital.com

## Context

Xeno Core begins as a robotics engineering portfolio and technical publishing platform. It must also support future growth into a professional robotics, AI, and autonomous-systems business.

The platform requires:

- Strong performance and SEO
- Low operating cost
- Git-based deployment
- Markdown-based technical publishing
- Secure infrastructure
- Full ownership of code and content
- Minimal vendor lock-in
- Future support for services, products, documentation, and applications

## Decision

Xeno Core will use the following architecture:

| Layer | Decision |
|---|---|
| Framework | Astro |
| Language | TypeScript |
| Content | Markdown and MDX |
| Content organization | Astro Content Collections |
| Styling | Native CSS |
| Interactive components | Astro Islands |
| Optional UI framework | React only when justified |
| Rendering | Static generation by default |
| Repository | GitHub |
| Production branch | `main` |
| Hosting | Cloudflare Workers Static Assets |
| CI/CD | Cloudflare Git-based builds |
| DNS | Cloudflare authoritative DNS |
| TLS | Cloudflare Universal SSL |
| Registrar | GoDaddy |
| Backend | Cloudflare Workers APIs when required |
| Large media | Cloudflare R2 or external video hosting when required |

## Rationale

Astro is optimized for content-focused websites and produces lightweight static HTML by default. Xeno Core’s primary content—projects, articles, diagrams, research, and documentation—does not require a browser-heavy application framework.

Markdown and MDX provide a maintainable technical-writing workflow. Astro Content Collections will provide schemas and type-safe metadata for projects, articles, and research.

Cloudflare provides DNS, TLS, edge delivery, static hosting, and a future serverless path within one infrastructure layer. The domain will remain registered at GoDaddy.

## Architectural Principle

> Static by default. Dynamic only when required.

Interactive JavaScript, APIs, databases, and application frameworks will be introduced only when a concrete requirement justifies them.

## Consequences

### Benefits

- Fast page delivery
- Small browser-side JavaScript footprint
- Strong SEO foundation
- Low hosting cost
- Reduced attack surface
- Portable Markdown content
- Git-based change history and deployment
- Clear growth path for future business services

### Tradeoffs

- Content changes require a Git commit and deployment
- Dynamic features require separate implementation
- Cloudflare-specific services may introduce some infrastructure dependency
- Contributors must understand Git and the project’s content schemas

## Alternatives Considered

### Next.js

Not selected for the primary website because Xeno Core does not currently require an application-oriented React framework, server rendering, authentication, or complex state management.

A future application may use Next.js at a separate hostname such as `app.xenocoredigital.com`.

### React Without a Framework

Not selected because React alone does not provide the complete routing, content, build, metadata, and static-generation architecture required by the project.

### WordPress and Hosted Site Builders

Not selected because they introduce unnecessary runtime complexity, maintenance requirements, or platform lock-in while providing less direct control over the engineering workflow.

### Vercel and Netlify

Both are viable hosting platforms, but Cloudflare was selected to unify DNS, TLS, CDN, static hosting, and future edge services.

## Future Boundaries

The public company and engineering site will remain separate from future applications where practical:

- `xenocoredigital.com` — corporate, portfolio, projects, articles, and research
- `app.xenocoredigital.com` — future web applications
- `docs.xenocoredigital.com` — future product documentation
- `api.xenocoredigital.com` — future APIs

## Review Triggers

This decision should be reviewed if Xeno Core requires:

- Extensive authenticated functionality
- Complex transactional workflows
- Real-time application state
- A large editorial team requiring a CMS
- Infrastructure that Cloudflare cannot reasonably support
