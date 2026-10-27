# palakdebpatra.com

This repository publishes Palak Deb Patra's portfolio at **[palakdebpatra.com](https://palakdebpatra.com/)**. The portfolio's source code lives in [`CaptainBlue793/DevDen`](https://github.com/CaptainBlue793/DevDen); this repository contains the GitHub Pages deployment workflow.

## How publishing works

1. A push to `DevDen/main` runs its checks and dispatches this repository's `deploy.yml` workflow using the `MAIN_SITE_DISPATCH_TOKEN` secret.
2. The workflow checks out `DevDen/main`, installs dependencies, runs lint, builds with Vite's `/` base path, and deploys `dist/` to GitHub Pages.
3. GitHub Pages serves the result at the custom domain `palakdebpatra.com`. The workflow can also be run manually from this repository's **Actions** tab.

To edit the portfolio, make changes in [DevDen](https://github.com/CaptainBlue793/DevDen), not here. If an update does not appear, check the Actions runs in both repositories. See [DevDen's deployment notes](https://github.com/CaptainBlue793/DevDen/blob/main/docs/deployment.md) for build details.

## Projects and email

Other GitHub Pages projects can use paths under the same domain. [Engineering Atlas](https://palakdebpatra.com/palak-engineering-atlas/) is published at `/palak-engineering-atlas/`. Each project uses its own repository and leaves its GitHub Pages **Custom domain** field empty.

Engineering Atlas uses a separate Cloudflare Worker for accounts and Resend to send sign-in codes from `login@palakdebpatra.com`. That sender is not a receiving inbox. The portfolio's contact link goes to `palakdevpatra@gmail.com`.

Cloudflare DNS holds the GitHub Pages records, GitHub domain verification record, and email authentication records. Keep those records when adding a new project path.
