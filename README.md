# Yu-Gi-Oh! Card Poll

A free, browser-based community poll for choosing Yu-Gi-Oh! cards. Participants do not need an account.

## Website

The site is deployed with GitHub Pages from the `main` branch using the workflow in `.github/workflows/deploy.yml`.

## How it works

- Card-name autocomplete is powered by the YGOPRODeck API.
- Submitted card IDs are loaded from Supabase and hidden from search suggestions.
- Visitors can select and submit multiple cards in one go.
- No participant identity or account is collected.
- The list of submitted cards refreshes periodically while the page is open.

## Supabase setup

The frontend connects directly to the Supabase REST API. It uses the project's URL and publishable key in `index.html`; publishable keys are intended for public client-side use. Never put a Supabase secret or service-role key in this repository.

The database table is `public.card_submissions`, with these columns:

- `id`: generated row ID
- `card_id`: YGOPRODeck card ID
- `card_name`: card name
- `created_at`: submission timestamp

Row Level Security must be enabled. The `anon` role needs SELECT and INSERT grants and matching RLS policies. The current policies allow public reads of submitted card IDs and anonymous inserts, but not updates or deletes.

## Development

The site is plain HTML, CSS, and JavaScript; no build step is required. Edit `index.html`. Pushing a change to `main` triggers a new GitHub Pages deployment.
