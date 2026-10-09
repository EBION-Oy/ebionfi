# EBION Oy

A small, responsive business website made with plain HTML, CSS, and SVG. No build step, dependencies, externally loaded fonts, analytics, or client-side JavaScript.

## Preview

Run from this directory:

```sh
python3 -m http.server 8000
```

Visit http://localhost:8000. You can also open `index.html` directly in a browser.

## Content

- `index.html`: all site copy, navigation, services, contact, and privacy information.
- `styles.css`: colors, typography, and responsive layouts.
- `assets/favicon.svg`: brand icon.

The public contact email is `info@ebion.fi`. The contact link opens the visitor’s email application.

Add EBION Oy’s confirmed Business ID and business address to the footer or a company information section. Confirm the service descriptions match the services you offer. Finnish service-provider information requirements are outlined in [Finlex, Act on the Provision of Services, section 7](https://www.finlex.fi/fi/lainsaadanto/2009/1166). These company details have deliberately not been invented.

## GitHub Pages

1. Push these files to your GitHub repository.
2. Open **Settings → Pages**.
3. Set the source to **Deploy from a branch**, select your publishing branch (usually `main`), and choose **/(root)**.
4. Save. GitHub will publish the website; `.nojekyll` keeps it a plain static site.

All local asset URLs are relative, so the site works at a repository URL such as `username.github.io/repository/` and at the root of your custom domain.

## Custom domain

The site uses `https://ebion.fi/`. The root `CNAME` file contains `ebion.fi`, and the HTML includes canonical and Open Graph URLs for this domain.

1. Verify `ebion.fi` in your GitHub account settings.
2. In the repository’s **Settings → Pages → Custom domain**, confirm `ebion.fi` and save. Keep the included `CNAME` file in the publishing branch.
3. Configure DNS at your domain provider. For `ebion.fi`, add the following `A` records at `@`:

   ```text
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   For `www`, add a DNS `CNAME` record pointing to `YOUR_GITHUB_USERNAME.github.io` (without the repository name). GitHub can redirect between the root domain and `www` when both are configured.

4. After the DNS check succeeds and a certificate is available, enable **Enforce HTTPS**.

See [GitHub’s custom-domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) for current setup instructions and DNS values.

## Privacy and accessibility

The site itself does not collect visitor data or set cookies. The footer explains the hosting provider’s role and links to GitHub’s privacy statement. No consent banner is added because no optional tracking is used; [Traficom’s cookie guidance](https://www.kyberturvallisuuskeskus.fi/en/our-activities/regulation-and-supervision/cookies) explains consent requirements. If you add analytics, forms, embeds, or other data collection, review the privacy information and consent requirements for that implementation.

The layout includes semantic landmarks, heading hierarchy, a skip link, keyboard focus indicators, decorative SVGs hidden from assistive technology, and reduced-motion support. Review any new content and integrations for accessibility before publishing.
