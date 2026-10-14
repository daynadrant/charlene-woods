# Charlene In The City

A multi-page real estate agent website for **Charlene In The City** ([charleneinthecity.ca](https://charleneinthecity.ca)). It's plain HTML, CSS and JavaScript with no build step, based on the [EstateAgency](https://bootstrapmade.com/real-estate-agency-bootstrap-template/) Bootstrap template from BootstrapMade.

## Pages

| Page | File |
| --- | --- |
| Home | `index.html` |
| About | `about.html` |
| Services | `services.html` |
| Property listings | `properties.html` |
| Single property | `property-single.html` |
| Contact | `contact.html` |
| Privacy policy | `privacy-policy.html` |
| Terms and conditions | `terms-conditions.html` |

`malcolm.html` and `soudan.html` are additional pages, and `floorplan1.jpg` / `floorplan2.jpg` are floor plan images used by the property pages.

## Repo layout

```
assets/
  css/      main stylesheet
  scss/     Sass sources
  js/       site scripts
  img/      photos and graphics
  vendor/   third-party libraries (Bootstrap, etc.)
forms/
  contact.php   contact form handler (see below)
CNAME           custom domain (charleneinthecity.ca)
```

## Running locally

No install needed. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Contact form

`forms/contact.php` is the template's stock handler. It expects the template's paid "PHP Email Form" library at `assets/vendor/php-email-form/php-email-form.php`, which is not included, and its recipient is still the placeholder `contact@example.com`. To make the form send mail, add that library (or replace the script with your own mailer) and set a real receiving address. See `forms/Readme.txt`.

## Credits

Template: EstateAgency by [BootstrapMade](https://bootstrapmade.com/). Follow the template's license terms, including attribution, when publishing.
