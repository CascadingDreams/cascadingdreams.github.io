# Personal Portfolio

**[samanthahill.dev](https://samanthahill.dev)**

My personal portfolio site — built with vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies. Hosted on GitHub Pages.

![Portfolio screenshot](docs/portfolio%20image.png)

---

## Built with

| Tool | Role |
|---|---|
| HTML / CSS / JavaScript | The entire site — I kept it framework-free intentionally |
| [Claude Code](https://claude.ai/code) | AI coding assistant I used to build, iterate, and refine the site throughout development |
| [Playwright](https://playwright.dev) | Browser automation I used for local testing and visual inspection |
| [shields.io](https://shields.io) | Badge images for the tech stack section |
| [Google Fonts](https://fonts.google.com) | Inter (UI) and JetBrains Mono (terminal / code) |
| [GitHub API](https://docs.github.com/en/rest) | I pull live "currently working on" data from my public events endpoint |
| [GitHub Pages](https://pages.github.com) | Hosting and deployment |

---

## What's in it

### Interactive terminal

The centrepiece of the hero section. I built a command interpreter that accepts typed input and responds with styled output.

| Command | Description |
|---|---|
| `help` | List available commands |
| `whoami` | Name and location |
| `ls` | List my projects |
| `skills` | Full tech stack |
| `contact` | Links and email |
| `open [project]` | Open a project on GitHub in a new tab |
| `clear` | Clear the terminal (re-shows help) |
| `surprise` | Kaomoji loop — keeps going if you type `y` |

**Terminal features I added:**
- `↑` / `↓` arrow keys cycle through command history
- `Tab` autocompletes commands and `open` project names
- Typewriter animation types `help` on load
- Click anywhere on the terminal to focus the input

### Tech stack section

I display my skills as five groups of shields.io badge images (Languages, Frameworks Libraries & Tools, Data & BI, Cloud & DevOps, Collaboration), all styled in my accent blue (`#4d9bf5`). The layout uses a 6-column CSS grid — 3 groups on the top row, 2 centred on the bottom row for symmetry.

### GitHub activity

On page load, I fetch my public GitHub events and find the most recent `PushEvent` to show which repo I last committed to. It appears below the hero buttons with a pulsing green dot. Uses the unauthenticated public API (60 req/hour per IP — fine for a portfolio).

### Other UI details

- **Scroll progress bar** — 2px accent-blue line fixed at the very top of the viewport as you scroll
- **Active nav** — nav links highlight as the corresponding section scrolls into view, using `IntersectionObserver`
- **Copy email** — clicking my email address copies it to clipboard and shows `copied! ✓` for 2 seconds
- **Favicon** — inline SVG data URI, `>_` in accent blue on a dark background, no external file needed
- **Fade-in animations** — sections fade up as they enter the viewport via `IntersectionObserver`

---

## Structure

I kept everything in a single `index.html` — styles in `<style>`, markup in `<body>`, scripts in a `<script>` block at the bottom.

```
cascadingdreams.github.io/
├── index.html       # the whole site
├── CNAME            # custom domain config for GitHub Pages
└── README.md
```

---

## Running locally

No build step required — just open `index.html` in a browser.

```bash
# or with Python's built-in server for accurate local behaviour:
python3 -m http.server 8000
```

---

## Deployment

I push to the `main` branch and GitHub Pages serves it automatically via the CNAME record pointing `samanthahill.dev` to `cascadingdreams.github.io`.
