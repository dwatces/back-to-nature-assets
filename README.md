# Back to Nature Tours — static assets

Durable home for the stylesheet used by the live Webflow site
**https://backtonaturetours.co.nz**.

The site links `styles.css` from this repo via the jsDelivr CDN so production
does not depend on any single free hosting account.

## Live link (paste into Webflow → Site Settings → Custom Code → Head)

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/dwatces/back-to-nature-assets@v1.0.0/styles.css">
```

The `@v1.0.0` tag pins an immutable, permanently-cached version.

## Updating the CSS later

1. Edit `styles.css`, commit, push.
2. Tag a new version and push the tag:
   ```bash
   git tag v1.0.1 && git push origin v1.0.1
   ```
3. Update the `@v1.0.0` in the Webflow `<link>` to the new tag, then **Publish** Webflow.

(Prefer a fixed URL instead of bumping tags? Point the link at `@latest`/`@main`
and purge the cache after each push via `https://purge.jsdelivr.net/gh/dwatces/back-to-nature-assets@main/styles.css`.)
