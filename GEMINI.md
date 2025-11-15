# GEMINI.md

## Project Overview

This project, "unduckified," is a web application that provides a faster, client-side alternative to DuckDuckGo's "bangs" feature. It's a fork of the original "unduck" project, with added features like dark mode, settings for customization, local search history, and Progressive Web App (PWA) capabilities.

The application is built using TypeScript and Vite. It works by intercepting search queries, identifying bang commands (e.g., `!g` for Google), and then redirecting the user to the appropriate search results page on the target site. All of this is done in the user's browser, which makes it significantly faster than DuckDuckGo's server-side approach.

## Building and Running

The project uses `bun` as the package manager. The following scripts are defined in `package.json`:

*   **`bun run dev`**: Starts the development server with Vite.
*   **`bun run build`**: Builds the application for production.
*   **`bun run preview`**: Previews the production build locally.
*   **`bun run hash`**: Generates the `src/bangs/hashbang.ts` file from the bang data.

### Development

To run the project in a development environment, you would typically run:

```bash
bun install
bun run dev
```

### Production

To build the project for production, you would run:

```bash
bun install
bun run build
```

## Development Conventions

*   **Package Manager**: The project uses `bun` for package management. This is indicated by the presence of a `bun.lock` file.
*   **Build Tool**: `vite` is used for building and serving the application.
*   **Language**: The project is written in TypeScript.
*   **Code Style**: The project uses `prettier` for code formatting, as indicated by the `.prettierrc` file. It also uses `biome` for linting, as indicated by the `biome.json` file.
*   **PWA**: The project is a Progressive Web App, using the `vite-plugin-pwa` plugin.
*   **Bangs Data**: The bang data is stored in a large JSON object in `src/bangs/bangs.json` and then processed into a more efficient hashmap in `src/bangs/hashbang.ts` by the `bun run hash` script.
