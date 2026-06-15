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

The app is a static SPA served via [Cloudflare Workers static assets](https://developers.cloudflare.com/workers/static-assets/). Config lives in `frontend/wrangler.jsonc`.

Run the commands below in the `/frontend` folder.

1. Authenticate Wrangler with your Cloudflare account (one-time):

```bash
bunx wrangler login
```

2. Build and deploy:

```bash
bun run deploy
```

This runs `vite build` and then `wrangler deploy`, uploading the `dist/` output. To preview the production build locally on the Workers runtime, run `bun run cf:dev`.

> CI / non-interactive deploys: set `CLOUDFLARE_API_TOKEN` (and `CLOUDFLARE_ACCOUNT_ID`) env vars instead of `wrangler login`.

## Demo

Check it out here at [gittok.vercel.app](https://gittok.vercel.app)

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes and commit them

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
