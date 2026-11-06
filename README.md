# Yu-Gi-Oh! Card Poll

A browser-based community poll for choosing Yu-Gi-Oh! cards.

## Website

The site is deployed with GitHub Pages from the `main` branch using the workflow in `.github/workflows/deploy.yml`.

## Development

The current site is plain HTML, CSS, and JavaScript, so no build step is required. Edit `index.html`; pushing a change to `main` triggers a new deployment.

## Planned functionality

- Search the Yu-Gi-Oh! card database with autocomplete.
- Hide cards that have already been selected.
- Allow each visitor to submit one or more cards without creating an account.
- Store submissions in a small hosted database (to be configured).
