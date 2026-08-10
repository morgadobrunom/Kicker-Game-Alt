# Kicker Game — Concept Brief

Summary of the **Kicker Game Concept Brief** and **Product Concept Brief** for this project.

---

## Overview

A fast-paced **arcade football game** where players score goals against a single opponent within a time limit. The game is a **companion to a comic series** about an Ethiopian soccer-playing group of teens.

**Focus areas:** movement precision, shooting accuracy, and adaptive strategy as ball spawns rotate around the field.

**Prototype:** [silver-moxie-cd1494.netlify.app](https://silver-moxie-cd1494.netlify.app)  
**Reference:** `street-goal-arcade.html` in this repo

---

## Platform & Audience

| Aspect | Detail |
|--------|--------|
| **Platform** | Mobile touch-first; portrait orientation; thumb-accessible controls |
| **Distribution** | Likely played through an online portal — **lightweight loading is critical** |
| **Localization** | Must be localized for **Ethiopia** |
| **Branding** | Assets must be **customizable to the sponsor brand** |

**Target players:**
- Casual mobile gamers
- Players seeking quick arcade sessions
- Those who enjoy skill-based scoring and high-score chasing
- Audience comfortable with touch-based analog and gesture controls

---

## Design Pillars

1. **Immediate Feedback** — Every action has clear, instant visual/audio response
2. **Skill Expression** — Swipe control, placement, and timing create a skill curve
3. **Replayability** — Randomized ball spawns and a tight timer encourage repeated plays

---

## Core Game Loop

1. Player moves upfield using a left-hand joystick
2. Player gains possession of the ball
3. Player swipes to shoot toward the goal
4. Goal scored or ball goes out of bounds
5. Ball respawns in a new location
6. Repeat until time expires

*Mechanics are suggestions — open to slight variations. Long-term vision includes stages with obstacles/defenders and **PvP online mode** (head-to-head with other players or bots).*

---

## Gameplay Mechanics

### Movement
- Analog joystick on the **left** side of the screen
- Smooth acceleration and deceleration
- Player moves upfield (toward goal) and laterally
- Confined within field boundaries

### Possession
- Ball automatically attaches when player is close enough
- Physical feedback when picking up the ball
- Possession breaks when the ball is kicked

### Shooting
- Swipe gesture on the **right** side of the screen
- **Power:** swipe speed or length (faster/longer = stronger)
- **Direction:** follows initial angle of the swipe
- **Curve:** subtle bend based on swipe curvature (gentle, not dramatic)
- Maximum range and power limits prevent trivial long-range scoring

### Ball Respawn
- Ball spawns in a randomized sector after each goal or out-of-bounds
- Court divided into **4 quadrants** (2×2 grid)
- Same sector never spawns twice consecutively
- Visual highlight shows new spawn location briefly
- Encourages dynamic repositioning each round

### Scoring & Win/Lose
- **One point per goal**
- Only shots under the crossbar count
- Must be within the goal mouth horizontally
- **Time limit:** 30 seconds per round
- **Objective:** Score as many goals as possible
- **End:** Time expires or player chooses to quit
- High score tracked; **"New Best"** indicator when personal record is beaten

### Controls Summary

| Action | Input |
|--------|-------|
| Move | Left thumb joystick |
| Shoot | Right thumb swipe |
| Shot power | Swipe speed |
| Shot direction | Swipe angle |
| Shot curve | Swipe curvature |

---

## Backend, Data & Integration

The game must integrate with an external platform and backend:

- **Account ID** is provided by the platform (account data stored on their side)
- Game runs in its **own container and database**
- Backend interaction is limited to:
  - Transmission of **session data**
  - Some **fulfillment information**
- **Progression and status API is required** — capture and stream game data to backend
- **Instrumentation is particularly important**, including:
  - How far the player kicks from
  - How strong they usually kick
  - Other behavioral/play metrics

---

## Development Steps

Not necessarily in this order:

1. Provide **game loop and level validation**
2. Provide **UI**
3. **Instrument the game**
4. Create **leaderboard** and/or **missions/badges**, e.g.:
   - Streak player
   - Speedy player (highest time)
   - Sharp shooter
   - Best player in character A / character B
   - Certain distance covered (marathon runner)
   - *Needs more work*
5. **Integrate on the platform**

---

## Progression & Meta

- High score tracking with personal best indicators
- Stages and progressions with obstacles or defenders (future)
- Leaderboard integration
- Missions/badges system tied to player behavior and achievements

---

## Future Expansion Ideas

| Feature | Priority / Notes |
|---------|------------------|
| **Multiplayer (head-to-head, same-screen)** | Very desired |
| PvP online mode (real players or bots) | Long-term |
| Leaderboard | Planned |
| Narrow down / refine levels | Planned |
| Seasonal unlocks | Future |
| Power-ups (slower ball, field extension, time boost) | Future |
| Difficulty modifiers (larger/smaller goal, faster clock) | Future |
| Cosmetics (player kit colors, ball skins) | Future |
| Multiple court themes (indoor, beach, synthetic surfaces) | Future |

---

## Open Questions / TBD

- Finalize mission/badge definitions beyond initial list
- Multiplayer feasibility and scope
- Level design and obstacle/defender progression details
- Sponsor brand asset customization spec
- Ethiopia localization scope (language, cultural assets, etc.)
