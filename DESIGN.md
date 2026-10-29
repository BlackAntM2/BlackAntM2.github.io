# ANTTECH site — design system

The studio site is a cartridge shelf on a black pegboard wall. Each game is an upright plastic cartridge in its own colour, standing in a plywood ledge, with a price tag hanging underneath. Pulling a cartridge lifts it out of its slot and shows that game below.

## World
- **Wall:** matte black pegboard (`--peg #161615`), punched holes every 28px (`--peg-hole #050505` with a `--peg-rim #262624` lip). Matches the black ant mark.
- **Ledge:** plywood (`--ply #dcae72`, front edge `--ply-edge #b9864a`, top grain `--ply-grain #c89a5e`). Its front face hides the cartridges' feet.
- **Cartridges:** one body colour per game, never reused: Tap Against Time `#4b2a8c`, Dockside `#178f92`, Circuit Weave `#5a626e`. Grip ridges across the top, a cream label (`--label #fbf7ee`) with the real app icon and the name.
- **Tags:** the one primary action style. Cream tag (`--tag #fbf7ee`) with black text and a punched hole; outlined tag (`.is-waiting`) for anything not yet downloadable.
- **Ink:** `--ink #f3efe6` text, `--ink-soft #b8b1a3` secondary.

## Type
- Display: Bricolage Grotesque, self-hosted variable woff2 (`assets/fonts/bricolage.woff2`, OFL), set condensed (`font-stretch` 78–88%), weight 800, tight tracking.
- Body: the platform UI stack, 17px.

## Motion
- One moment: the cartridge lift, `transform` over 420ms on `cubic-bezier(0.16, 1, 0.3, 1)`, with the game panel fading up as it lands. Off under `prefers-reduced-motion`.

## Rules
- A game that can't be downloaded yet never gets a filled tag.
- Never invent ratings, download counts or quotes.
- Without JavaScript every game panel shows in full.
- Adding a game: a new cartridge colour, its icon at 256px webp in `assets/games/`, two 414×900 screenshots, a tag, and a panel.
