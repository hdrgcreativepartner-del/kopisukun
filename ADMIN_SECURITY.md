# Admin security

## Important
GitHub Pages is static. A username/password inside `index.html` is not secure:
visitors can inspect the JavaScript and bypass the login.

The current browser-only admin stores additions in `localStorage`. It does not
modify the repository HTML, but it is NOT a secure admin system.

## Production architecture
Use:

Admin browser
  -> HTTPS backend `/api/admin/login`
  -> authenticated server session
  -> `/api/menu` create/update/delete
  -> GitHub App or server-side GitHub credential
  -> repository menu data
  -> GitHub Pages deployment

Never put a GitHub token, GitHub App private key, or real admin password in
HTML, CSS, JavaScript, or any public GitHub Pages asset.
