# Charlene In The City

Website for **Charlene In The City** ([charleneinthecity.ca](https://charleneinthecity.ca)), a Toronto real estate agent. It's a static site (plain HTML, CSS and JavaScript, no build step) built on the [EstateAgency](https://bootstrapmade.com/real-estate-agency-bootstrap-template/) Bootstrap template from BootstrapMade.

The site has two parts that work together:

1. **This repo**: the static pages, which hold the marketing content, the market report, the contact form and the analytics tag.
2. **A separate WordPress site**: it runs the listings and is embedded into the Properties page (see [Listings](#listings-idx-automation)).

## Pages

| Page | File | Notes |
| --- | --- | --- |
| Home | `index.html` | Hero, neighbourhood highlights, "View Listings" button |
| About | `about.html` | |
| Services | `services.html` | Includes the monthly **Market Report** (see below) |
| Properties | `properties.html` | Embeds the live listings |
| Contact | `contact.html` | Contact form and map |
| Privacy policy | `privacy-policy.html` | |
| Terms and conditions | `terms-conditions.html` | Includes the TRREB and CREA disclaimers |

## Listings (IDX automation)

Listings are not stored in this repo. They come from a separate **WordPress** site hosted on Bluehost, which uses the **RealtyPress** plugin to pull MLS® listings in through IDX and keep them up to date automatically. No manual listing entry is needed.

`properties.html` displays that site in a full-width iframe:

```html
<iframe src="https://rfp.htc.mybluehost.me/listings/" ...></iframe>
```

Things to know:

- To change how listings look, what's shown or how they're filtered, edit the WordPress site (RealtyPress settings and templates). Editing this repo won't change them.
- The iframe points at Bluehost's temporary domain (`rfp.htc.mybluehost.me`). If that site is moved to a permanent domain or the temporary address changes, update the `src` in `properties.html` or the Properties page will go blank.
- MLS® data is subject to TRREB and CREA rules. The required disclaimers live on the Terms and conditions page and in the footers of the other pages. Keep them in place.

## Google Analytics

Every page is tagged with **Google Analytics 4** (measurement ID `G-38BRF7Z8TE`). The standard `gtag.js` snippet sits at the top of each page's `<head>`:

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-38BRF7Z8TE"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag() { dataLayer.push(arguments); }
  gtag('js', new Date());
  gtag('config', 'G-38BRF7Z8TE');
</script>
```

Page views, traffic sources and visitor behaviour are reported in the linked Google Analytics property. When you add a new page, copy this snippet into its `<head>` so it's tracked too. The privacy policy mentions Google Analytics.

## Monthly market report

The "RLP Signature TRREB Stats" section on the Services page is plain HTML, updated by hand each month. To update it, open `services.html`, find the `Market Report` heading, and replace the title (for example "October 2026") and the bullet points with the latest report.

## Contact form

The form on `contact.html` posts to [Formspree](https://formspree.io), which emails the submissions. To change where they go, update the form's endpoint or the recipient in the Formspree dashboard.

`forms/contact.php` is a leftover stub from the template and isn't used. It also depends on the template's paid PHP mailer library, which isn't included.

## Repo layout

```
index.html, about.html, services.html,
properties.html, contact.html,
privacy-policy.html, terms-conditions.html     the pages
assets/
  css/main.css      site styles
  js/main.js        site scripts
  img/              photos, logos and graphics
  vendor/           third-party libraries (Bootstrap, AOS, Swiper, etc.)
forms/              unused template contact form stub
CNAME               custom domain (charleneinthecity.ca)
```

## Running locally

No install needed. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

The listings iframe, analytics, fonts and contact form need an internet connection.

## Credits

Template: EstateAgency by [BootstrapMade](https://bootstrapmade.com/). Follow the template's license terms, including attribution, when publishing.
