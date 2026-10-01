# BChat website

The public website for [BChat](https://bchat-five.vercel.app), the group chat app for UCLA classes: landing page, Privacy Policy and Terms of Service.

Plain HTML and CSS, no build step. **Every merge to `main` deploys automatically** to Vercel, and every pull request gets its own preview link.

```
index.html            landing page
privacy.html          generated from legal/privacy-policy.md, don't edit by hand
terms.html            generated from legal/terms-of-service.md, don't edit by hand
css/styles.css        design tokens match the app's client/context/ThemeContext.tsx
assets/               logo, favicons, app screenshots
legal/*.md            copies of docs/legal/*.md from the app repo
scripts/build-legal.mjs
```

## Making changes

1. Branch off `main`, edit, and preview locally:
   ```bash
   npm run dev     # http://localhost:8090
   ```
2. Open a pull request. Vercel comments a preview link on it.
3. Merge. The site updates within about a minute.

## Updating the legal pages

The Terms of Service and Privacy Policy are written in the **app repo** ([dylanttang/BruinChat](https://github.com/dylanttang/BruinChat), `docs/legal/`), because the app shows the same text. When they change there:

1. Copy `docs/legal/privacy-policy.md` and `docs/legal/terms-of-service.md` into `legal/` here.
2. Run `npm run legal` to regenerate `privacy.html` and `terms.html`.
3. Open a PR with all four files.

## Notes

- The App Store listing and the Google OAuth consent screen link to `/privacy.html` and `/`, so keep those paths.
- The hero chat is HTML styled like the app's chat screen. Screenshots in `assets/screens/` come from the iOS simulator in light mode; retake them when those screens change.
- Light and dark mode follow the visitor's system setting.
- Don't use "Bruin" (a UCLA trademark) or Apple's logo. Use the official App Store badge once there's a store link.
