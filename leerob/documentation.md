# Documentation

Here's how to build incredible developer documentation:

## 1. Fast

- Pages need to load as fast as possible (prefer static pages).
- Optimize image, font, and script loading.
- Search needs to be extremely fast to load and view results.

## 2. Readable

- Be concise (make every token count).
- Avoid technical jargon and idioms.
- Optimize for skimming (good use of **bold**, ***italic***, lists, headings, images, etc).
- Keep the first-time experience simple and slowly reveal complexity.
- Ensure docs have many code examples you can copy/paste or run.

## 3. Helpful

- Always document workarounds even if it's a product gap.
- Make it easy for readers to leave feedback on docs (e.g. typos).
- Automate checking for broken links on git pushes.
- Create learning material with a structured curriculum.
- For any breaking change, include codemods and migration guides.

## 4. AI-native

Spoiler alert: most docs traffic now comes from AI crawlers.

- Prefer cURL over "click" if possible.
- Prefer prompts over tutorials.
- "Ask AI" sidebar, which can reference your docs pages.

## 5. Agent-ready

- Make it easy to copy/paste content in AI chatbots as Markdown.
- Support viewing pages as Markdown (just add `.md` to the URL).
- Serve Markdown files when `Accept: text/markdown` is requested.
- Serve an `llms.txt` file as a directory of Markdown files.

## 6. Polished

- Buttons should have generous hit areas (especially sidenavs).
- Sidebars should retain scroll position and expanded state.
- Ensure good active/hover states for elements.
- Add dynamic OG images.
- Every heading and section should be linkable with stable anchors.
- Related guides, APIs, and examples should reference and cross-link.
- Add metadata/canonical tags to ensure docs show up cleanly in search.

## 7. Localized

- Don't display `/en` in the URL by default.
- Use server-side routing to serve the correct language.
- Localize static strings and docs content.

## 8. Responsive

- Great mobile menus / Safari iOS support.
- Tooltips on desktop, popovers on mobile.

## 9. Accessible

- Skip nav to the main content.
- Ensure all images have `alt` tags.
- Respect `prefers-reduced-motion` system settings.

## 10. Universal

- Ship docs-as-code for libraries with JSDoc (or as a package).
- Ship your docs as an MCP like Context7.
- Ship your docs in your library `node_modules`.
- Ship rules files (like `AGENTS.md`) with your product.
- Ship evals and recommend specific models for your product.

---

#author: Lee Robinson
#published: January 2025
#source: https://leerob.com/docs
#background: Developer, writer, and educator at Cursor teaching about AI. Previously at Vercel. Known for clear, practical approach to explaining developer concepts and bridging engineering excellence with accessible teaching.
#decade: #2020s
