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

A shot ends when it hits a planet or a ship, leaves the play area, or has flown for 25 seconds. **You can hit your own ship**, and that point goes to your opponent.

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

## Achievements 🏆

Trick shots earn achievements, which pop up as they happen. The 🏆 button in the header shows which have been earned, by whom and how many times. Once an achievement is earned, the list also shows a short explanation of the physics behind it. Achievements last for the session: they reset when the page is reloaded, or with the reset button in the list.

| | Achievement | How to earn it |
|---|---|---|
| 🎯 | **Deadshot** | Hit the enemy with your first shot on a new map. |
| 🔄 | **Loop de loop** | Your shot goes all the way round a planet (any result). |
| ☄️ | **Slingshot** | Swing at least 90° around one planet, then hit the enemy. |
| 🦶 | **Shot myself in the… foot** | Gravity swings your shot back round and it hits your own ship. |
| ⏳ | **Hang time** | Hit the enemy after more than 15 seconds in flight. |
| 😅 | **Close shave** | Miss the enemy by less than 5 units (measured to the ship's hull). |
| 🍎 | **Newton's First** | Hit the enemy with gravity switched off. |
| 🎱 | **Pinball** | Hit the enemy after 3 or more bounces off the edges (Bounce mode). |

The computer opponent can earn them too. One shot can earn several at once: a first-shot, three-bounce hit with gravity off earns Deadshot, Pinball and Newton's First together.

## Classroom ideas

- **Gravity off:** set gravity to 0× and fire. The missile travels in a straight line at constant speed (Newton's first law).
- **Same shot, different gravity:** fire, change gravity to 2×, then fire the identical angle and speed. What changed, and why?
- **Density vs size:** turn on planet labels and find a big red planet and a small blue one with similar masses. Compare how they bend a shot.
- **Force vs velocity:** turn on the arrows and watch a slingshot. The force points at the planet, not the way the missile is moving.
- **Slingshot discussion:** why doesn't the missile speed up after swinging round a planet here, when real spacecraft gain speed from a gravity assist? (Here the planets are fixed in place; real planets are moving.)
- **Record and refine:** students log each angle and speed they try, and the result, then explain how they corrected their aim.

## Credits

Inspired by the original *Gravity Wars* (1989). The ship graphics are simple code-drawn homages to the Enterprise and a Klingon Bird of Prey, as in the original game. This is a fan remake for educational use and is not affiliated with Star Trek or its rights holders.
