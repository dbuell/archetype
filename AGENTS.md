# Archetype Website - Development Guidelines

## Workflow

### Feature Development Process

1. **Create a feature branch** before making any changes:
   ```bash
   git checkout -b feat/your-feature-name
   ```

2. **Make changes and commit** on the feature branch

3. **Create a PR** when ready for review:
   ```bash
   gh pr create --title "feat: description" --body "Summary of changes"
   ```

4. **Merge after approval** via GitHub PR UI or:
   ```bash
   gh pr merge
   ```

## GitHub Pages Deployment

- GitHub Pages deploys from the `main` branch
- Changes to `main` are automatically live within a few minutes
- No manual deployment steps needed

## Email Privacy

If push is rejected due to email privacy, use the no-reply email:
```
2711948+dbuell@users.noreply.github.com
```

Set it temporarily for commits:
```bash
GIT_AUTHOR_EMAIL='2711948+dbuell@users.noreply.github.com' git commit ...
```

## File Structure

```
index.html    - Homepage
about.html    - About page
team.html     - Team/About Us page
styles.css    - Shared stylesheet
CNAME         - Domain configuration for GitHub Pages
docs/         - Documentation and specs
```

## Common Tasks

### Add a new page
1. Copy `about.html` as a template (has header/footer)
2. Add CSS classes to `styles.css` if needed
3. Update navigation links in header on ALL pages
4. Test navigation works between pages
