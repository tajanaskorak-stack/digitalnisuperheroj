# Tailwind CSS Migration Plan

## Current State Analysis
- **Tailwind CSS v4** is already installed and configured in `astro.config.mjs`
- **DaisyUI** plugin is installed and imported in `global.css`
- **shadcn/ui** is configured with proper CSS variables and utilities
- **Button component** is already using Tailwind classes
- **Most styling** is done with traditional CSS in `<style>` blocks within Astro components
- **tailwind.config.js** has empty content array - needs to be updated

## Migration Strategy
Maintain the exact same visual appearance while transitioning from hard CSS to Tailwind utilities and DaisyUI components.

## Step-by-Step Tasks

### 1. Configure Tailwind Content Scanning
**File:** `tailwind.config.js`
- Update the `content` array to include all source files
- This ensures Tailwind purges unused styles correctly

### 2. Convert Global Styles
**File:** `src/styles/global.css`
- Move custom CSS variables and fonts to proper Tailwind config
- Convert remaining hard CSS to Tailwind utilities using `@apply`
- Preserve the Bear Blog design while using Tailwind

### 3. Convert Component Styles
Convert `<style>` blocks in Astro components to Tailwind classes:

**Files to update:**
- `src/layouts/BlogPost.astro` - Inline styles for layout, hero image, prose, title, date
- `src/components/Header.astro` - Header navigation styles
- `src/components/Footer.astro` - Footer styling
- `src/components/HeaderLink.astro` - Link styling

### 4. Test and Verify
- Run the development server to ensure visual consistency
- Check responsive breakpoints
- Verify all components render correctly
- Confirm no CSS conflicts

## Design Preservation Notes
- Keep the original color scheme using CSS custom properties
- Maintain responsive breakpoints and layout structure
- Preserve typography hierarchy and spacing
- Keep the gradient background and box shadows

## Post-Migration Benefits
- Consistent utility-first approach across all components
- Better maintainability with Tailwind's responsive utilities
- Access to full DaisyUI component library
- Improved development experience with IntelliSense
- Smaller bundle size through better tree-shaking

## Rollback Plan
If issues arise, the original CSS can be restored from git history since we're maintaining the same visual output during migration.
