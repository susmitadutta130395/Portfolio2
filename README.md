# Susmita Dutta — Dark Cyberpunk Executive Portfolio & 3D Video Engine

An award-winning, production-ready dark cyberpunk portfolio built for **Susmita Dutta** (Business Development Manager, Operations Manager, Social Media Manager & Content Strategist), featuring an interactive **Cursor-Controlled & Scroll-Scrubbed 3D Video Background Engine** and a **3D Draggable Cylindrical Gallery for Certifications**.

---

## 🏛️ Executive Profile Summary

- **Candidate**: Susmita Dutta
- **Core Title**: Business Development Manager | Operations Manager | Social Media Manager | Content Strategist
- **Experience**: 8+ Years across Growth Marketing, Cross-Border E-Commerce, Paid Acquisition (Meta Ads), and Dignitary PR
- **Location**: Guwahati / New Delhi, India
- **Contact**: +91 86382 39868 | susmitadutta130395@gmail.com
- **Enterprise Footprint**: 35+ Enterprise Accounts & Government Mandates (Shopify, Nykaa, Myntra, Aramex, CID Assam, UNICEF, Apollo Hospitals, Godrej & Boyce)

---

## ⚡ Signature Architectural Highlights

### 1. Cinematic Cursor & Scroll Video Engine (`src/components/CinematicVideo.tsx`)
- **Normalized LERP Scrubbing**: Integrates normalized cursor X (30% weight) and document scroll progress (70% weight) in a continuous `requestAnimationFrame` loop.
- **Seeking Precision**:
  ```ts
  currentRef.current += (targetRef.current - currentRef.current) * 0.10;
  if (Math.abs(delta) > 0.001) {
    try { video.currentTime = currentRef.current; } catch {}
  }
  ```
- **Interactive 3D Parallax Tilt**:
  `transform: scale(1.06) translate3d(dx * -15px, dy * -15px, 0) rotateX(dy * -2deg) rotateY(dx * 2deg)`
- **Atmospheric Overlays**:
  - `.cine-vignette`: Dark radial edge falloff.
  - `.cine-glow` (`#cine-glow`): Dynamic cursor-tracking spotlight updated on mousemove.
  - `.cine-grain`: Subtle SVG noise grain overlay with keyframe jitter.
  - `.cine-scan`: Ultra-faint scanlines.
  - `#scroll-progress-bar`: Ambient red glowing scroll indicator at the top of the viewport (`height: 2px`).

### 2. 3D Draggable Circle Gallery for Certifications (`src/components/sections/Certifications.tsx`)
- **Responsive Radius**: 480px (Desktop), 380px (Tablet), 275px (Mobile).
- **3D Camera Pull-Back Technique**:
  - Cylinder ring placed at `transform: translateZ(-R) rotateY(angle deg)`.
  - Cards placed at `transform: translate(-50%, -50%) rotateY(i * step) translateZ(R)`.
  - Front-facing card sits precisely at $Z = -R + R = 0$ (exact scale 1.0), preventing magnification ballooning or overlapping with the section title.
- **Backface Culling**: Hides rear cards when $\cos(\phi) < -0.15$ to avoid inverted typography.
- **Unified Pointer Physics**: Pointer capture, multi-sample velocity tracking, throw inertia with 0.945 friction damping, and gentle 0.06°/frame auto-spin with toggle.
- **Cybernetic Verification Modal**: Inspects cryptographic SHA-256 hashes (`SHA256://...`), verified dates, issuer badges, and validated competencies.

### 3. Bilateral Alternating Experience & Education Timeline (`src/components/sections/Experience.tsx`)
- Central glowing neon laser spine down the middle (50% desktop, single-column mobile).
- Alternating left & right cards with glowing waypoint nodes and pulsing status rings.
- Interactive filter pills: `All`, `Work Experience`, `Education`.

### 4. Editorial Hero Section (`src/components/sections/Hero.tsx`)
- 'Oswald' Google font typography: `BUILDING IDEAS` in solid white, `INTO EXPERIENCES.` with linear gradient text clip and neon period.
- High-intensity background watermark with candidate's first name: `SUSMITA` (`WebkitTextStroke: '2px rgba(196, 0, 36, 0.35)'`).
- Telemetry metric counters & Open to Opportunities status beacon.

---

## 📂 Project Directory Structure

```
susmita-dutta-portfolio/
├── package.json                          # Next.js 14 + Tailwind + TypeScript dependencies
├── tsconfig.json                         # TypeScript configuration with @/* path aliases
├── tailwind.config.ts                    # Custom cyberpunk palette & tokens
├── postcss.config.js                     # PostCSS config
├── next.config.mjs                       # Next.js configuration
├── server.js                             # Zero-dependency Node server with HTTP 206 Partial Content
├── index.html                            # Standalone production preview
├── public/
│   ├── video/
│   │   └── portfolio-background.mp4      # Background video asset
│   └── images/
│       └── susmita-portrait.png          # Executive candidate portrait
└── src/
    ├── app/
    │   ├── globals.css                   # Overlays, scanlines, fonts, and tokens
    │   ├── layout.tsx                    # Root layout with Lenis & Custom Cursor
    │   └── page.tsx                      # Page composition
    ├── types/
    │   └── index.ts                      # Strict TypeScript interfaces
    ├── data/
    │   └── portfolioData.ts              # Complete extracted resume dataset
    └── components/
        ├── CinematicVideo.tsx            # Signature Video Scrubbing Engine
        ├── CustomCursor.tsx              # Luxury Lerp Cursor & Magnetic Ring
        ├── LenisProvider.tsx             # Smooth inertial scrolling
        ├── Navbar.tsx                    # Frosted glass floating navigation
        ├── CertificationModal.tsx        # Cryptographic verification modal
        └── sections/
            ├── Hero.tsx                  # Editorial Oswald Hero
            ├── About.tsx                 # Cyber-inspection dossier
            ├── Experience.tsx            # Bilateral Alternating Timeline
            ├── Certifications.tsx        # 3D Draggable Cylindrical Gallery
            ├── Projects.tsx              # 3D perspective tilt cards
            ├── Skills.tsx                # Categorized skill meters & client badges
            ├── Contact.tsx               # Cybernetic contact form & clipboard copy
            └── Footer.tsx                # Cybernetic footer
```

---

## 🚀 How to Run

### Method 1: Instant Server (Recommended with `agy-node`)
Run the lightweight local server directly:
```bash
agy-node server.js
```
Then open:
```
http://localhost:3000
```

### Method 2: Next.js 14 Dev Server
Install dependencies and run Next.js:
```bash
npm install
npm run dev
```
Then open:
```
http://localhost:3000
```

