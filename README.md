# Back to Nature Tours: static assets

The stylesheet and logo file for the live Webflow site at [backtonaturetours.co.nz](https://backtonaturetours.co.nz), served from this repo through the jsDelivr CDN.

Keeping these files on GitHub, with jsDelivr in front, means the live site does not depend on any single free hosting account.

## Files

- `styles.css`: the site stylesheet (colours, type, layout, components and responsive rules), including rules that target Webflow's generated markup.
- `assets/logo-mark.png`: the logo mark used in the site navigation (512 x 512 PNG).

## Using the files

jsDelivr serves each git tag as a fixed, long-cached version, so pin the links to a tag. `v1.1.0` contains both files. `v1.0.0` contains the stylesheet only; its `styles.css` is identical to the one in `v1.1.0`.

Stylesheet, added in Webflow under Site Settings > Custom Code > Head code:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/dwatces/back-to-nature-assets@v1.1.0/styles.css">
```

Logo:

```
https://cdn.jsdelivr.net/gh/dwatces/back-to-nature-assets@v1.1.0/assets/logo-mark.png
```

## Updating

1. Edit the files, then commit and push to `main`.
2. Tag a new version and push the tag:
   ```bash
   git tag v1.2.0 && git push origin v1.2.0
   ```
3. Change the version in the Webflow links to the new tag, then publish the site in Webflow.

To follow `main` instead of a tag, use `@main` in the links and purge the jsDelivr cache after each push, for example `https://purge.jsdelivr.net/gh/dwatces/back-to-nature-assets@main/styles.css`.

## Author

Built by Daniel Olliver. More of my work: [danielolliver.com/dev](https://danielolliver.com/dev/).

I also run [Olliver Web](https://olliverweb.co.nz), a web design and development studio in Auckland.
