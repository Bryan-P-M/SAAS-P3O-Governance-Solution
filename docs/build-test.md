# Build and Test Commands

This document outlines the build and test commands for the Helm project.

## Prerequisites

- Git installed
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Node.js v18+ (for future development phases)
- A local development server (optional but recommended)

---

## Phase 1: Static Website

Phase 1 is a static HTML/CSS website with no build step required.

### Running Locally

**Option 1: Direct file access**
```bash
# Open index.html directly in your browser
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

**Option 2: Python simple server**
```bash
# Python 3
python -m http.server 8000

# Then open http://localhost:8000
```

**Option 3: Node.js http-server**
```bash
# Install globally (one time)
npm install -g http-server

# Run server
http-server -p 8000

# Then open http://localhost:8000
```

**Option 4: VS Code Live Server**
1. Install the "Live Server" extension in VS Code
2. Right-click `index.html` and select "Open with Live Server"

---

## Linting and Validation

### HTML Validation
```bash
# Using html-validate (Node.js)
npm install -g html-validate
html-validate index.html

# Or use the W3C validator online:
# https://validator.w3.org/
```

### CSS Validation
```bash
# Using stylelint (Node.js)
npm install -g stylelint stylelint-config-standard
stylelint "css/**/*.css"

# Or use the W3C CSS validator online:
# https://jigsaw.w3.org/css-validator/
```

---

## Future Phases: Build Commands

When the project evolves beyond static HTML, the following build setup is planned:

### Development Build
```bash
npm install           # Install dependencies
npm run dev           # Start development server with hot reload
```

### Production Build
```bash
npm run build         # Create optimised production build
npm run preview       # Preview production build locally
```

### Type Checking (if TypeScript is adopted)
```bash
npm run typecheck     # Run TypeScript compiler checks
```

---

## Test Commands

### Phase 1: Manual Testing
- Visual inspection across browsers (Chrome, Firefox, Safari, Edge)
- Responsive design testing (mobile, tablet, desktop)
- Accessibility testing with browser DevTools

### Future Phases: Automated Testing
```bash
npm test              # Run all tests
npm run test:unit     # Run unit tests only
npm run test:e2e      # Run end-to-end tests
npm run test:coverage # Run tests with coverage report
```

---

## Continuous Integration

GitHub Actions workflow will run on pull requests:

```yaml
# .github/workflows/ci.yml (future)
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Validate HTML
        run: npx html-validate index.html
      - name: Lint CSS
        run: npx stylelint "css/**/*.css"
```

---

## Deployment

### GitHub Pages (Phase 1)
```bash
# Push to main branch - GitHub Pages auto-deploys
git push origin main
```

### Manual Deployment Check
```bash
# Verify all files are committed
git status

# Check remote is configured
git remote -v

# Push to trigger deployment
git push
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| CSS not loading | Check file path in `<link>` tag is correct |
| Changes not appearing | Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R) |
| GitHub Pages not updating | Wait 1-2 minutes; check Actions tab for errors |
| Local server 404 errors | Ensure you're running server from project root |

---

## Quick Reference

| Task | Command |
|------|---------|
| Start local server | `python -m http.server 8000` |
| Validate HTML | `npx html-validate index.html` |
| Lint CSS | `npx stylelint "css/**/*.css"` |
| Deploy to GitHub Pages | `git push origin main` |
