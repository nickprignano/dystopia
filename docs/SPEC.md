# Dystopia spec (v1)

Status: approved by the owner (2026-11-10). Builds start when it's this game's turn. Name **Dystopia** (owner's
pick, 2026-11-10). Numbers checked by a simulation; red-teamed by Fable twice,
once for the game and once for the drone-and-cameras theme (fixes listed at the end).

## What it is

An original one-button flyer for `dystopia.prignano.ai`, in the genre the 2013 phone hit
made famous (and the 2000s helicopter games started). **You fly a little toy drone down a sunny
suburban street.** It sinks all the time; each tap gives it a burst of thrust, and the street
scrolls toward you. Street cameras stand on poles and hang from overhead arms; fly through the
gap between them. Bump a camera, a pole or the road and the run ends. Your score is the number of
gaps you pass.

**The twist: race a swarm that learns to fly.** A swarm of 48 faint rival drones flies the same
street beside you. Each one has a tiny brain, a neural network of 43 numbers, that decides when to
thrust. At first they thrust almost at random and drop out of the sky. After each of your runs,
the drones that got farthest become the parents of the next generation, with small random changes.
Somewhere around your 20th run (anywhere from the 3rd to the 50th in our simulation) the best of
them starts flying far past where you crash. The race is how long you stay ahead, and the results
screen shows the learning: the best drone's brain, and a chart of you against your swarm,
generation by generation.

That fits prignano.ai, an AI site. The method is real: a tiny neural network per drone, evolved by
a genetic algorithm (often called neuroevolution), all on the device. The swarm learns to fly the
street; it does not learn from you (that was Infinite Recursion's twist).

The look is a flat, bold-outlined cartoon suburb: bright flat colors, chunky shapes, a sunny sky,
and a few neighbors going about their day below. It's our own cast and street (see "The look").

Plain JavaScript and canvas, no build step, no dependencies. The repo is the site. Installable as
an app (PWA) from day one. Made for all ages: kids will play it.

## Decisions so far

| # | Question | Answer |
| --- | --- | --- |
| 1 | Kind of game | An original one-button flyer in the genre of the 2013 phone hit, with our own name, art and sound, and a twist (owner, via the coordinator, 2026-11-10) |
| 2 | Twist | Race an evolving swarm of tiny neural-network drones (default; open question 2 has others) |
| 3 | Theme | The player is a toy drone, the obstacles are pole-mounted street cameras, the setting is a neighborhood (owner, 2026-11-10). Cameras are generic, with no real company's look, name or logo |
| 4 | Look | A flat, bold-outlined cartoon suburb with an original cast and street (owner, 2026-11-10). Traits of any existing show stay out (below) |
| 5 | Name | **Dystopia** (owner, 2026-11-10): a cheerful cartoon street where the cameras watch you, which is the joke. A 2005 sci-fi shooter mod on Steam shares the name; accepted for a hobby site, as Infinite Recursion accepted an itch.io namesake. The card leads with "Race a swarm that learns to fly". Earlier working name: Fitness Function |
| 6 | Home | Its own public repo `nickprignano/dystopia`, served at `dystopia.prignano.ai`, deployed by Workers Builds on each merge to `main`. The owner creates the repo and adds the domain. Launch ends with the `content/games.json` PR in `prignanodotai-web` |
| 7 | License | MIT. Our own code, art and sound |
| 8 | Audience | All ages. Nothing leaves the device |

## Prior art and licenses

Checked 2026-11-10: our KB prior-art script (nothing in our KBs), a GitHub search of the most
starred browser clones (licenses from the GitHub API), and the news on the original's trademark.

| Source | License | What we take |
| --- | --- | --- |
| The original phone game (2013, pulled by its maker in February 2014) | Closed, all rights reserved. Its trademark was later registered by others and bought by a foundation in August 2024 for a relaunch the original maker publicly disowned ([mobilegamer.biz](https://mobilegamer.biz/flappy-birds-new-owner-attempts-to-clear-the-air-and-flaps-back-at-dong-nguyen/), [VGC](https://www.videogameschronicle.com/news/original-flappy-bird-creator-denounces-crypto-backed-re-release)) | Genre mechanics only: gravity, tap to lift, gaps to fly through, one point per gap. Nothing of its name, look, sounds or screens (list below). The trademark is actively held, so we stay well clear |
| The older chick-and-cactus Facebook game (2009) | Closed. The 2024 foundation says it holds exclusive rights | Nothing. Named in the words test only |
| Apple and Google app review, 2014 | n/a | Both rejected new games with the original's first word in the title ([MacRumors](https://www.macrumors.com/2014/02/17/flappy-bird-clones-rejected/), [TouchArcade](https://toucharcade.com/2014/02/17/apple-and-google-are-rejecting-flappy-games)). That word never appears in our name, page, README, manifest or games.json card |
| [ssusnic's machine-learning flyer](https://github.com/ssusnic/Machine-Learning-Flappy-Bird) (1.8k stars) | MIT | The idea of a population of tiny networks (2 inputs, 6 hidden, 1 output) evolved by a GA to play the genre. Credited in About. No code or art; ours is written fresh with a different network, GA and rules |
| [ellisonleao/clumsy-bird](https://github.com/ellisonleao/clumsy-bird) (1.6k stars) | GPL-3.0 | Nothing. GPL would bind our MIT repo |
| Other popular browser clones (CodingTrain, kubowania, aaarafat, CodeExplainedRepo and others) | Mostly no license; most ship the original's sprites and sounds | Nothing |
| Real makers of neighborhood plate-reading cameras and of drones | Their names and product looks are their own | Nothing but the everyday ideas of a camera on a pole and a toy quadcopter. Names in the words test; looks excluded below |
| Infinite Recursion and Zero Sum (ours) | MIT | Small pieces copied freely: flash limiter, banned-words test, seeded pure game module tested in Node, `sw-version.mjs`, `wrangler.jsonc`, `docs/DEPLOY.md` |
| Pinball PR #7 (ours) | GPL-3.0-only | The PWA recipe as written in ai-brain's prompt library ("Make a static web game installable"), rewritten here |

### What we don't take from the original game

Its name or any word of it, or its bird's name; a bird at all; green pipes with caps; the
brick-and-bush skyline and striped ground; the "Get Ready" screen with the tapping hand; the white
flash when you crash; bronze, silver, gold and platinum medals at 10, 20, 30 and 40; its sounds;
its pixel score digits.

### The look

A drawing style can't be owned, but a recognizable cast, place or trade dress can. So the look is
described by what it is, and anything that would make a viewer name an existing cartoon is out.

- **It is:** thick dark outlines on the things that matter, flat colors with no gradients, simple
  chunky shapes, a sunny sky with thin streak clouds, a tidy street of small houses, and a few
  neighbors with cartoon proportions, drawn with no skin color at all (owner, 2026-11-10): each
  is a flat silhouette in one scenery color from the palette, with no face, which also keeps the
  street from reading as anyone's cast.
- **It isn't (traits of any existing show):** yellow skin or a yellow hero; big round white eyes
  with dot pupils; overbites or four-finger hands; spiky or tall blue hair; a family of five or a
  pear-shaped bald dad; puffy white clouds on flat blue; a pink or orange house with a brown roof
  and attached garage; a cooling-tower or factory skyline; any real or famous town name, landmark,
  shop, logo font or catchphrase; parody of anyone. No text in the scene at all.
- A test can't judge likeness, so the owner looks at the art in the build 1 PR before it merges,
  with this list next to it.

## How it looks and feels

### The street

- **Scale:** houses and lawns fill the bottom 35 to 40% of the field; the band you fly in is
  mostly sky. No vertical post in the scenery is taller than the house eaves, and there are no
  streetlights, utility poles or tall tree trunks, so nothing in the background looks like the
  poles that end a run.
- **Two kinds of line:** the drone and everything deadly (camera boxes, arms, poles, the road) get
  the 3 px dark outline and one reserved dark fill. Scenery gets thinner, lighter outlines and sits
  in a narrow brightness band per palette (pale by day, dark at dusk), so the things you must read
  stand out from a busy street.
- **Palettes** in `data/palette.json`: day for light mode (blue sky, green lawns, warm houses) and
  evening for dark mode (dusk sky, a few lit windows, at most 8 on screen).
- Three layers scroll at different speeds: far rooftops and trees, then houses, fences and lawns,
  then the road and sidewalk. The back layers are drawn once per session (one scenery seed per
  session) to offscreen tiles, so a frame is mostly copies and a restart doesn't hitch.
- **Neighbors** in the house layer: three short loops (mowing, watering, waving at the street), at
  most 3 on screen, as faceless one-color silhouettes. They don't react to you. No people in windows.
- **Cameras:** a gap is made of two cameras, one on a pole rising from the sidewalk and one on a
  rigid arm reaching down from above the field. Each is a generic white bullet camera with a
  sunshade on a bracket, a small status light that stays steady (never blinks), no solar panel, no
  logo. The lens turns to follow your drone as it approaches (in Watch, the champion), the gentle
  joke of the game.
- Parked cars have blank plates.
- The playfield keeps a fixed 9:16 shape scaled to fit, centered with margins on wide screens.
  Canvas backing store capped at 2× pixel ratio.

### Your drone and the swarm

- **Your drone** is a chunky toy quadcopter with prop guards, in one bright color that isn't
  yellow, white or grey, with a little face (two bean eyes) on its body and no gimbal or camera.
  It's drawn within 16 u of its center sideways and 11 u up and down, so the rotors barely
  overhang the hit circle and never visibly pass through a camera. Rotors are steady translucent
  discs while thrusting (never alternating frames); it tilts with its speed. Drawn last, on top.
- **The swarm**: 48 rival drones drawn as plain outlines (no fill, no face) at about 40% opacity,
  pre-rendered once to a small image and stamped with `drawImage`, so 48 cost little on a cheap
  phone. **The champion** (last generation's best drone) has a solid outline and a short trail, so
  there is one rival to watch, not a cloud. A drone that crashes drifts down and fades. Settings
  has **Show swarm** (on by default).

### Tone

Playful and neutral. The cameras are a sight gag (they turn to watch you, a crash says "Bonk!"),
not a message: no police, no plate reading, no news or real towns. About says simply: "This game
records nothing about you."

### Flash safety (from Zero Sum)

No full-screen flashes. A crash is a short wobble of your drone and a 150 ms outline pulse on the
camera you hit, never a white screen. Camera status lights never blink. Nothing flashes saturated
red. The shared limiter allows at most 3 glow events a second.

**Stripes:** no repeating run in any layer has more than 5 light-dark pairs above 1.5:1 contrast,
which covers fences, siding, shingles, garage doors, crosswalks, mown lawns and rows of lit windows;
the road has no dashed line. A test checks the layer tiles.

Reduce effects, or `prefers-reduced-motion` (watched live), turns off the wobble, pulse and neighbor
loops, and freezes the back layers in place.

### Controls

- **Phone:** tap anywhere on the playfield to thrust. Each new touch thrusts, so two thumbs work.
  Thrust fires on `pointerdown`, not on click. Pause is a 44 px button outside the playfield.
  `touch-action: none`, no double-tap zoom or pull-to-refresh.
- **Keyboard and mouse:** Space, Up or W thrusts (held keys don't repeat), click thrusts, P pauses,
  M mutes. Focus leaves the menu buttons when a run starts, so Space never presses a button and
  thrusts at once.
- A run starts on your first tap; until then the drone hovers in place. Pause freezes you and the
  swarm together. The game pauses when the tab is hidden and resumes with a 3-second countdown.
- The first run shows one line over the sky: "The outline drones are your swarm. They learn a
  little after every run."

### Easy

An **Easy** switch for young kids: gaps 30% taller, the street 20% slower, the first 5 gaps extra
wide. There is one swarm; it flies whichever street you fly. Best scores and "caught you" records
are kept per mode. (A swarm trained on Normal flies Easy perfectly; one trained on Easy is weaker
on Normal, so a kid's swarm may surprise a grown-up on Normal.)

### Sound

Synthesized with the Web Audio API, so there is nothing to license: a short rotor whir for each
thrust, a soft camera-shutter tick for each gap passed, a plastic bonk for a crash, and a two-note
chirp, at most once a run, when the champion passes your score. The swarm makes no other sound. Muted until the first tap or key; the
mute setting is saved on the device.

### Accessibility

Menus, results and the chart are real DOM text with an `aria-live` region for results; the chart
has a text summary ("Generation 12. Swarm best 17, your best 21"). It's a reflex game with no
screen-reader mode, and How to play says so.

## The rules

### Physics

One pure module (`src/sim.js`) runs the world in fixed 1/120 s steps, whatever the screen's refresh
rate, so a 60 Hz laptop and a 120 Hz phone play the same game. Drawing interpolates between steps.
Starting numbers live in `data/tuning.json` (world units; the field is 360 × 640):

| Setting | Normal | Easy |
| --- | --- | --- |
| Gravity | 1,500 u/s² | 1,500 |
| Thrust sets upward speed to | 420 u/s | 420 |
| Fastest fall | 600 u/s | 600 |
| Shortest time between thrusts | 0.1 s | 0.1 |
| Street speed | 140 u/s | 112 |
| Camera spacing | 220 u | same |
| Gap height (between the two camera boxes) | 150 u | 195 |
| Gap center moves at most | 120 u from the last gap | 100 |
| Gap center kept between | 120 u and 470 u | 145 u and 470 u, so the upper camera stays on screen |
| Drone hit circle | radius 11 at the body (rotors overhang it) | same |

**Obstacle shapes** (what collides): each camera box is 60 × 30 u at the edge of the gap. The
lower camera's pole and the upper camera's arm are each 20 u wide, flush with the box's front edge,
running to the road and to the top of the field. Every colliding shape is at least 12 u wide, and
each is drawn exactly as it collides.

A burst lifts the drone about 59 u over 0.28 s. The hit circle covers the drone's body; the rotor
tips overhang it, so near misses feel fair. The top of the field is a ceiling: the drone stops
there, it doesn't crash.

**Why every street is flyable:** between two cameras there is 160 u of open air, 1.1 s at Normal
speed. Climbing the largest allowed change of 120 u takes about 0.6 s of thrusting, and falling it
takes less. The simulation backs this up (below).

### Street

Each run gets a seed. Cameras come from a seeded generator, so a run replays exactly in the same
browser (`?seed=N`, for tests and bug reports). You and the swarm always fly the same street. The
scenery (houses, neighbors) comes from a second seed and never affects play.

### Scoring and records

One point per gap passed. Kept on the device: your best (per mode), your last 50 runs for the
chart, the generation your swarm first beat your best (per mode), and the swarm. No medals, no
top-10 table: the chart is the record.

## The swarm

### The brain

Each drone has a small neural network, `src/brain.js`:

- **Inputs (4):** the drone's height, its vertical speed, the horizontal distance to the next
  camera pair, and the height difference to that gap's center, each scaled to about -1 to 1.
- **Hidden layer:** 7 neurons (tanh). **Output:** 1 neuron (sigmoid); above 0.5 means thrust.
- That's 4×7 + 7 + 7 + 1 = 43 weights and biases.

**What's the same and what isn't**, said plainly in How to play and About: the swarm has the same
physics, the same hit circle and the same 0.1 s between thrusts as you. It looks at only the next
gap (you can often see two), and it sees the world 0.2 s late. But it reads exact numbers 120
times a second and never tires or mis-taps. It's a tiny neural network, not an AI that thinks.

### Evolution

- **Population:** 48. A brand-new swarm starts with random weights (normal, sd 1).
- **Fitness**: distance flown, plus a small bonus for being close to the next gap center
  when it crashed, so drones that crash at the same camera still rank.
- **Next generation:** the 3 best are copied unchanged (elitism). The other 45 each have two
  parents picked by tournament (best of 3 random drones), mixed weight by weight (uniform
  crossover), then each weight changes with probability 0.1 by a normal step (sd 0.4), clamped to
  ±4.
- **One generation per run, always finished.** When you crash, the drones still flying finish the
  street headless, in milliseconds, until all have crashed or the best reaches 100 gaps. Your run
  length never cuts the swarm's learning short. Then the generation is bred and saved. A **Watch
  them fly on** button replays the rest of that generation at normal speed; otherwise the results
  come straight up.
- **Hatching:** a new swarm is trained for 8 generations headless (well under a second) behind a
  short "Charging your swarm" moment, so even run 1 has a few drones that clear a gap or two.
- **Seeded in tests:** the GA uses its own seeded generator, so tests replay a swarm's history
  exactly. In the game a swarm's history also depends on every street seed, so it isn't
  replayable there, and the spec doesn't claim it.

### Watch

A mode with no player, where the swarm trains by itself while the page is open and visible:

- **1×** draws the street and the swarm as in play.
- **Fast** doesn't draw the street at all (scenery scrolling at high speed would strobe). It runs
  generations headless and shows only the generation counter, the champion's brain and the chart
  updating, about 5 generations a second.
- Every generation ends at 100 gaps, so a trained swarm never runs forever.

### Persistence

The swarm is 48 × 43 numbers stored as a base64 `Float32Array` (about 11 KB), with a format
version, the generation number, the GA seed and the best distance per generation. On load it's
checked (version, length, every number finite) inside try/catch; anything wrong starts a new swarm
quietly. **New swarm** in settings starts over (with a confirm). Two open tabs: the last one to
save wins; that's accepted, not handled.

About says plainly that the swarm lives in this browser only: Safari can clear a site's storage
after 7 days without a visit, and an installed app on iPhone keeps separate storage from the
Safari tab. Installing the app is the best way to keep a swarm.

### Results screen

After each run:

1. Your score and best, the champion's distance this generation, and the generation number, with
   one line that fits where the swarm is:
   - early: "3 drones made the first gap, up from 0"
   - closing in: "Your swarm's best flew 9. You're still ahead"
   - the first time it beats your best: "Your swarm caught you at generation 17"
   - after: "Your swarm out-flew you by 30 this time"
2. **The champion's brain:** the network drawn as lines, inputs labeled on the left (height, speed,
   distance, gap), thrust on the right. Line thickness shows a weight's size; positive weights
   solid, negative dashed, so color is never the only cue.
3. **You vs your swarm:** a line chart over the last 50 runs, your score and the swarm's best as a
   3-generation rolling best, generation on the x axis.
4. **Fly again** (the first fresh tap after 0.8 s, so a held tap from the crash can't skip it).

### Making sure it learns

Before writing this spec we simulated the physics and the swarm in Node with the numbers above
(2026-11-10, a throwaway script kept outside this repo):

- **Every street is flyable.** A one-line pilot (thrust when below the gap and falling) cleared
  500 gaps on all 200 seeds, Normal and Easy, with the camera shapes above. What makes it hard for
  people is timing.
- **The swarm learns, unevenly.** Over 40 seeded swarms, the best drone first reached 20 gaps after
  a median of 21 generations (fastest 3, slowest 50) with simple full-height obstacles; with the
  final camera shapes, 20 swarms gave a median of 21 (3 to 50). After that it often slips back for a while before it holds. With 24
  drones, 1 swarm in 10 to 20 stayed stuck past generation 60; 48 fixed it. Cutting a generation
  short at the player's crash slows learning badly for a weak player, which is why generations
  always finish.
- **Where button-mashers crash.** 4,000 random tappers: 47% on an upper arm (mashers sit against
  the ceiling), 34% on the road, 13% on a camera box, 6% on a pole. That's why the arm is as wide
  and as visible as the pole; an earlier 4 u cable drew the most deaths and was the hardest thing
  to see.

So the swarm isn't a steady opponent you trade wins with. It's a clock: the record that matters is
the generation it caught you, and **New swarm** starts the race again.

## Privacy (kids will play)

No accounts, names, analytics, ads, trackers or third-party scripts. The prignano-theme header
loads from jsDelivr pinned to a commit SHA with a subresource integrity hash and is cached for
offline use. Settings, scores and the swarm stay in `localStorage`; **Delete my data** in settings
clears them. No network calls beyond the pinned theme files. The About screen says this in plain
words, with the MIT notice, a link to the source and the credit for the learning-swarm idea.

## Installable app

Pinball PR #7's recipe: manifest (`display: standalone`, portrait), original icons (the toy drone
mid-thrust on a sky-blue square, in any, maskable and Apple touch sizes), iOS home-screen tags, a
service worker that caches every served file with its list stamped by `tools/sw-version.mjs` and a
test that fails when the list is stale, an Update button on the title screen, safe-area padding,
the site header hidden in the installed app, and sound resumed after an iPhone locks.

## Hosting

Cloudflare Workers static assets, no Worker script: `wrangler.jsonc` named `dystopia`,
`.assetsignore` leaving out tests, tools and docs, Workers Builds deploying each merge to `main`.
No cost: static assets are free and unlimited. The owner creates the repo and adds the custom
domain. Claude writes `docs/DEPLOY.md` the way Infinite Recursion's is written and changes nothing
on the account without his yes. The last step of `docs/DEPLOY.md` is the `content/games.json` PR:
the game goes in hidden with an empty url when the repo is created, and the launch PR sets the url
and `live`. The card text and the repo description get the same banned-word check by hand before
those PRs.

## Files

```
index.html, styles.css, manifest.webmanifest, sw.js, _headers, icons/
src/sim.js        world, physics, street, collisions (pure, seeded)
src/brain.js      the network (pure)
src/evolve.js     fitness, selection, crossover, mutation (pure, seeded)
src/swarm.js      runs 48 brains in the sim (typed arrays, a ring buffer for the 0.2 s delay),
                  hatching, finishing a generation headless, save and load
src/scene.js      houses, lawns, neighbors, offscreen parallax layers (seeded, no effect on play)
src/draw.js       drone, cameras, swarm sprite, flash limiter
src/charts.js     the brain drawing and the you-vs-swarm chart
src/input.js      pointer and keyboard
src/audio.js      Web Audio sounds, mute
src/main.js       screens: title, play, results, watch, settings, about
data/tuning.json  physics, street, Easy, GA numbers
data/palette.json day and evening palettes
tools/sw-version.mjs, tools/make-icons.mjs
wrangler.jsonc, .assetsignore, docs/DEPLOY.md
test/             node --test
```

ES modules loaded directly by the browser. Tests and tools need only Node.

## Tests

`node --test` covers:

1. **Physics:** the same seed and tap times give the same run whether the screen draws at 30, 60
   or 144 Hz; taps closer than 0.1 s are ignored; the ceiling stops the drone; the hit circle and
   obstacle shapes, not the drawing, decide crashes.
2. **Fair street:** the one-line pilot clears 500 gaps on each of 200 seeds, Normal and Easy, with
   the 0.1 s limit; the generator never moves a gap center more than the limit or outside its
   band; the scenery seed never changes a run; every colliding shape is at least 12 u wide; and
   a random-tapper tally of crash causes is printed so shape changes stay honest.
3. **Brain and evolution:** the network matches a hand-worked example within 1e-9; the population
   stays 48; the 3 best survive unchanged; weights stay within ±4; a seeded swarm's history repeats
   in Node.
4. **It learns:** 20 seeded swarms trained with no player, each generation run to its full horizon:
   the median reaches 20 gaps (Normal) within 30 generations, and at least 18 of 20 within 60. Also:
   hatching runs 8 generations, and "caught you" is recorded once per swarm per mode.
5. **Same rules:** a swarm drone and the player go through the same `sim.step`; nothing else moves
   a drone.
6. **Storage:** a saved swarm loads back the same; a truncated, wrong-version or non-finite save
   starts a new swarm without throwing.
7. **Words:** an encoded banned list appears in no shipped file, the README or the manifest: the
   original game's title and its first word alone, its bird's name, its maker's name and studio,
   the 2024 foundation's name, the older chick game's title, a well-known cartoon's title, family
   name, town and studio, the best-known plate-camera company's name and the bare word "flock" (we
   say "swarm"), and drone makers' names. No bird names for anything. The About credit names
   ssusnic's project in words and links it by one exact URL the test allows; `docs/` isn't scanned.
   Commit messages, PR titles and branch names get the same check by hand.
8. **Palette:** in both palettes, the drone's outline and the obstacle fill meet 3:1 contrast
   against every scenery color, and the swarm outline meets 2:1 after blending at its opacity;
   scenery colors stay in their brightness band; the palette has no skin colors (neighbors use a
   scenery color); the drone color is not a saturated yellow (hue 45 to 65 degrees, saturation
   above 50%).
9. **Flash and stripes:** never more than 3 glow events a second; Reduce effects gives zero;
   camera lights never change; Fast Watch draws no street; no layer tile breaks the stripe rule;
   at most 8 lit windows on screen.
10. **PWA:** the service worker's file list is current.

`Math.tanh` and `Math.exp` can differ in the last bits between browsers, so tests run in Node and
a `?seed=N` replay is only promised in the same browser.

**Done means:** all tests pass in CI, and before each build PR the build thread runs a scripted
Playwright check (not in CI, like Infinite Recursion) at phone and desktop sizes: hatching, a
fixed-seed run that passes a few gaps and crashes, Watch them fly on, the results screen with the
brain and chart, Watch at 1× and Fast, day and evening palettes. The owner checks the art against "The look" in
build 1. Installing, offline play and a frame-rate check of the
street plus 48 drones on a real low-end phone are manual checks in `docs/DEPLOY.md`.

## Pull requests

After the owner creates the repo:

1. **Spec:** this file as `docs/SPEC.md`, `AGENTS.md`, `CLAUDE.md`, MIT `LICENSE`. Plus the hidden
   `games.json` entry in `prignanodotai-web`.
2. **Build 1, the game:** sim, street, cameras, drone, scenery and neighbors, palettes, input, Easy,
   scores, pause, flash limiter, CI, tests 1, 2, 7, 8 and 9. Playable solo. The owner's art check.
3. **Build 2, the swarm:** brain, evolution, hatching, headless finish, results screen with brain
   and chart, Watch, persistence, tests 3 to 6, and any tuning the learning test needed.
4. **Build 3, finish:** sound, the PWA recipe, About and credits, `wrangler.jsonc`,
   `docs/DEPLOY.md`, test 10, polish.

Then the Cloudflare setup (with the owner's yes) and the launch `games.json` PR.

## Not in v1

A shared leaderboard, racing a friend online, more than one swarm, naming drones, a swarm that
learns from your flying, changing the network shape, NEAT (growing networks), moving cameras or
power-ups, neighbors who react to you, pets, more neighborhoods, any text in the scene, Watch speeds beyond 1× and Fast, music,
gamepad.

## Open questions

None. The owner decided all of them on 2026-11-10: name **Dystopia**; neighbors with no skin
color; and the defaults for the rest (the evolving swarm as the twist, one swarm that keeps
learning across runs and visits, a playful and neutral tone).

## Fable red team 1 (2026-11-10, the game)

14 findings, all folded in:

1. Cutting a generation at the player's crash slowed learning badly for weak players: a 3-second
   player's median went from 21 to 46 generations, and 5 of 20 never got there. → Every generation
   finishes headless to its full horizon; Skip became an optional replay.
2. "Caught you" was decided by how long you lasted that run. → Fixed by 1.
3. Watch at 16× strobed and never ended once trained. → Watch is 1× or Fast; Fast draws no world;
   generations end at 100 gaps.
4. Runs 1 to 10 were 48 grey shapes dropping in the first second, then a 15 s wait. → Hatching (8
   headless generations), a highlighted champion, early results lines, a first-run explainer, no
   waiting.
5. "Once it gets there it flies 100 gaps" wasn't what the simulation shows. → Wording fixed; the
   chart plots a 3-generation rolling best.
6. "Same rules as you" overclaimed. → A plain list of what's the same and what isn't.
7. The words test would have failed on the About credit and missed several names. → Credit by exact
   URL; list, scope and dates fixed.
8. The first look still read as a reskin of the original. → Reworked (now the drone street).
9. The name reads as a workout app. → Card leads with the twist; alternatives listed.
10. Persistence gaps (Safari clearing, size, validation, a false replay claim). → Fixed as above.
11. Cross-browser math, tolerances, brittle thresholds, a slow sim. → Fixed as above.
12. One swarm, two modes, no rule for records. → Records per mode.
13. Stripe patterns, Space on a focused button, a repeating call, ceiling wording. → Fixed.
14. Scope trims and missing pieces. → Trimmed and added.

## Fable red team 2 (2026-11-10, the drone, cameras and cartoon look)

15 findings, all folded in:

1. The 4 u overhead cable killed the most button-mashers (44% in Fable's tally) and was the hardest
   thing to see. → A 20 u rigid arm flush with the box; every colliding shape at least 12 u and
   drawn as it collides; a crash-cause tally in test 2.
2. One drone color can't reach 3:1 against a whole bright street, and obstacles weren't tested. →
   Reserved dark fill and thick outline for the drone and deadly things, scenery in a brightness
   band, contrast tested both ways and for the swarm.
3. Streetlights, utility poles and trunks would look like deadly poles. → None taller than the
   eaves; houses fill the bottom 35 to 40%.
4. The public spec recorded intent to imitate a show. → The look is described positively; the
   exclusions are "traits of any existing show".
5. More traits that would read as that show (yellow drone, puffy clouds, the house, the skyline,
   the family, hands), and a skin test that checked a label. → Added to the list; the test checks
   hue and saturation.
6. Camera-company gaps: the bare word, bird names, commit text, and the real unit's look. → Banned
   as a whole word, no bird names, hand check on commits, a generic white bullet camera.
7. The drone could read as a real brand or a spy camera. → Prop guards, no gimbal or camera, not
   white or grey; no people in windows.
8. "Spotted!" framed cameras as something to hide from, and the privacy line was a message. →
   "Bonk!", and "This game records nothing about you."
9. The stripe rule missed windows, siding, shingles and lawns, and rotor blur could flicker. → One
   numeric stripe rule tested on the tiles, a lit-window cap, steady rotor discs.
10. Easy pushed the upper camera off screen. → Easy's lowest gap center is 145 u.
11. Wide rotors would look like they pass through cameras. → Drawn size capped at 16 by 11 u.
12. Performance underspecified. → Swarm stamped from one sprite, scenery tiles once per session,
    reduced motion freezes rather than hides.
13. Leftovers from the bird version. → Fixed.
14. Overbuilt: shop names, a constant hum, pets and a bike loop. → Cut.
15. The sim misses mashers and perceived fairness. → The crash-cause tally above, and the owner's
    art check.
