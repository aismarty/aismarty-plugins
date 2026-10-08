---
name: install-widget
description: Add the AI Smarty widget snippet to the website code in the current project and verify it after deploy. Use when the user wants the AI agent installed on their site from a code project.
---

# Install the widget in this codebase

1. Call `list_agents` if the agent is not known, then `get_agent` and read the install snippet. Use that snippet exactly. Do not alter or invent it.
2. Detect the framework from the project files and find the layout or footer file:
   - Next.js: `app/layout.tsx` or `src/app/layout.tsx`, or `pages/_document.tsx`
   - Astro: the main file in `src/layouts`
   - Nuxt: `app.vue` or a file in `layouts`
   - SvelteKit: `src/app.html`
   - Plain HTML: the shared footer, or each page if there is none
   - WordPress theme: `footer.php`
   - Shopify theme: `layout/theme.liquid`
   - Other: ask the user which file renders on every page.
3. Search the project for the snippet first. If it is already present, say so and stop. Never add it twice.
4. Insert the script once, just before the closing `</body>` tag (or the framework's equivalent, such as a script component in the root layout).
5. Show the diff and wait for the user to confirm. Do not run deploy commands.
6. After the user deploys, ask for a live page address on the site and call `check_widget_installed` with it. Report the result as returned. If the widget is not found or the domain is not allowed, explain which and what to check.

The agent must be published to be live for visitors. Use `publish_agent` only after the user confirms.
