# Cornelia Block Club Website
## Project Specification for Claude Code

---

## Overview

A simple, warm, community-focused static website for an informal block club on Cornelia Avenue between Elaine Place and Broadway in Chicago's East Lakeview neighborhood. The site serves as a local civic resource hub and community connector—not a traditional "block club" with meetings, but a friendly digital gathering point.

**Core Philosophy:** Privacy-conscious, good vibes only, hyper-local utility. No reply-all drama.

---

## Technical Stack

| Component | Choice | Rationale |
|-----------|--------|-----------|
| **Framework** | Astro | Simple, fast, markdown-based, great for content sites |
| **Styling** | Tailwind CSS | Utility-first, easy customization |
| **Hosting** | GitHub Pages | Free, Casey knows it |
| **Forms** | Embedded Google Forms | Free, privacy-conscious, Casey manages the data |
| **Domain** | Optional: custom domain later | Start with github.io |

---

## Project Structure

```
cornelia-block-club/
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro      # Main layout with nav, footer
│   ├── components/
│   │   ├── Header.astro          # Site header with nav
│   │   ├── Footer.astro          # Footer with contact info
│   │   ├── Card.astro            # Reusable card component
│   │   ├── ResourceLink.astro    # Quick link with icon
│   │   └── GoogleFormEmbed.astro # Reusable form embed
│   ├── pages/
│   │   ├── index.astro           # Home page
│   │   ├── resources.astro       # Local resources & civic info
│   │   ├── block-party.astro     # Block party info & history
│   │   ├── get-involved.astro    # Ways to connect
│   │   └── contact.astro         # Contact & signup
│   ├── content/
│   │   └── config.ts             # Content collections config (optional for future)
│   └── styles/
│       └── global.css            # Global styles, CSS variables
├── public/
│   ├── images/
│   │   └── (block photos, street trees, etc.)
│   └── favicon.svg
├── astro.config.mjs
├── tailwind.config.mjs
├── package.json
└── README.md
```

---

## Design Direction

### Aesthetic: "Neighborly Civic Pride"
- **Tone:** Warm, approachable, slightly retro-civic (think WPA posters meets modern web)
- **Not:** Corporate, cold, or over-designed

### Color Palette
```css
:root {
  /* Primary - Chicago-inspired, warm */
  --color-primary: #2E5A4C;        /* Deep forest green - trees, parks */
  --color-primary-light: #4A8B75;  /* Lighter green for hovers */
  
  /* Accent - Friendly warmth */
  --color-accent: #E07A3D;         /* Warm terracotta/brick */
  --color-accent-light: #F4A574;
  
  /* Neutrals - Warm grays */
  --color-bg: #FAF8F5;             /* Warm off-white */
  --color-bg-alt: #F0EDE8;         /* Slightly darker for cards */
  --color-text: #2C2C2C;           /* Near black */
  --color-text-muted: #6B6B6B;     /* Secondary text */
  
  /* Chicago accent */
  --color-chicago-blue: #41B6E6;   /* Chicago flag blue - sparingly */
}
```

### Typography
```css
/* Display: Something with character */
font-family: 'Fraunces', Georgia, serif;  /* Or: Playfair Display, Lora */

/* Body: Clean and readable */
font-family: 'Source Sans 3', -apple-system, sans-serif;  /* Or: Nunito, Lato */
```

### Design Elements
- Subtle paper/grain texture on background (optional)
- Rounded corners (soft, approachable)
- Generous whitespace
- Simple iconography (Lucide icons)
- Photos of the actual block/neighborhood if available

---

## Page Content & Structure

### 1. Home Page (`index.astro`)

**Hero Section:**
```
Welcome to Cornelia Ave
Between Elaine Place & Broadway
```
Brief welcome message (2-3 sentences max): "We're neighbors on one of Lakeview's great tree-lined blocks. This site is a simple way to stay connected and find local resources."

**Quick Links Grid (3-4 cards):**
- 🎉 Block Party Info → /block-party
- 📋 Local Resources → /resources  
- 🤝 Get Involved → /get-involved

**Simple CTA:**
"Want occasional updates about block happenings?" → Link to signup form

---

### 2. Resources Page (`resources.astro`)

**This is the civic utility hub.** Organized into clear sections:

#### Our Location
- **Address Range:** Cornelia Ave between Elaine Place (west) and Broadway (east)
- **Zip Code:** 60657
- **Neighborhood:** East Lakeview / Lakeview East
- **Community Area:** Lake View (one of Chicago's 77 community areas)

#### Ward Information
Our block is split between two wards:

**44th Ward** (likely western portion)
- **Alderman:** Bennett Lawson
- **Office:** 3223 N. Sheffield Ave, Suite A, Chicago, IL 60657
- **Phone:** 773-525-6034
- **Email:** ward44@cityofchicago.org
- **Website:** [44thward.org](https://www.44thward.org/)
- **Newsletter signup:** Available on website

**46th Ward** (likely eastern portion near Broadway)
- **Alderwoman:** Angela Clay
- **Office:** 4544 N. Broadway, Chicago, IL 60640
- **Phone:** 773-878-4646
- **Email:** info@46thward.com
- **Website:** [46thward.com](https://www.46thward.com/)

*Tip: Not sure which ward you're in? Look up your address at [chicagoelections.gov](https://chicagoelections.gov/districts-maps/ward-maps-electeds)*

#### Police District
- **District:** 19th District – Town Hall
- **Station:** 850 W. Addison St.
- **Coverage:** Lawrence to Fullerton, river to lake (includes all of Lakeview)
- **Non-emergency:** 312-744-8320
- **CAPS Info:** [chicagocaps19.org](https://chicagocaps19.org/)
- **Beat Meetings:** Community policing meetings held monthly in each beat
  - Find your beat & meeting schedule: [chicagopolice.org/find-your-district](https://www.chicagopolice.org/police-districts/find-your-district/)

#### Report Issues (CHI 311)
The CHI 311 system is your go-to for non-emergency city services:

- **Website:** [311.chicago.gov](https://311.chicago.gov)
- **App:** "CHI 311" on [iOS](https://apps.apple.com/us/app/chi311/id1441580123) and [Android](https://play.google.com/store/apps/details?id=org.cityofchicago.chi311)
- **Phone:** Call 311

**Common requests:**
| Issue | How to Report |
|-------|---------------|
| Pothole | 311 → "Pothole in Street" |
| Streetlight out | 311 → "Street Light Out" |
| Graffiti removal | 311 → "Graffiti Removal" |
| Alley light out | 311 → "Alley Light Out" |
| Tree trimming | 311 → "Tree Trim Request" |
| Rodent issue | 311 → "Rodent Baiting Request" |
| Abandoned vehicle | 311 → "Abandoned Vehicle" |
| Garbage cart issue | 311 → "Garbage Cart Maintenance" |

*Pro tip: Use the app to snap a photo and pin the exact location for faster service.*

#### Schools
CPS neighborhood schools are assigned by address. Look up your specific school:
- **CPS School Locator:** [schoolinfo.cps.edu/schoollocator](https://schoolinfo.cps.edu/schoollocator/index.html)

**Nearby schools serving East Lakeview:**
- Hawthorne Scholastic Academy (3319 N. Clifton Ave) - K-8
- Harriet Tubman Elementary (2851 N. Seminary Ave) - PK-8
- Lake View High School (4015 N. Ashland Ave) - 9-12

#### Neighborhood Organizations
- **East Lakeview Neighbors (ELVN):** [eastlakeview.org](https://eastlakeview.org/) - Our broader neighborhood association
- **Lakeview Citizens Council:** [lakeviewcitizens.org](https://lakeviewcitizens.org/) - Umbrella org for all Lakeview neighborhood groups
- **Lakeview East Chamber of Commerce:** [lakevieweast.com](https://lakevieweast.com/)

#### Emergency Contacts
| Service | Number |
|---------|--------|
| Emergency | 911 |
| Non-emergency police | 312-744-8320 |
| City services (311) | 311 |
| Poison Control | 1-800-222-1222 |
| ComEd Outages | 1-800-334-7661 |
| Peoples Gas Emergency | 1-866-556-6002 |

---

### 3. Block Party Page (`block-party.astro`)

**Intro:**
We host block parties twice a year (usually early summer and fall). These are casual, bring-a-dish affairs where we close the street, set up tables, and hang out.

**How Block Parties Work:**
- Permits are free and handled through the alderman's office
- Street closure: typically 10am-10pm
- One block only (intersection to intersection)
- No fireworks (they're illegal and can get future permits denied)

**Want to Help Plan?**
If you'd like to help coordinate, sign up below and we'll reach out.

[Embedded Google Form - Interest signup]

**Past Block Parties:**
(Space for photos/recaps if Casey wants to add them later)

**Official Info:**
- [City Block Party Permit Info](https://www.chicago.gov/city/en/depts/cdot/provdrs/construction_information/svcs/block_party_permitinformation.html)
- [44th Ward Block Party Packet (2025)](https://www.44thward.org/resources/block-parties/)
- Contact for 44th Ward block parties: Esmeralda.Borrero@cityofchicago.org

---

### 4. Get Involved Page (`get-involved.astro`)

**Intro:**
This isn't a formal organization with meetings and bylaws—just neighbors who want to make our block a little better. Here are some ways to connect.

**Ways to Participate:**

1. **Join the Email List**
   Get occasional updates about block happenings (a few times a year, max).
   [Embedded Google Form]

2. **Help with Block Parties**
   We always need people to help set up, bring food, or just show up and chat.

3. **Propose an Idea**
   Got an idea for the block? A community garden plot? A little free library? Speed bumps? Share it.
   [Embedded Google Form or mailto link]

4. **Connect with Neighbors**
   Looking for a dog walker? Want to organize a plant swap? Let us know and we can help facilitate (without sharing your contact info publicly).

**Philosophy:**
We're privacy-conscious. We don't share email addresses or create big reply-all chains. This is about good vibes and simple connection.

---

### 5. Contact Page (`contact.astro`)

**Stay Connected**

[Embedded Google Form for newsletter signup]

**Questions or Ideas?**
Email us: [your-email]@gmail.com (or whatever you want)

---

## Google Forms Setup (Casey to create)

### Form 1: Newsletter Signup
Fields:
- Name (required)
- Email (required)
- Which block are you on? (optional - dropdown or short answer)
- How did you hear about us? (optional)

### Form 2: Block Party Volunteer Interest
Fields:
- Name
- Email
- How can you help? (checkboxes: Setup, Cleanup, Bring food, Organize activities, Other)
- Anything else?

### Form 3: Ideas / Feedback (optional)
Fields:
- Name (optional)
- Email (optional)
- Your idea or feedback

---

## Implementation Notes for Claude Code

### Getting Started
```bash
# Create new Astro project
npm create astro@latest cornelia-block-club

# Choose: Empty template
# TypeScript: Yes (or No, preference)
# Install dependencies: Yes

cd cornelia-block-club

# Add Tailwind
npx astro add tailwind

# Install additional dependencies
npm install @fontsource/fraunces @fontsource/source-sans-3
```

### Key Implementation Details

1. **Keep it simple** - This is a ~5 page static site, not a web app
2. **Mobile-first** - Many neighbors will view on phones
3. **Fast loading** - Minimal JS, optimized images
4. **Accessible** - Good contrast, semantic HTML, keyboard navigation
5. **Easy to update** - Content should be easy to edit in markdown or directly

### Google Form Embedding
```astro
---
// components/GoogleFormEmbed.astro
interface Props {
  formUrl: string;
  title: string;
  height?: string;
}

const { formUrl, title, height = "600" } = Astro.props;
---

<div class="google-form-container">
  <iframe 
    src={formUrl}
    width="100%" 
    height={height}
    frameborder="0" 
    marginheight="0" 
    marginwidth="0"
    title={title}
  >
    Loading…
  </iframe>
</div>

<style>
  .google-form-container {
    border-radius: 8px;
    overflow: hidden;
    border: 1px solid var(--color-bg-alt);
  }
</style>
```

### Deployment to GitHub Pages
```yaml
# .github/workflows/deploy.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
      - run: npm ci
      - run: npm run build
      - uses: actions/upload-pages-artifact@v3
        with:
          path: dist
  
  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - uses: actions/deploy-pages@v4
        id: deployment
```

### astro.config.mjs for GitHub Pages
```javascript
import { defineConfig } from 'astro/config';
import tailwind from '@astrojs/tailwind';

export default defineConfig({
  site: 'https://YOUR_USERNAME.github.io',
  base: '/cornelia-block-club', // if using project pages
  integrations: [tailwind()],
});
```

---

## Future Enhancements (Phase 2+)

If the site grows, consider:
- **Event calendar** - Simple markdown-based events with date filtering
- **Photo gallery** - Past block party photos
- **Neighbor directory** - Opt-in only, privacy-first
- **Pet registry** - "Lost pets" utility
- **Tool lending** - "Who has a ladder?" type thing
- **Walking tour** - Your Detour-style audio tour idea!

---

## Summary

This spec gives you:
1. Complete site architecture
2. All local civic data researched and ready to paste
3. Design direction with colors and typography
4. Google Forms integration strategy
5. GitHub Pages deployment setup
6. Clear content for each page

**To build:** Hand this document to Claude Code and ask it to scaffold the Astro project following this spec. You can iterate from there.

Good luck, Casey! This is going to be great for the block. 🌳
