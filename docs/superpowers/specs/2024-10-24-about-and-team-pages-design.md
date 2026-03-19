# About and Team Pages Design

## Goal
Add two new pages to the Archetype website: an "About" page detailing the company's mission and services, and an "About Us" (Team) page highlighting the key personnel.

## Approach
- Create `about.html` and `team.html` based on the existing `index.html` structure to ensure a consistent look and feel (header, footer, typography, colors).
- Extract the common CSS into a separate file (`styles.css`) and link it in all three HTML files (`index.html`, `about.html`, `team.html`).
- Update navigation links in the header across all pages to point to the new pages.

## Content Mapping
### About Page (`about.html`)
- **Hero Section:** "Revolutionizing the Electrical Product Safety Certification Process".
- **Main Content Area:** 
  - Section on bridging the gap between manufacturers and certification bodies, prioritizing efficiency and time.
  - Section on streamlining the process, submitting updates to standards, and mitigating financial losses.
  - Section on the centralized platform feature for posting certifications and creating an interconnected ecosystem.

### Team Page (`team.html`)
- **Hero Section:** "Meet the Archetype Team".
- **Team Grid:** A grid layout displaying the team members.
  - **Mary Foerster (CEO):** Experience in certification ecosystem, connecting dots, established relationships.
  - **Dr. Tomer Libal (CTO):** 24+ years in AI, AI and Law focus, American University of Paris, University of Luxembourg.
  - **Devin Buell (COO):** 15+ years bringing products to market, building teams/processes, sustaining operations.
  - **Steven Foerster (VP of Engineering):** 28+ years building systems (cybersecurity, automation, AI).

## Architectural Changes
1. Create `styles.css` from the `<style>` block in `index.html`.
2. Update `index.html` to link to `styles.css` and remove the inline `<style>`.
3. Create `about.html` using the base template from `index.html` (header, footer), linking to `styles.css`.
4. Create `team.html` using the base template from `index.html` (header, footer), linking to `styles.css`. Add a new CSS grid layout for the team members in `styles.css` (e.g., `.team-grid`, `.team-member`).
5. Update navigation in all three files.

