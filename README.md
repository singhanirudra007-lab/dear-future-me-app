# Dear Future Me

**A digital time capsule app.** Write a letter, add photos and save memories, then seal them until a date you choose. This repository contains a working, clickable prototype built from a Figma design.

- **Brief:** an app where users write letters, upload photographs and save memories to be opened on a future date.
- **Audience:** ages 16 to 25, so the look is soft and playful.
- **Type of project:** a design project (UI/UX), coded as a working prototype of one full user flow: creating a time capsule.

---

## Contents

1. [Quick start](#quick-start)
2. [User flow](#user-flow)
3. [Screens](#screens)
4. [Features](#features)
5. [Micro-interactions](#micro-interactions)
6. [Design system](#design-system)
7. [Tech and project structure](#tech-and-project-structure)
8. [Data and storage](#data-and-storage)
9. [Deploying](#deploying)
10. [Accessibility](#accessibility)
11. [Known limitations](#known-limitations)

---

## Quick start

There is nothing to install and nothing to build.

1. Open `index.html` in any modern browser.
2. The first load needs internet so the fonts can load from Google Fonts.

For the best view on a computer, the app shows inside a 390 px wide phone frame. On a phone it fills the screen.

---

## User flow

```
Splash → Intro slides (3) → Name + goal → Welcome
                                              │
                                              ▼
Home ──► Create capsule ──► Write letter ──► Add photos ──► Pick date ──► Review ──► Seal ──► All set ──► Home
 │
 ├── Memories (timeline)
 ├── Profile
 └── Settings
```

The main flow is **creating one time capsule**: name it and choose a cover, write a letter, add photos, pick an unlock date, review everything, then seal it.

---

## Screens

### Onboarding
| Screen | What it does |
| --- | --- |
| Splash | App name, tagline and two polaroid photos. "Let's Begin" starts onboarding. |
| Intro 1: Write to your future self | Explains letters. "Dear Future Me," types itself out. |
| Intro 2: Save photos and moments | Explains photos. Photo tiles pop in one by one. |
| Intro 3: Seal it and wait | Explains the unlock date. A photo drops into a jar and the lid closes. |
| Nice to meet you | Asks for your first name and what you will save most (Memories, Gratitude, Goals, Letters to me). A script greeting updates as you type. |
| Welcome | "You're all set" with confetti. Go straight to making a first capsule, or explore the app. |

### Main app
| Screen | What it does |
| --- | --- |
| Home | Greeting, a "Create a Time Capsule" card, and your capsules with their opening dates. Search, "See all" and a ⋮ menu (Open, Delete) on each capsule. |
| Create capsule | Step 1 of 4. Name the capsule and pick a cover, either a default or one from your gallery. |
| Write a letter | Step 2 of 4. A prompt of the day, a "Dear Future Me," letter box and a live counter (max 1000 characters). |
| Add photos | Step 3 of 4. Pick up to 6 photos from the samples or upload from your gallery. |
| Pick a date | Step 4 of 4. A calendar (only future dates), a live "days from now" count and a "Surprise me!" button. |
| Review and seal | Summary of name, date, letter and photos, with Edit links for each part. |
| Sealing and All set | A sealing animation, then a confirmation with confetti and a countdown ("see you in N days"). |
| Memories | A timeline of your capsules as cards. Search, favourite with a star, and filter to favourites. |
| Capsule page | Locked capsules show a jar and the days left. Capsules past their date show the letter and photos. |
| Profile | Avatar, name, join date and stats (capsules, photos, days to the next opening). Rename and log out. |
| Settings | Opening day reminder toggle, hide capsule titles, replay onboarding and reset sample capsules. |

The bottom navigation has Home, Memories, a raised purple Create button, Profile and Settings.

---

## Features

- **Full capsule creation** in four steps with a review before sealing.
- **Upload from gallery** for both the capsule cover and the capsule photos. Images are resized in the browser to a maximum of 640 px on the long side (JPEG) to keep storage small.
- **Date picker** that blocks past dates, with month navigation and a random "Surprise me!" date.
- **Capsule locking:** a capsule stays locked until its date. Once the date has passed, the capsule page shows the letter and photos.
- **Memories timeline** with search and favourites.
- **Persistence:** your name, capsules, favourites, settings and uploaded photos are saved in the browser.
- **Onboarding** you can replay any time from Settings.
- **Responsive:** phone frame on desktop, full screen on phones.

---

## Micro-interactions

| Where | Interaction |
| --- | --- |
| Splash | Staggered entrance, floating polaroids, a paper plane that flies in, a nudging arrow on the button. |
| Intro slides | Slides move sideways in the direction you go. The active dot stretches. Swipe, tap a dot or use the arrow keys. |
| Name step | The greeting bumps as you type. Goal chips bounce when picked. |
| Photos | Selected photos pop and their tick bounces. The counter bumps. The grid shakes if you try to pick more than 6. Uploads pop in. |
| Date | The chosen day pops. The "days from now" number counts up or down. "Surprise me!" shuffles through dates before landing. |
| Sealing | A photo (or envelope) drops into a jar, the lid closes, the star lights up with a burst, then the text changes from "Sealing your capsule…" to "Sealed!". |
| All set and Welcome | Confetti, a floating jar and a pulsing glow. |
| Everywhere | Press feedback on buttons and nav items, lift on hover for cards. |

All animation is shortened to almost nothing when the device has "reduce motion" turned on.

---

## Design system

The look follows the reference style: soft off-white, lavender glows, dark pill buttons, polaroid photos and a glass jar with a star.

**Colors**

| Use | Value |
| --- | --- |
| Background | `#FBFAF9` |
| Text | `#1D1D1F` |
| Secondary text | `#6B6A70` |
| Buttons | `#2A2A2D` |
| Accent purple | `#6A58A8` |
| Create button purple | `#7447B0` |
| Lavender glow | `#ECE6F8` |
| Star gold | `#F4D77A` |
| Success green | `#3C8A55` on `#DDF1E0` |

**Fonts**

| Role | Font |
| --- | --- |
| Headings | DM Mono (monospace) |
| Body text | Instrument Sans |
| Script accents | Caveat |

**Shapes:** pill buttons (fully rounded, 54 px high), large rounded cards (22 to 28 px radius), soft shadows.

---

## Tech and project structure

The whole app is one file with no framework, no build tools and no dependencies.

```
.
├── index.html     the complete prototype (HTML, CSS, JavaScript and images)
├── vercel.json    small config for deploying on Vercel
└── README.md      this file
```

- **HTML, CSS and vanilla JavaScript** only.
- **Screens** are small functions that return HTML. A single `render()` function swaps the current screen, and one `bind()` function attaches the click handlers.
- **Images** (the sample photos and avatar) are embedded in `index.html` as base64 JPEGs, so the app works from a single file. This is why the file is about 480 KB.
- **Fonts** load from Google Fonts.

---

## Data and storage

Everything is saved in the browser's `localStorage` under the key `dfm-proto-v2`. Nothing is sent to a server.

Saved data: name, goal, join date, settings, capsules (title, cover, letter, photos, dates, favourite flag) and uploaded photos.

To start fresh, use **Profile → Log out**, or clear the site data in your browser. **Settings → Reset sample capsules** restores the three starter capsules.

---

## Deploying

### Vercel
1. Put these files at the root of a GitHub repository.
2. Import the repository at vercel.com/new.
3. Set Framework Preset to "Other" and leave Build Command and Output Directory empty. Deploy.

Or run `vercel` from this folder with the Vercel CLI.

### GitHub Pages
1. Push the files to a repository.
2. Go to Settings → Pages.
3. Choose "Deploy from a branch", pick `main` and `/ (root)`, then Save.
4. It will be live at `https://<your-username>.github.io/<repo-name>/`.

---

## Accessibility

- Buttons and form fields have labels, and icon-only buttons have `aria-label`s.
- Toggle buttons use `aria-pressed` and `aria-checked`. The current tab uses `aria-current`.
- Visible keyboard focus on controls.
- The upload tiles work with the keyboard (Enter or Space).
- Respects the "reduce motion" setting.

---

## Known limitations

This is a prototype, not a finished product.

- **No account system or server.** "Log out" only clears data stored in this browser. Data does not move between devices.
- **No real notifications.** The "Opening day reminder" toggle is saved but does not send anything.
- **Not secure storage.** Capsules are locked by the interface only. Anyone with access to the browser's storage could read them. Do not store private information in it.
- **Storage size.** Browsers limit `localStorage` (about 5 MB). If it fills up, new uploads work for the session but may not be saved.
- **Image formats.** Uploads rely on the browser being able to read the image. Some formats, such as HEIC on certain browsers, may fail with a message.
- **Sample photos** were taken from the Figma design at a small size, so they look soft when shown large.
- **Starter capsules** are example data with fixed dates.
- Tested in a desktop browser. It has not been tested across a range of real phones.
