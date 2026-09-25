# Gravity Wars

A browser remake of the classic 1989 artillery game *Gravity Wars*, built for use in science classrooms.

Two ships sit in a field of planets. Players take turns firing a missile by choosing an **angle** and a **launch speed**. Every planet pulls on the missile with gravity (an inverse-square force), so shots curve, slingshot and sometimes orbit. Old shot trails stay on screen, so players learn by adjusting from their last attempt. The first to hit the other ship wins the round.

## How to run it

**Just open `gravity-wars.html` in any modern browser** (Chrome, Edge, Firefox or Safari on a desktop, laptop, Chromebook or iPad).

- It is a single file with no installation and no internet connection needed.
- To share it with students, copy the file to a USB stick, a shared drive or your LMS. Students download it and open it.
- Settings are remembered per browser.

## How to play

| Control | What it does |
|---|---|
| **Angle** box / slider | Direction to fire, in degrees. **0° = right, 90° = up, 180° = left, 270° = down**, the same for both players. Decimals are fine (e.g. `37.25`). |
| **Speed** box / slider | Launch speed, from 0 to 100. |
| **FIRE** / `Enter` | Fire. While a shot is flying, the button becomes **Skip**. |
| `Tab` | Jump from the angle box to the speed box. |
| `←` `→` / `↑` `↓` | Adjust angle / speed by 1. Hold `Shift` for big steps or `Ctrl` for 0.1 steps. |

A shot ends when it hits a planet or a ship, leaves the play area, or burns out. A shot that is off-screen burns out after 25 seconds, but one still on screen keeps flying (it might loop back!) for up to 90 seconds. Use **Skip** to jump to the end. **You can hit your own ship**, and that point goes to your opponent.

## The physics

- **Planet colour shows density**, from red (low, ρ = 1) through orange, yellow, green and cyan to blue (high, ρ = 5).
- **Mass = density × radius³**, so size and colour both matter. A large red planet can pull about as hard as a small blue one.
- **Gravity follows the inverse-square law.** The pull on the missile from each planet is `G × M / d²`, and the pulls from all the planets add together as vectors.
- **Hits use each ship's actual outline**, rotated with the ship, so a shot that clips a wingtip or a nacelle counts and one that slips past it doesn't. To see the hit shapes, add `#hitbox` to the end of the page address.
- The simulation uses velocity-Verlet integration at 240 steps per second, so orbits stay stable and repeatable. The same angle and speed on the same map always give the same result.

## Settings (⚙)

**Game**
- **Opponent:** two players taking turns on one device, or the computer (Easy / Medium / Hard). The computer aims better as the round goes on, much like a person correcting from their trails.
- **Number of planets:** from *Very few* to *Lots*. Layouts are always random; this only sets a rough range. It applies from the next round.
- **Achievements:** turn the trick-shot pop-ups on or off (see below).

**Physics**
- **Gravity strength:** from 0× (off) to 3×. It takes effect straight away, even mid-round, so students can repeat the same shot under different gravity. Planet masses don't change; only the strength of the pull does. The **Gravity** button in the header shows the current value and opens this setting.

**Display**
- **Screen edges:** open space (shots can fly off and come back), vanish, bounce or wrap.
- **Trails:** keep every shot this round, keep the last shot per player, or show only the most recent shot.
- **Animation speed:** slow, normal or fast.

**Teaching overlays** (all optional)
- **Gravity field arrows:** the direction and strength of the pull across the whole map.
- **Gravity strength map:** a banded glow, where brighter means stronger. The bands show the inverse-square fall-off.
- **Velocity & force arrows:** `v` and `F` arrows ride along with the missile, plus a faint line to each planet that gets thicker the more that planet is pulling.
- **Planet labels:** each planet's density (ρ) and mass (M).
- **Shot readout:** time, speed, gravity pull and closest approach to the target.

## Challenges 🎯

The **🎯 Challenges** button opens 13 set maps, the same for every student. Each has one goal, and often some controls locked (e.g. speed fixed, so only the angle changes), so students work on one idea at a time. Each level shows:

- an **intro card** with what you're learning, the goal and the rules;
- a **💡 Hint** that unlocks after two misses;
- a **debrief** on passing that explains the physics, plus 1–3 ⭐ based on shots used.

All levels are open, so play them in any order. Levels are tagged **Stage 4** (Years 7–8) or **Stage 5** (Years 9–10 extension).

| # | Challenge | Stage | You control | The idea |
|---|---|---|---|---|
| 1.1 | Straight shooter | 4 | angle | 0° = right; gravity off, so shots go straight (Newton's first law). A protractor surrounds the ship. |
| 1.2 | Up and across | 4 | angle | Measuring angles: 45° |
| 1.3 | Behind you | 4 | angle | Angles past 180°; small errors grow with distance |
| 1.4 | Bank shot | 4 | angle | Bounce off an edge: angle of incidence = angle of reflection |
| 2.1 | Which way will it bend? | 4 | angle | Gravity pulls towards a planet's centre, so aim off to compensate |
| 2.2 | Speed matters | 4 | speed | Slower shots spend longer near a planet, so they bend more |
| 2.3 | Tune the gravity | 4 | gravity strength | Stronger gravity → bigger force → more bending (F = ma) |
| 3.1 | Density matters | 4 | angle | Same size, 5× the density → 5× the mass → 5× the pull |
| 3.2 | Big red, small blue | 4 | angle | Equal masses cancel, whatever the size (mass = ρ × r³) |
| 3.3 | The balance point | 5 | angle | Inverse-square law: 4× the mass balances at 2× the distance |
| 4.1 | Slingshot | 5 | angle & speed | Swing 90°+ round the big planet to hit a hidden target |
| 4.2 | Into orbit | 5 | speed | Find orbital speed: too slow crashes, too fast escapes |
| 4.3 | Grand finale | 5 | angle & speed | Everything combined in a crowded field |

Every level has been checked with the game's own physics to make sure it can be solved. Challenge attempts appear in the shot log and reports, with whether they were passed and in how many shots.

## Achievements 🏆

Trick shots earn achievements, which pop up as they happen. The 🏆 button in the header shows which have been earned, by whom and how many times. Once an achievement is earned, the list also shows a short explanation of the physics behind it. Achievements last for the session: they reset when the page is reloaded, or with the reset button in the list.

| | Achievement | How to earn it |
|---|---|---|
| 🎯 | **Deadshot** | Hit the enemy with your first shot on a new map. |
| 🔄 | **Loop de loop** | Your shot goes all the way round a planet (any result). |
| ☄️ | **Slingshot** | Swing at least 90° around one planet, then hit the enemy. |
| 🦶 | **Shot myself in the… foot** | Gravity swings your shot back round and it hits your own ship. |
| ⏳ | **Hang time** | Hit the enemy after more than 10 seconds in flight. |
| 😅 | **Close shave** | Miss the enemy by less than 5 units (measured to the ship's hull). |
| 🍎 | **Newton's First** | Hit the enemy with gravity switched off. |
| 🎱 | **Pinball** | Hit the enemy after 3 or more bounces off the edges (Bounce mode). |

The computer opponent can earn them too. One shot can earn several at once: a first-shot, three-bounce hit with gravity off earns Deadshot, Pinball and Newton's First together.

## Shot log and reports 📋

The **📋 Log** button lists every shot fired this session, grouped by round. For each shot it shows the angle, speed, how much the player changed their angle and speed since their previous shot, gravity, result, flight time, closest approach and any achievements. Type the students' names in to use them in the exports.

| Export | What you get |
|---|---|
| **Print / Save PDF** | A printable report: a summary per player, a picture of each round's map with its shot trails, the shot tables, and **reflection questions** with lines to write on. Choose *Save as PDF* as the printer to keep a copy. |
| **Download report** | The same report as a web page file, e.g. to hand in through the LMS. |
| **Download CSV** | The shot table as a spreadsheet file for Excel or Google Sheets, ready for graphing (e.g. closest approach vs shot number). |
| **Copy table** | The shot table copied to the clipboard, to paste into Word, Docs, Excel or Sheets. |

The reflection questions are built from each student's own shots. They quote the student's run of closest approaches in their longest round, and ask about planet crashes (the inverse-square law), any gravity changes they tried, and achievements earned or planned. They end with advice for a first-time player. Untick *Add reflection questions* for a plain log. The log resets when the page is reloaded.

## Classroom ideas

- **Gravity off:** set gravity to 0× and fire. The missile travels in a straight line at constant speed (Newton's first law).
- **Same shot, different gravity:** fire, change gravity to 2×, then fire the identical angle and speed. What changed, and why?
- **Density vs size:** turn on planet labels and find a big red planet and a small blue one with similar masses. Compare how they bend a shot.
- **Force vs velocity:** turn on the arrows and watch a slingshot. The force points at the planet, not the way the missile is moving.
- **Slingshot discussion:** why doesn't the missile speed up after swinging round a planet here, when real spacecraft gain speed from a gravity assist? (Here the planets are fixed in place; real planets are moving.)
- **Record and refine:** print the shot log report at the end of the lesson. Students answer the reflection questions about how they corrected their aim, or graph their closest approach against shot number from the CSV.

## Credits

Inspired by the original *Gravity Wars* (1989). The ship graphics are simple code-drawn homages to the Enterprise and a Klingon Bird of Prey, as in the original game. This is a fan remake for educational use and is not affiliated with Star Trek or its rights holders.
