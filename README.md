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
| Services | `services.html` | Includes the monthly Market Report|
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

## Google Analytics

Every page is tagged with **Google Analytics 4**. The standard `gtag.js` snippet sits at the top of each page's `<head>`:

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-38BRF7Z8TE"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag() { dataLayer.push(arguments); }
  gtag('js', new Date());
  gtag('config', 'G-38BRF7Z8TE');
</script>
```

Page views, traffic sources and visitor behaviour are reported in the linked Google Analytics property. The privacy policy mentions Google Analytics.


## Contact form

The form on `contact.html` posts to [Formspree](https://formspree.io), which emails the submissions.

## Repo layout

```
index.html, about.html, services.html,
properties.html, contact.html,
privacy-policy.html, terms-conditions.html     the pages
assets/
  css/main.css      site styles
  js/main.js        site scripts
  img/              photos, logos and graphics used on the pages
  vendor/           third-party libraries (Bootstrap, AOS, Swiper, etc.)
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
