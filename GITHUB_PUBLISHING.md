# GitHub Pages publishing

The public frontend must never contain a GitHub Personal Access Token.

Recommended flow:
1. Admin logs in to the menu admin.
2. Admin adds/edits/deletes a menu.
3. Frontend sends the updated menu JSON to a secure backend endpoint such as `/api/publish-menu`.
4. The backend authenticates to GitHub using a server-side secret or GitHub App.
5. The backend commits the updated menu data to the repository.
6. GitHub Pages deploys the update.

This keeps the token out of the public HTML/JavaScript and browser developer tools.
