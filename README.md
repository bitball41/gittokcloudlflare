# GitTok

A fork of WikiTok to present a TikTok-style interface for exploring random GitHub repos.

## Features

- Vertical scrolling feed of random GitHub repos  uhb
- Repo previews with images, titles and excerpts
- Share repos directly or copy links
- Preloading of images and content for smooth scrolling
- Responsive design that works on mobile and desktop
- Progressive Web App (PWA) support for installing as a standalone app

## Tech Stack

- React 18
- TypeScript
- Tailwind CSS
- Vite

## Development

Run the commands below in the `/frontend` folder.

1. Install dependencies:

```bash
bun install
```

2. Run development server:

```bash
bun run dev
```

No backend required!

## Deploy to Cloudflare Workers

The app is a static SPA served via [Cloudflare Workers static assets](https://developers.cloudflare.com/workers/static-assets/). The deploy config lives in `wrangler.jsonc` at the repo root. Its `build.command` installs deps and runs `vite build` in `frontend/`, then the `frontend/dist/` output is uploaded as static assets with SPA fallback routing.

### Git integration (automatic)

If the repo is connected to a Cloudflare Workers project via [Git integration](https://developers.cloudflare.com/workers/ci-cd/builds/git-integration/), every push builds and deploys automatically using the default deploy command (`npx wrangler deploy`) — no extra build settings required, since the root `wrangler.jsonc` drives the build.

### Manual deploy (from the repo root)

1. Authenticate Wrangler with your Cloudflare account (one-time):

```bash
npx wrangler login
```

2. Build and deploy:

```bash
npx wrangler deploy
```

> CI / non-interactive deploys: set `CLOUDFLARE_API_TOKEN` (and `CLOUDFLARE_ACCOUNT_ID`) env vars instead of `wrangler login`.

## Demo

Check it out here at [gittok.vercel.app](https://gittok.vercel.app)

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes and commit them

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
