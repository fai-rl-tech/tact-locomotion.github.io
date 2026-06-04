# TACT-ful — 3-Minute Video Script & Production Outline
### CoRL 2026 Supplementary Video

---

## Quick Reference for Canva

| Property | Value |
|---|---|
| **Format** | 1920 × 1080 px, 16:9 |
| **Duration** | 3:00 (180 s) |
| **Frame rate** | 30 fps |
| **Narration pace** | ~107 wpm (slow, clear academic delivery) |
| **Total spoken words** | ~315 |
| **Primary colour** | `#3949ab` (indigo) |
| **Dark background** | `#0d0d1a` |
| **Light background** | `#f0f2ff` |
| **White** | `#ffffff` |
| **Accent** | `#e8eaf6` |
| **Heading font** | Montserrat ExtraBold / 900 |
| **Body font** | Inter Regular / 400–600 |
| **Narration font** | (not on screen — audio only) |

---

## Narrative Arc

```
ACT 1  THE PROBLEM        0:00 – 0:32   4 frames   Dark background
ACT 2  THE METHOD         0:32 – 1:22   5 frames   Light / white
ACT 3  SIM DEMOS          1:22 – 1:52   2 frames   Dark / video
ACT 4  REAL ROBOT DEMOS   1:52 – 2:22   4 frames   Full-bleed video
ACT 5  RESULTS            2:22 – 2:50   3 frames   White / data
ACT 6  CONCLUSION         2:50 – 3:00   1 frame    Dark / end card
```

---

## Frame-by-Frame Script

---

### FRAME 01 | Title Card | 0:00 – 0:05 | 5 s
**Background:** `./static/images/teaser_vinfast1.png` — full bleed, dark overlay (~60% opacity `#0a0a1a`)

**On screen:**
- Top-centre: `TACT`**`ful`** — giant, white, Montserrat 900, letter-spaced
- Below: *Multi-Channel Terrain Affordance and Compliance Training for Payload-Robust Perceptive Humanoid Locomotion* — white, Inter 600, 28 px
- Badge: `CoRL 2026  ·  Under Review` — indigo pill

**Voiceover:**
> "TACT-ful — terrain awareness and payload compliance for service humanoids."

**Production notes:**
- Fade in from black over 1 s
- Acronym letters T-A-C-T in indigo `#3949ab`; "ful" in white

---

### FRAME 02 | Blind Locomotion Fails | 0:05 – 0:15 | 10 s
**Background:** `#0d0d1a` solid dark

**On screen:**
- Top-left label: `ACT 1 — THE PROBLEM` (small caps, `#6366f1`, 18 px)
- Centre: **[REPLACE: external video clip — blind locomotion robot failing on stairs]**
  - Placeholder box: dark grey `#1e1e30`, dashed border `#4a5568`
  - Label: "CLIP: Blind policy — stair failure"
- Bottom text overlay: *"No perception → line contact → friction cone collapses"* — white, 24 px, semi-bold

**Voiceover:**
> "Locomotion policies trained without perception fail on structured terrain. A sole straddling a step edge creates a line contact — the friction cone collapses. The robot falls."

**Production notes:**
- Video clip fills ~70% of frame, centred
- Bottom text fades in at ~4 s into frame

---

### FRAME 03 | Perceptive but No Payload | 0:15 – 0:25 | 10 s
**Background:** `#0d0d1a` solid dark

**On screen:**
- Top-left label: `ACT 1 — THE PROBLEM`
- Left panel (~50%): **[REPLACE: perceptive policy succeeding on stairs — no load]**
  - Label: "Perceptive — no payload ✓"
- Right panel (~50%): **[REPLACE: same or similar policy failing with payload]**
  - Label: "Perceptive — with payload ✗"
- Bottom: *"Depth camera helps with terrain — but payload shifts the CoM, tilts the trunk, diverges the capture point"*

**Voiceover:**
> "Perceptive methods navigate stairs well. But add a payload — the center of mass shifts, the trunk tilts, the capture point diverges. The policy has no answer."

**Production notes:**
- Thin vertical divider between panels
- "✓" green, "✗" red; labels bottom-anchored on each panel
- Use own simulation clip of baseline policy failing under load if no external clip available

---

### FRAME 04 | Our Solution | 0:25 – 0:32 | 7 s
**Background:** `./static/images/teaser_vinfast_14.png` — full bleed, dark overlay 55%

**On screen:**
- Large centred text: **"One training run. Terrain + payload."** — white, Montserrat 800, 52 px
- Stat strip (4 boxes, centred, below):
  - `1.0 m/s` — on stairs
  - `~15 kg` — zero-shot payload
  - `50 Hz` — policy frequency
  - `No distillation`
- Bottom: `Standard PPO · Sim-to-Real · No Force Sensor`

**Voiceover:**
> "TACT-ful solves both — in a single training run, with standard PPO, no distillation."

**Production notes:**
- Energetic cut from dark problem frames; momentary brightness pop
- Stat boxes: indigo `#3949ab` fill, white text, rounded 10 px

---

### FRAME 05 | System Overview | 0:32 – 0:42 | 10 s
**Background:** `#ffffff`

**On screen:**
- Title: `System Overview` — indigo dark, Montserrat 700, 36 px
- Main figure: `./static/images/System Overview - Perceptive.svg` — 85% width, centred
- Two callout labels (below figure):
  - Left: `DCM Foothold Planner — terrain-optimal targets`
  - Right: `Wrench Compliance Scheduler — virtual force + moment`

**Voiceover:**
> "Two modules feed a shared reward: a GPU-parallel DCM foothold planner for terrain-quality-aware landing targets, and a wrench compliance scheduler that injects virtual force and moment at a sampled load point."

**Production notes:**
- ACT 2 label top-right: `ACT 2 — METHOD`
- Thin `3 px` indigo rule under title

---

### FRAME 06 | Multi-Channel Terrain Cost | 0:42 – 0:54 | 12 s
**Background:** `#f0f2ff` (light indigo tint)

**On screen:**
- Title: `Multi-Channel Terrain Cost`
- Left (55%): `./static/images/teaser_2.png` — terrain affordance map image
- Right (40%): Three stacked channel cards
  - **Q — Flatness** | elevation range over footprint — flags edge landings
  - **E — Steepness** | max-pooled Sobel gradient — propagates worst riser
  - **M — Height Feasibility** | velocity-aware kinematic limit
  - + **Climb bonus b** — rewards stepping up onto reachable treads (green card)
- Below cards: small formula `J_i = α_pos·d_pos + α_dcm·d_dcm + α_E·E + α_Q·Q + α_M·M − α_climb·b`

**Voiceover:**
> "Three terrain channels — flatness Q, steepness E, velocity-aware feasibility M — drive the planner and shape RL rewards. A climb bonus rewards stepping onto reachable treads."

**Production notes:**
- Each card animates in with VO mention (stagger 2 s apart if using Canva animation)
- Channel initial letters (Q, E, M) large and bold, indigo

---

### FRAME 07 | Bézier Swing & Foot Orientation | 0:54 – 1:04 | 10 s
**Background:** `#ffffff`

**On screen:**
- Title: `Bézier Swing Trajectory & Tangent-Guided Orientation`
- 2 × 2 image grid (fills 75% of frame):
  - (a) `./static/images/bezier_step_up.png` — *Step-up: apex over riser*
  - (b) `./static/images/bezier_step_down.png` — *Step-down: extended travel*
  - (c) `./static/images/bezier_gap.png` — *Gap crossing*
  - (d) `./static/images/bezier_flat.png` — *Flat terrain: symmetric arc*
- Right side, two bullet points:
  - Pre-apex: tangent rotated 90° → sole clears riser
  - Post-apex: tangent aligns → flat tread landing

**Voiceover:**
> "A Bézier arc biases its apex toward the higher endpoint — over the riser on step-up, extended on step-down. The arc tangent guides sole orientation: the foot clears the riser, then arrives flat on the tread."

**Production notes:**
- Highlight (a) and (b) with a subtle indigo glow border first, then (c) and (d)

---

### FRAME 08 | Lower-Body Compliance Training | 1:04 – 1:16 | 12 s
**Background:** `#ffffff`

**On screen:**
- Title: `Lower-Body Compliance Training`
- Left (50%): Schematic diagram (create in Canva):
  - Robot body silhouette (use `./static/images/teaser_vinfast3.png` as reference)
  - Anchor point in world frame (circle with cross)
  - Arrow from anchor → load attachment point on robot
  - Labels: `anchor p_a`, `load point p_load`, `F_ext (spring-damper)`, `τ_ext (moment)`
- Right (45%): Three stacked cards
  - "Virtual spring-damper generates force **and** moment — no payload mass needed"
  - "Wrench-aware targets: pelvis height yields to F, trunk angle yields to τ"
  - "No force sensor required. No retraining at deployment."

**Voiceover:**
> "A virtual spring-damper at the load attachment point generates physically consistent force and moment — without payload mass in simulation. Wrench-aware targets train the policy to yield. No force sensor. No retraining."

**Production notes:**
- Bold and highlight "No force sensor." — key selling point
- Arrow animated if possible; otherwise static diagram is fine

---

### FRAME 09 | Training Pipeline | 1:16 – 1:22 | 6 s
**Background:** `#1a237e` (dark indigo)

**On screen:**
- Title: `Training Setup` — white, large
- 2 × 3 grid of white stat boxes:
  - `4 096` / parallel environments
  - `Standard PPO` / no distillation
  - `30 Hz` / depth CNN, 4-frame stack
  - `50 Hz` / proprioception history
  - `20 k` / training iterations
  - `0-shot` / sim-to-real transfer

**Voiceover:**
> "Four thousand and ninety-six parallel MuJoCo environments, standard PPO — no distillation, no teacher-student staging. Deployed zero-shot."

**Production notes:**
- White text on dark indigo; stat values large (Montserrat 900); labels small below
- Brief, punchy frame — acts as a visual breath before the demos

---

### FRAME 10 | Simulation — Baseline & Light Payloads | 1:22 – 1:37 | 15 s
**Background:** `#0d0d1a`

**On screen:**
- Top-left: `ACT 3 — SIMULATION` label in `#6366f1`
- Three equal video panels (side by side):
  1. **[SIM VIDEO: no payload]** — label `Baseline · no load`
  2. **[SIM VIDEO: front-mounted backpack 5 kg]** — label `Front · 5 kg`
  3. **[SIM VIDEO: rear-mounted backpack 5 kg]** — label `Rear · 5 kg`
- Each panel: condition label bottom-left, white on semi-dark bar

**Voiceover:**
> "Simulation: baseline at one meter per second. Five kilograms front-mounted — pelvis drops, compliance absorbed. Rear-mounted — trunk pitches back, the policy adapts."

**To replace placeholders:** drop files into `static/videos/`:
- `sim_no_payload.mp4`
- `sim_front_backpack_5kg.mp4`
- `sim_rear_backpack_5kg.mp4`

**Production notes:**
- Panels flush with no gap; thin `1 px` divider `#2d3748`
- Label bars: `rgba(0,0,0,0.55)` background

---

### FRAME 11 | Simulation — Heavy & Complex Payloads | 1:37 – 1:52 | 15 s
**Background:** `#0d0d1a`

**On screen:**
- Top-left: `ACT 3 — SIMULATION`
- Three equal video panels:
  1. **[SIM VIDEO: both backpacks, 10 kg total]** — label `Front + Rear · 10 kg`
  2. **[SIM VIDEO: basket 5 × 1 kg weighted blocks]** — label `Basket · 5 kg`
  3. **[SIM VIDEO: car door ~5 kg]** — label `Car Door · ~5 kg`

**Voiceover:**
> "Both backpacks — ten kilograms total. A basket of weighted blocks shifting with each step. A car door at arm's length — the largest moment arm. Zero-shot. No fine-tuning."

**To replace placeholders:** drop files into `static/videos/`:
- `sim_both_backpacks_10kg.mp4`
- `sim_basket_5kg.mp4`
- `sim_car_door_5kg.mp4`

**Production notes:**
- End on car-door panel — most dramatic; consider brief pause before cut

---

### FRAME 12 | Real Robot — Stair Traversal | 1:52 – 2:00 | 8 s
**Background video:** `./static/videos/stair_traversal.mp4` — full bleed, muted, loop

**On screen:**
- Top-left: `ACT 4 — REAL ROBOT  ·  Zero-shot from simulation` — white, 20 px
- Bottom bar: `Stair traversal  ·  risers up to 0.20 m  ·  1.0 m/s` — white on dark gradient

**Voiceover:**
> "Deployed directly from simulation — no hardware fine-tuning. Climbing and descending stairs at one meter per second."

**Production notes:**
- Fade in from black over 0.5 s
- Bottom gradient: `linear-gradient(transparent, rgba(0,0,0,0.7))` 30% height

---

### FRAME 13 | Real Robot — 7 kg Wrist Payload | 2:00 – 2:08 | 8 s
**Background video:** `./static/videos/up_stair_traversal_7kg.mp4` — full bleed, muted, loop

**On screen:**
- Top-left: `ACT 4 — REAL ROBOT`
- Bottom bar: `Wrist-mounted tray  ·  7 kg  ·  moment-dominated load`
- Bottom-right badge: `65% SR  vs.  50% baseline`

**Voiceover:**
> "Seven kilograms, wrist-mounted — a moment-dominated load with a long arm. The trunk tilts into the weight rather than resisting it."

**Production notes:**
- Badge: indigo pill, white text, bottom-right
- The trunk tilt behaviour is visible in the footage — let it play

---

### FRAME 14 | Real Robot — 20 kg Descending | 2:08 – 2:17 | 9 s
**Background video:** `./static/videos/down_stair_traversal.mp4` — full bleed, muted, loop

**On screen:**
- Top-left: `ACT 4 — REAL ROBOT`
- Centre-top large text: **`20 kg`** — white, Montserrat 900, 96 px (fades in at 2 s)
- Bottom bar: `Rear-mounted backpack  ·  descending stairs  ·  zero-shot`

**Voiceover:**
> "Twenty kilograms — a full expedition backpack. Descending stairs, zero-shot."

**Production notes:**
- The "20 kg" super-title is the centrepiece; animate fade-in at 2 s into frame
- Keep narration short — let the footage do the work

---

### FRAME 15 | Real Robot — 20 kg Ascending | 2:17 – 2:22 | 5 s
**Background video:** `./static/videos/up_stair_traversal.mp4` — full bleed, muted, loop

**On screen:**
- Top-left: `ACT 4 — REAL ROBOT`
- Bottom bar: `Ascending  ·  20 kg backpack  ·  zero-shot`

**Voiceover:**
> "And ascending."

**Production notes:**
- Short, punchy — two words. Let the video speak.
- Brief pause (0.5 s) before cut to results

---

### FRAME 16 | Terrain Traversal Ablation | 2:22 – 2:33 | 11 s
**Background:** `#ffffff`

**On screen:**
- Title: `Terrain Traversal Results` — top-left, `ACT 5 — RESULTS` label top-right
- Left panel (55%): Two stacked ablation charts
  - `./static/images/ablation_normal.png` — *Standard terrain (0.05–0.20 m risers)*
  - `./static/images/ablation_hard_terrain.png` — *Hard terrain (0.20–0.30 m, OOD)*
- Right panel (40%): Four stat callout boxes stacked
  - `70%` SR — standard terrain (Ours)
  - `+13 pp` vs. TACT-only
  - `+17 pp` vs. Adaptive Gait only
  - `2.8×` foot-target distance without TACT

**Voiceover:**
> "Seventy percent success rate — thirteen points above TACT-only, seventeen above adaptive gait. Without terrain guidance, foothold distance increases 2.8 times. Foothold quality, not speed, drives the difference."

**Production notes:**
- Highlight "Ours" bar in each chart with an indigo annotation arrow if possible
- Stat boxes fade in left-to-right over the narration

---

### FRAME 17 | Payload Generalization | 2:33 – 2:44 | 11 s
**Background:** `#ffffff`

**On screen:**
- Title: `Payload Generalization — Zero-Shot`
- Left (55%): `./static/images/payload_w_terrain.png` — SR and power vs. payload condition
- Right (40%): Three result cards stacked
  - **Pelvis +15 kg** — 50% vs. 38% SR · 247 vs. 277 W
  - **Pelvis +20 kg** — parity (~37% vs. ~35%) · −27 W retained
  - **Wrist +10 kg** ✦ — **65% vs. 50% SR** · 223 vs. 259 W (green highlight)

**Voiceover:**
> "Zero-shot payload. At fifteen kilograms: fifty percent versus thirty-eight, thirty watts less power. Wrist-mounted ten kilograms — the largest margin: sixty-five versus fifty percent. Moment sampling targets this directly."

**Production notes:**
- Wrist card: green background `#e8f5e9`, bold numbers, ✦ star badge
- Secondary labels: "(arm-extended wrench sampling)"

---

### FRAME 18 | Limitations | 2:44 – 2:50 | 6 s
**Background:** `#f5f5f5` (light grey)

**On screen:**
- Title: `Limitations` — dark grey, Montserrat 700
- Three bullet points (left-aligned, spaced):
  - Quantitative ablations in simulation only — hardware results are qualitative
  - Hard-terrain SR: only **30%** (risers 0.22–0.28 m)
  - Compliance saturates at **~20 kg** centered load

**Voiceover:**
> "Limitations: ablations are in simulation; hard-terrain success reaches only thirty percent; compliance saturates near twenty kilograms."

**Production notes:**
- Honest, understated frame; no dramatic design
- Bold numbers within bullets for scanability

---

### FRAME 19 | Conclusion & End Card | 2:50 – 3:00 | 10 s
**Background:** `./static/images/teaser_vinfast1.png` — full bleed, dark overlay 65%

**On screen:**
- Centre-top: `TACT`**`ful`** — white, large, same style as Frame 01
- Three pill badges centred:
  - `Multi-Channel Terrain Cost`
  - `Compliance Without Force Sensors`
  - `Zero-Shot Sim-to-Real`
- Tagline: *"One training run. Structured terrain. Heavy payload. Real robot."* — white italic
- Bottom: Project URL — `fai-rl-tech.github.io/tact-locomotion.github.io` — white, monospace

**Voiceover:**
> "Terrain awareness and payload compliance — one PPO run, deployed zero-shot on a real service robot. Paper and supplementary materials at the project website."

**Production notes:**
- Fade out to black over final 2 s
- URL appears at 5 s into frame

---

## Timing Summary

| Frame | Title | Start | End | Duration | Words |
|---|---|---|---|---|---|
| 01 | Title Card | 0:00 | 0:05 | 5 s | 11 |
| 02 | Blind Locomotion Fails | 0:05 | 0:15 | 10 s | 32 |
| 03 | Perceptive, No Payload | 0:15 | 0:25 | 10 s | 34 |
| 04 | Our Solution | 0:25 | 0:32 | 7 s | 18 |
| 05 | System Overview | 0:32 | 0:42 | 10 s | 36 |
| 06 | Multi-Channel Terrain Cost | 0:42 | 0:54 | 12 s | 33 |
| 07 | Bézier Swing & Orientation | 0:54 | 1:04 | 10 s | 38 |
| 08 | Compliance Training | 1:04 | 1:16 | 12 s | 40 |
| 09 | Training Pipeline | 1:16 | 1:22 | 6 s | 22 |
| 10 | Sim: Baseline + Light Loads | 1:22 | 1:37 | 15 s | 28 |
| 11 | Sim: Heavy + Complex Loads | 1:37 | 1:52 | 15 s | 26 |
| 12 | Real: Stair Traversal | 1:52 | 2:00 | 8 s | 20 |
| 13 | Real: 7 kg Wrist | 2:00 | 2:08 | 8 s | 20 |
| 14 | Real: 20 kg Descending | 2:08 | 2:17 | 9 s | 11 |
| 15 | Real: 20 kg Ascending | 2:17 | 2:22 | 5 s | 2 |
| 16 | Terrain Ablation | 2:22 | 2:33 | 11 s | 32 |
| 17 | Payload Generalization | 2:33 | 2:44 | 11 s | 37 |
| 18 | Limitations | 2:44 | 2:50 | 6 s | 16 |
| 19 | Conclusion & End Card | 2:50 | 3:00 | 10 s | 26 |
| | **Total** | | | **180 s** | **~482\*** |

> \* Estimated at final delivery pace (~107 wpm for 3:00). Some frames include deliberate pauses — actual comfortable delivery will feel unhurried.

---

## Simulation Video Drop-in Reference

When simulation videos are ready, place them in `static/videos/` with these filenames (matching the HTML placeholders in `slides_video.html`):

| Filename | Content |
|---|---|
| `sim_no_payload.mp4` | Baseline — no payload, stair traversal |
| `sim_front_backpack_5kg.mp4` | Front-mounted backpack, 5 kg |
| `sim_rear_backpack_5kg.mp4` | Rear-mounted backpack, 5 kg |
| `sim_both_backpacks_10kg.mp4` | Both front + rear backpacks, 10 kg |
| `sim_basket_5kg.mp4` | Basket with 5 × 1 kg weighted blocks |
| `sim_car_door_5kg.mp4` | Car door, ~5 kg |
