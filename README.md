# Srithvik Ellanki, Engineering Portfolio

Aerospace Engineering (Astronautics) at Florida Institute of Technology.

This repo is a static GitHub Pages site. There's no build step: `index.html` loads its photos from `img/` and its videos and resume from `media/`.

## Updating the live site

1. Unzip this package.
2. Upload `index.html`, `README.md`, and the `img` and `media` folders over the existing files in the repo, then commit.
3. GitHub Pages republishes automatically within a minute or two.

## Updating your resume

Replace `media/Srithvik_Ellanki_Resume.pdf` with your new PDF, using the exact same file name. Every Resume button on the site points to that one file, so nothing else needs to change.

If you ever want a different file name, change the one line near the top of the script in `index.html`:

```
var RESUME_FILE = 'media/Srithvik_Ellanki_Resume.pdf';
```

## Site structure

- **Home:** just you: the space intro, with an About me button at the bottom that slides the About page up over the landing page
- **About** (`#about`): its own page with About me, Outside of engineering, and a button into the Work page
- **Work** (`#work`): its own dark page with a sideways reel of big project panels (drag it, or use the arrows or arrow keys). Panels glide smoothly between stops. The ones not in front stay dark and blurred, and the panel in front brightens before its text fades in, and a counter, progress bar, and the arrows sit under the reel. The last panel is a "More to come" slide; it stays at the end automatically as you add projects. Hovering Work in the top bar also lists every project.
- **Project pages:** each opens from its panel with the photo expanding into a full width header, plus a full screen photo viewer and a Next project link
- **Photos:** on a computer, hovering any photo lifts it out as a larger print so it's easier to see (the Outside of engineering photos also tilt like a scrapbook); clicking opens the full screen viewer. On phones, a tap opens the viewer.

## Direct links

Add these to the end of the site URL:

- `#about` opens the About page
- `#work` opens the Work page
- `#ledisco-sat` LEDISCO Sat, senior design CubeSat
- `#phantom-10k` Phantom 10k
- `#aurelian` Project Aurelian
- `#golden-rose` L1 Rocket
- `#pin-calculator` Motor Case Pin Calculator
- `#rice-camp` Aerospace Engineering Camp at Rice University

## Adding a new project

Each project is one `<article>` in `index.html`. Its Work panel, Work menu entry, page header, photo viewer, and "Next project" link are built automatically, so there's no separate menu to edit.

1. Put new photos in `img/` and new videos in `media/`. Lowercase names with hyphens work best, like `img/cubesat-assembly.jpg`.
2. In `index.html`, find the commented template near the bottom, labeled "ADDING A PROJECT".
3. Copy it in next to the other project articles and fill in:
   - `id`: the direct link name, like `cubesat`, which becomes `#cubesat`
   - `data-tab`: the project name on its card
   - `data-meta`: the small date line on the card
   - `data-order`: where it sits in the Work reel (1 is first)
   - `data-size`: only used for the Next project tile; `xl`, `tall`, `wide`, or `one`
   - `data-tag`: a short area label, like Propulsion
   - `data-summary`: one sentence shown on its Work panel
   - `data-cover`: the Work panel and page header photo. Add `data-credit="Photo: Name"` to show a small photo credit on it. Add `data-fit="contain"` to show a white drawing as a dark blueprint.
4. Fill the page with any of the building blocks the other pages already use:
   - `strip`: the Role, Date, Team and Tools summary
   - `hero`: a full width lead photo
   - `mods`: spec numbers
   - `parts`: CAD and photo pairs
   - `media`: a video beside two photos
   - `timeline`: a test log, where each entry is marked pass (`ok`) or problem (`bad`)
   - `failure`: a failure analysis panel
   - `rows` and `steps`: decisions, trades, or a sequence
   - `mgrid` and `gallery`: photo grids

## Design notes

- Home and Work are always a night sky, and the top bar is always dark. Project pages follow the visitor's light or dark setting.
- Red is reserved for the current page marker and for real anomalies or failures.
- Keep every number exactly as tested or simulated.
