# Resume
 
Personal resume site built with Nuxt 4. A single-page, terminal-styled resume with a few small interactive touches, plus a downloadable PDF version.
 
**[Live site](https://frontend-resume-bygray.netlify.app/)**
 
## Features
 
- 🖱️ Blinking terminal cursor after the name, CSS-only
- 📊 Stats (years of experience, lines of code, cups of coffee) count up from 0 on load
- 🌐 Language proficiency shown as animated conic-gradient rings, filling on mount
- 🧲 Magnetic Download button — follows the cursor within a radius, settles back outside it
- 📄 One-click PDF download of the resume (black & white, no photo, working hyperlinks)
- ♿ Respects `prefers-reduced-motion`
- 📱 Responsive layout down to mobile widths
## Tech stack
 
| Layer      | Tech                                      |
|------------|--------------------------------------------|
| Framework  | Nuxt 4 (`app/` directory structure)       |
| UI         | Vue 3, `<script setup>`, Composition API  |
| Language   | TypeScript                                |
| Fonts      | `@nuxt/fonts` (JetBrains Mono, IBM Plex Sans) |
| Images     | `@nuxt/image`                             |
| Rendering  | Static generation (SSR-rendered at build time, no server at runtime) |
| Hosting    | Netlify                                   |
 
## Project structure
 
```
app/
├── components/
│   └── resume/
│       ├── ResumeHero.vue          # name, photo, contacts, download button
│       ├── ResumeStats.vue         # animated stat counters
│       ├── ResumeSkills.vue        # skills grid
│       ├── ResumeProjects.vue      # project cards
│       ├── ResumeExperience.vue    # work history
│       ├── ResumeEducation.vue
│       └── ResumeLanguages.vue     # animated language rings
├── assets/
│   ├── css/main.css                # design tokens, base styles
│   └── icons/                      # contact icons
├── app.vue                         # assembles all sections
public/
└── resume.pdf                      # downloadable resume
```
 
## Getting started
 
```bash
git clone https://github.com/GrayMurakami/frontend-resume-bygray.git
cd frontend-resume-bygray
npm install
npm run dev
```
 
## Build
 
```bash
npm run build
```
 
On Netlify, Nitro (Nuxt's server engine) detects the Netlify environment automatically and outputs a static build to `dist` — no extra configuration needed beyond build command `npm run build` and publish directory `dist`.
 
## Contact
 
- Email: [email]
- Telegram: [telegram]
- GitHub: [github.com/GrayMurakami](https://github.com/GrayMurakami)
- LinkedIn: [linkedin]
