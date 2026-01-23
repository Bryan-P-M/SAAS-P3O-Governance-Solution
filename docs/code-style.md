# Code Style Guidelines

This document defines the coding standards and style guidelines for the Helm project.

---

## General Principles

1. **Consistency** - Follow existing patterns in the codebase
2. **Readability** - Code should be self-documenting where possible
3. **Simplicity** - Prefer simple solutions over clever ones
4. **Accessibility** - Build for all users from the start

---

## HTML Guidelines

### Structure
- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- Maintain proper heading hierarchy (h1 → h2 → h3, never skip levels)
- Use meaningful `id` and `class` names

### Formatting
```html
<!-- Use 2-space indentation -->
<section class="features">
  <h2>Features</h2>
  <ul>
    <li>Feature one</li>
    <li>Feature two</li>
  </ul>
</section>

<!-- Use lowercase for tags and attributes -->
<img src="image.png" alt="Description" />

<!-- Quote all attribute values -->
<a href="https://example.com" class="link">Link text</a>
```

### Accessibility
- Always include `alt` text for images
- Use ARIA labels where semantic HTML is insufficient
- Ensure sufficient colour contrast (WCAG AA minimum)
- Make all interactive elements keyboard-accessible

### Best Practices
- Include `lang` attribute on `<html>` element
- Use `<button>` for actions, `<a>` for navigation
- Avoid inline styles; use CSS classes instead
- Keep the DOM structure as flat as reasonably possible

---

## CSS Guidelines

### File Organisation
```
css/
├── styles.css       # Main stylesheet (Phase 1)
└── (future structure)
    ├── base/        # Reset, typography, variables
    ├── components/  # Reusable component styles
    └── layouts/     # Page layout styles
```

### Naming Convention
Use BEM (Block Element Modifier) naming:
```css
/* Block */
.card { }

/* Element */
.card__title { }
.card__body { }

/* Modifier */
.card--featured { }
.card--compact { }
```

### Formatting
```css
/* Use 2-space indentation */
/* One property per line */
/* Space after colon */
/* Semicolon on every declaration */

.selector {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background-color: var(--color-background);
}

/* Group related properties */
.element {
  /* Positioning */
  position: relative;
  top: 0;

  /* Box model */
  display: block;
  width: 100%;
  padding: 1rem;
  margin: 0;

  /* Typography */
  font-family: var(--font-primary);
  font-size: 1rem;
  color: var(--color-text);

  /* Visual */
  background-color: white;
  border: 1px solid var(--color-border);
  border-radius: 4px;

  /* Misc */
  transition: opacity 0.2s ease;
}
```

### CSS Custom Properties (Variables)
```css
:root {
  /* Colours */
  --color-primary: #1a365d;
  --color-secondary: #2b6cb0;
  --color-text: #1a202c;
  --color-text-muted: #718096;
  --color-background: #ffffff;
  --color-border: #e2e8f0;

  /* Typography */
  --font-primary: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-mono: 'Fira Code', monospace;

  /* Spacing */
  --space-xs: 0.25rem;
  --space-sm: 0.5rem;
  --space-md: 1rem;
  --space-lg: 2rem;
  --space-xl: 4rem;

  /* Breakpoints (for reference) */
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
}
```

### Responsive Design
```css
/* Mobile-first approach */
.container {
  padding: 1rem;
}

@media (min-width: 768px) {
  .container {
    padding: 2rem;
  }
}

@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
}
```

### Best Practices
- Use relative units (`rem`, `em`, `%`) over pixels where appropriate
- Avoid `!important` except for utility classes
- Use CSS custom properties for theming
- Keep specificity low; avoid deep nesting
- Use `flexbox` or `grid` for layouts

---

## JavaScript Guidelines (Future Phases)

### General
- Use ES6+ syntax
- Prefer `const` over `let`; avoid `var`
- Use meaningful variable and function names
- Keep functions small and focused

### Formatting
```javascript
// 2-space indentation
// Single quotes for strings
// Semicolons required
// Space before function parentheses

function calculateTotal(items) {
  const total = items.reduce((sum, item) => {
    return sum + item.price;
  }, 0);

  return total;
}

// Object and array formatting
const config = {
  apiUrl: 'https://api.example.com',
  timeout: 5000,
  retries: 3,
};

const features = [
  'raid-log',
  'action-tracking',
  'governance-meetings',
];
```

### Naming Conventions
| Type | Convention | Example |
|------|------------|---------|
| Variables | camelCase | `userName`, `totalCount` |
| Constants | SCREAMING_SNAKE_CASE | `MAX_RETRIES`, `API_URL` |
| Functions | camelCase | `getUserData()`, `calculateTotal()` |
| Classes | PascalCase | `RaidItem`, `GovernanceBoard` |
| Files | kebab-case | `raid-log.js`, `user-service.js` |

---

## Git Commit Messages

### Format
```
<type>: <short summary>

<optional body - explain what and why>
```

### Types
| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no code change |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test` | Adding or updating tests |
| `chore` | Maintenance tasks |

### Examples
```bash
feat: Add RAID log dashboard component

fix: Correct date formatting in action items

docs: Update build instructions for Windows

style: Apply consistent spacing in navigation CSS

refactor: Extract common validation logic to utility
```

### Guidelines
- Use imperative mood ("Add feature" not "Added feature")
- Keep the first line under 72 characters
- Reference issue numbers where applicable: `fix: Resolve login error (#42)`

---

## File and Folder Naming

| Type | Convention | Example |
|------|------------|---------|
| HTML files | kebab-case | `index.html`, `about-us.html` |
| CSS files | kebab-case | `styles.css`, `components.css` |
| JavaScript files | kebab-case | `main.js`, `raid-service.js` |
| Image files | kebab-case | `hero-background.png`, `logo-dark.svg` |
| Documentation | kebab-case | `project-brief.md`, `code-style.md` |
| Folders | kebab-case | `css/`, `images/`, `docs/` |

---

## Editor Configuration

### Recommended VS Code Settings
```json
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true
}
```

### Recommended Extensions
- Prettier - Code formatter
- ESLint (future)
- HTML CSS Support
- Live Server

---

## Code Review Checklist

Before submitting code for review:

- [ ] Code follows style guidelines
- [ ] HTML is valid and semantic
- [ ] CSS uses BEM naming convention
- [ ] No inline styles (unless absolutely necessary)
- [ ] Responsive design works on mobile
- [ ] Accessibility requirements met
- [ ] No console errors in browser
- [ ] Commit message follows convention
