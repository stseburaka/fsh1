# FSH1 website migration

## Context

- FSH1 owns the website and the domains `fsh1.org` and `www.fsh1.org`. The user is helping with the migration and is not the website owner.
- The existing website is built and published with Figma Sites at `www.fsh1.org`.
- The user's Figma Professional subscription ends on September 30, 2026. According to the project context, the current publication will stop working afterward, so the website needs a new hosting arrangement.
- The website is small: text/About content and a collection of photographs.
- The destination is a standalone static website hosted for free on GitHub Pages, initially in a separate public repository on the user's personal GitHub account.
- The repository may later be transferred to the website owners.
- Connecting `fsh1.org` and `www.fsh1.org` is a later step.

## Working rules

- Communicate with the user in Russian.
- Keep code, variable names, filenames, commit messages, and other technical identifiers in English.
- Reproduce the existing design; do not redesign the website. Preserve its content, visual appearance, and behavior as closely as possible.
- Support responsive layouts based on the existing website and supplied design references.
- Use a static architecture with no backend. Minimize dependencies and ongoing maintenance.
- Optimize photographs for the web without noticeable quality loss. Keep supplied originals intact and create separate optimized assets when needed.
- Do not publish, deploy, push content to a public repository, or change DNS without the user's explicit instruction. Do not enable GitHub Pages or connect custom domains without that instruction.
- Do not modify files or configuration outside this project directory. Keep generated files and project-specific tooling within this directory.
- Do not assume permission to use other hosting platforms. GitHub Pages is the agreed hosting target.

## Current stage

- Implementation is authorized and the static HTML/CSS scaffold is in place.
- Do not publish, push, enable GitHub Pages, connect custom domains, or change DNS. Local verification and preparation are authorized; external release is not.
- The supplied Figma transition file is readable through the connected Figma tools for metadata and design context. Use it together with the production site as the reference for structure, responsive dimensions, and asset order; do not use temporary Figma-hosted image URLs in production.
- `inbox/` contains user-supplied originals. Never edit those files in place. Copy and process them into `public/assets/`.

## Proposed technical baseline

- Prefer plain HTML, CSS, and only the vanilla JavaScript required to preserve existing interactions.
- Avoid a framework, package manager, or build pipeline unless inspection of the source website establishes a concrete need.
- Use relative asset paths so the site can work under a GitHub Pages repository path and later on a custom domain.
- The current site uses two static pages: `public/index.html` for Belarusian and `public/en/index.html` for English. Shared styles and local font subsets are in `public/assets/`.
- The photographic slots and their production aspect ratios are recorded in `docs/assets-manifest.json`. The current derivatives are in `public/assets/photos/` and were generated from the supplied originals in `inbox/photos/`.
