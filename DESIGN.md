# ANTTECH site — design system

The studio site is an iPhone home screen. On a computer a phone sits on the page with the studio pitch beside it; on a real phone the page itself is the home screen. Each game is an app icon. Tapping one springs its app open out of the icon; swiping up on the bar (or Esc / ×) shrinks it back in.

## World
- **Wallpaper:** near-black (`--bg #0d0d10`) with slow drifting light in the game colours, 34–45 s cycles, transform only.
- **Game colours,** one per game, never reused: Tap Against Time `#4b2a8c`, Dockside `#178f92`, Circuit Weave `#5a626e`, Raccoon Raid `#b5531f`.
- **Glass:** widgets, dock, dash, app windows and the close button are frosted glass (`.glass`): 22px blur, lit top edge, and a soft light that follows the pointer. App windows are frosted over the blurred home screen. Every icon has a glossy top light and one sweep of light on load.
- **Dash (≥1100px):** a GNOME-style glass dock down the left edge with the four games, About and Privacy. Icons swell as the pointer passes, show a name tip, bounce when launched, and get a dot while their app is open. The nine-dot button turns the home screen.
- **Home screen, page 1:** a studio widget, a "NEW" feature widget for the latest game, the four game icons, a Release board widget (status pills: green live, amber in review, orange in testing), page dots, and a glass dock (About, Privacy, Mail, Instagram) using our own glyphs, not brand logos.
- **Home screen, page 2:** Instagram and Mail widgets and an "In the lab" widget (never name unannounced games).
- **Apps:** App Store–style pages: icon, name, status, a blue GET button only for downloadable games (grey "Coming…" pill otherwise), description, screenshots, privacy link.
- **Ink:** `--ink #f5f3ee`, `--ink-soft #b9b6ae`.

## Type
- Display: Bricolage Grotesque, self-hosted variable woff2 (`assets/fonts/bricolage.woff2`, OFL), condensed (`font-stretch` 78–85%), weight 800.
- Body: the platform UI stack.

## Motion
- Open/close is a JS spring on one progress value (damping 0.86 / response 0.46 open, 1.0 / 0.36 close): clip-path grows from the icon rect, the icon art cross-fades out, the home screen scales to 0.9 and dims. Interruptible; a swipe hands its velocity to the spring.
- The two home pages are faces of a cube: drag sideways (or the dots, arrow keys, the dash's nine-dot button) and it rotates with a slight zoom-out, rubber-banding at the ends.
- Wobbly windows: apps squash and stretch as they open and close, and drift and skew with a sideways drag on the home bar, on loose springs (damping 0.3–0.45).
- On computers the phone tilts up to 4–5° toward the pointer with a glare across the glass.
- Icons spring in on load with a 45 ms stagger. Press-down shrinks an icon to 0.88.
- `prefers-reduced-motion`: apps open and close instantly, wallpaper, stagger, light sweep, wobble, tilt and magnification stop; the cube switches instantly.

## Rules
- A game that can't be downloaded yet never gets a GET button.
- Never invent ratings, download counts or quotes.
- Without JavaScript every app page shows in full under the home screen.
- Deep links: `/#tap-against-time`, `/#dockside`, `/#circuit-weave`, `/#raccoon-raid`, `/#about`, `/#privacy`.
- Adding a game: a new colour, its icon at 256px webp in `assets/games/`, two 414×900 screenshots (landscape: 900×414 in `.shots.wide`), an icon on the grid, a Release board row and an app `<article>`.
