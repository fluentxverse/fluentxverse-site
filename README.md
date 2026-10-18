# FluentXVerse Site

The public website for FluentXVerse, an online English tutoring platform with learner, tutor, and operations applications. It explains the product, educational approach, and privacy technology, and links visitors to the appropriate application.

Production entry points: https://fluentxverse.com and https://www.fluentxverse.com

## Scope

- Product and ecosystem overview, company information, and contact details.
- Dedicated AI, onchain technology, and privacy explanations.
- Links to student and tutor applications.
- Responsive layouts, locally served artwork, and search/social metadata.

## Architecture

SolidJS, Solid Router, TypeScript, and Vite. Cloudflare Workers serves static assets with single-page application routing. This site does not hold wallet keys, authenticate students, or execute marketplace transactions.

All site source is under `fluentxverse-site/`:

- `src/data/site.ts`: product descriptions, portal links, and team content.
- `src/pages/`: public pages, including AI and onchain explanations.
- `src/styles/`: styling and responsive behavior.
- `public/assets/`: artwork and public assets.
- `docs/`: content references and image provenance notes.

## Local Development

Use Node.js 22+, npm, and Bun. From the repository root:

```bash
npm run setup
npm run dev
npm run build
npm run preview
```

Use the development URL printed by Vite. No API credentials are required. Update approved product/team content in `src/data/site.ts`, and preserve asset attribution when replacing imagery.

## Deployment and Claims

The build produces `fluentxverse-site/dist/`. `wrangler.toml` declares the existing apex and `www` domains. CI builds source only; review domain ownership and routing before manual deployment. Do not use a catch-all asset rewrite that serves HTML for JavaScript or CSS requests.

Technology pages should distinguish implemented application behavior, deployment evidence, testnet work, and proposed features. Publishing a roadmap does not establish mainnet activation, an independent cryptographic audit, grant approval, regulatory compliance, or confidentiality of ordinary token transfers.

## Repository Provenance

This repository is an app-focused export of [the FluentXVerse monorepo](https://github.com/fluentxverse/fluentxverse-monorepo). The monorepo remains the source of truth; submit cross-application changes there. Existing directory names are retained so shared imports remain valid. The historical student/tutor folder suffix does not indicate a Preact app: both active web clients use SolidJS.

Exported source commit: [`c9696e491149`](https://github.com/fluentxverse/fluentxverse-monorepo/tree/c9696e491149275bc01df3b8d05d29a15263257a). See [SOURCE.json](SOURCE.json) for the exact scope. Local uncommitted edits, environment files, runtime data, curriculum backups, and generated proving artifacts are not published. Original Git history is not copied.

Cross-app parity tests and full deployment orchestration remain in the monorepo. The checks in this repository do not establish production acceptance, security audit completion, or proof-system review. No production deployment is triggered by this export.

## Security and Licensing

Never commit API tokens, seed phrases, private keys, student records, recordings, or real assessment evidence. Use synthetic fixtures in tests. Report security issues privately to hello@fluentxverse.com rather than opening an issue containing sensitive data.

No root license file was present in the source revision. Public source availability, if enabled, is not itself a license grant. Contact FluentXVerse for licensing terms; third-party dependencies retain their own licenses.
