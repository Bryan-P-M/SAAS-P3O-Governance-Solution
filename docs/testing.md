# Testing Instructions

This document provides comprehensive testing guidance for the Helm project.

---

## Testing Strategy Overview

| Phase | Testing Approach |
|-------|------------------|
| Phase 1 (Static Site) | Manual testing, browser validation, accessibility checks |
| Future Phases | Unit tests, integration tests, E2E tests, automated CI |

---

## Phase 1: Manual Testing Procedures

### 1. Browser Compatibility Testing

Test the landing page in all major browsers:

| Browser | Versions to Test | Priority |
|---------|------------------|----------|
| Chrome | Latest, Latest-1 | High |
| Firefox | Latest, Latest-1 | High |
| Safari | Latest (macOS/iOS) | High |
| Edge | Latest | Medium |

**Testing Checklist:**
- [ ] Page loads without errors
- [ ] All styles render correctly
- [ ] Navigation works as expected
- [ ] No console errors (open DevTools → Console)
- [ ] Images load properly
- [ ] Fonts display correctly

---

### 2. Responsive Design Testing

Test at these breakpoints:

| Device Type | Width | Test Method |
|-------------|-------|-------------|
| Mobile (small) | 320px | Chrome DevTools |
| Mobile (large) | 414px | Chrome DevTools |
| Tablet | 768px | Chrome DevTools |
| Desktop | 1024px | Browser window |
| Large Desktop | 1440px | Browser window |

**How to test with Chrome DevTools:**
1. Open Chrome DevTools (F12 or Cmd+Option+I)
2. Click the device toggle icon (or Cmd+Shift+M)
3. Select device or enter custom dimensions
4. Refresh the page and verify layout

**Responsive Testing Checklist:**
- [ ] Text is readable at all sizes (no tiny fonts)
- [ ] Buttons/links are tappable on mobile (min 44x44px)
- [ ] No horizontal scrolling on mobile
- [ ] Images scale appropriately
- [ ] Navigation adapts to screen size
- [ ] Content doesn't overflow containers
- [ ] Spacing looks appropriate at each breakpoint

---

### 3. Accessibility Testing

#### Automated Tools
1. **WAVE Browser Extension** (recommended)
   - Install from [wave.webaim.org](https://wave.webaim.org/extension/)
   - Click extension icon to run accessibility audit

2. **Lighthouse Accessibility Audit**
   - Open Chrome DevTools
   - Go to Lighthouse tab
   - Select "Accessibility" category
   - Click "Generate report"
   - Aim for 90+ score

3. **axe DevTools Extension**
   - Install from Chrome Web Store
   - Run full page scan

#### Manual Accessibility Checks
- [ ] **Keyboard Navigation**: Tab through all interactive elements
  - Focus is visible on all focusable elements
  - Tab order is logical
  - No keyboard traps
  - Enter/Space activates buttons and links

- [ ] **Screen Reader Testing** (optional but recommended)
  - macOS: Enable VoiceOver (Cmd+F5)
  - Windows: Use NVDA (free) or Narrator
  - Verify content is announced correctly

- [ ] **Colour Contrast**
  - Use [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
  - Normal text: minimum 4.5:1 ratio
  - Large text: minimum 3:1 ratio

- [ ] **Zoom Testing**
  - Zoom to 200% (Cmd/Ctrl + +)
  - Content should remain usable
  - No text cut off or overlapping

**Accessibility Checklist:**
- [ ] All images have alt text
- [ ] Headings are in correct order (h1 → h2 → h3)
- [ ] Links have descriptive text (not "click here")
- [ ] Form inputs have labels (future)
- [ ] Colour is not the only means of conveying information
- [ ] Page has a main landmark
- [ ] Skip link present (if applicable)

---

### 4. Content Testing

- [ ] All text is free of typos and grammatical errors
- [ ] Links point to correct destinations
- [ ] Email addresses are correct
- [ ] Phone numbers are correct (if any)
- [ ] Legal/copyright text is up to date
- [ ] No placeholder/lorem ipsum text remains

---

### 5. Performance Testing

**Lighthouse Performance Audit:**
1. Open Chrome DevTools
2. Go to Lighthouse tab
3. Select "Performance" category
4. Choose "Mobile" device
5. Click "Generate report"

**Performance Targets:**
| Metric | Target |
|--------|--------|
| Performance Score | 90+ |
| First Contentful Paint | < 1.8s |
| Largest Contentful Paint | < 2.5s |
| Cumulative Layout Shift | < 0.1 |

**Performance Checklist:**
- [ ] Images are optimised (compressed, correct format)
- [ ] No unused CSS
- [ ] Minimal render-blocking resources
- [ ] Page loads in < 3 seconds on 3G

---

### 6. HTML/CSS Validation

**HTML Validation:**
1. Go to [validator.w3.org](https://validator.w3.org/)
2. Upload file or paste HTML
3. Fix any errors (warnings are optional)

**CSS Validation:**
1. Go to [jigsaw.w3.org/css-validator](https://jigsaw.w3.org/css-validator/)
2. Upload file or paste CSS
3. Fix any errors

**Validation Checklist:**
- [ ] HTML has no errors
- [ ] CSS has no errors
- [ ] All tags are properly closed
- [ ] No duplicate IDs

---

## Testing Environments

### Local Testing
```bash
# Start local server
python -m http.server 8000

# Open in browser
open http://localhost:8000
```

### Staging (GitHub Pages Preview)
- Push to feature branch
- Use GitHub Pages preview or deploy preview

### Production (GitHub Pages)
- Main branch auto-deploys to GitHub Pages
- Verify at: `https://<username>.github.io/helm/`

---

## Bug Reporting Template

When reporting issues, include:

```markdown
## Bug Description
[Clear description of the issue]

## Steps to Reproduce
1. [First step]
2. [Second step]
3. [And so on...]

## Expected Behaviour
[What should happen]

## Actual Behaviour
[What actually happens]

## Environment
- Browser: [e.g., Chrome 120]
- OS: [e.g., macOS 14.0]
- Screen size: [e.g., 1920x1080]

## Screenshots
[If applicable]
```

---

## Future Phases: Automated Testing

### Unit Testing (Planned)
```bash
# Run unit tests
npm test

# Run with coverage
npm run test:coverage

# Run in watch mode
npm run test:watch
```

### End-to-End Testing (Planned)
```bash
# Run E2E tests
npm run test:e2e

# Run E2E tests in headed mode
npm run test:e2e:headed
```

### Continuous Integration
Tests will run automatically on:
- Pull request creation
- Push to main branch
- Scheduled daily runs

---

## Testing Checklist Summary

### Before Each Commit
- [ ] Page loads without console errors
- [ ] Visual inspection on desktop
- [ ] Quick mobile check (DevTools)

### Before Pull Request
- [ ] Full browser compatibility test
- [ ] Responsive design at all breakpoints
- [ ] Accessibility audit (Lighthouse 90+)
- [ ] HTML/CSS validation
- [ ] Content review for typos
- [ ] Performance check

### Before Release
- [ ] All PR checks pass
- [ ] Final review on staging
- [ ] Cross-browser testing
- [ ] Accessibility compliance verified
- [ ] Performance benchmarks met

---

## Quick Reference

| Task | Tool/Method |
|------|-------------|
| Check console errors | Browser DevTools (F12) |
| Test responsiveness | Chrome DevTools device mode |
| Accessibility audit | Lighthouse or WAVE extension |
| Validate HTML | validator.w3.org |
| Validate CSS | jigsaw.w3.org/css-validator |
| Check performance | Lighthouse Performance tab |
| Test colour contrast | WebAIM Contrast Checker |
