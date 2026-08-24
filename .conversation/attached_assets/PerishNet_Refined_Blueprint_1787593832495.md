# PerishNet — Refined Concept & PPT Blueprint
**SIH26197 · Software · Student Innovation · Agriculture, FoodTech & Rural Development**

*Scan Once. Monitor Continuously. Prevent Waste.*

> Existing freshness tools answer "How fresh is it?" PerishNet answers "How long will it remain usable, how is that changing, and what should we do now to prevent it from becoming waste?"

---

## 1. The Problem

Fruits and vegetables are not static inventory — their condition changes continuously due to temperature, humidity, handling, transport, and time. Today's freshness assessment is visual, subjective, periodic, and reactive. A farmer or retailer can tell you "this batch looks okay," but not how much usable life remains or what to do about it right now.

**Grounding stats for the slide:**
- India loses up to **15% of its fruit and vegetable production** to post-harvest spoilage, per a 2022 NABCONS study commissioned by the Ministry of Food Processing Industries and reported to Parliament in August 2024.
- ICAR-CIPHET estimates the **annual economic value of harvest and post-harvest losses across major crops at roughly ₹92,651 crore**, with fruits and vegetables together accounting for a large share of that figure.
- Lead with the ₹-crore number on the slide — it lands harder with a judging panel than a percentage.

---

## 2. Why Current Approaches Fall Short

- Manual inspection → subjective, inconsistent across handlers
- Static "best before" labeling → doesn't reflect actual handling/storage history
- Single-point freshness classifiers (photo → verdict) → tell you *now*, not *what's coming* or *what to do*

---

## 3. The Core Idea

PerishNet fuses three sources of intelligence:

| Source | Tells you |
|---|---|
| 📱 One-time smartphone photo | Where the produce **starts** (initial visual condition) |
| 📦 Continuous sensor pod | What **happens afterward** (environmental history) |
| 🧠 AI Life Engine | Where it's **going** (dynamic prediction + recommended action) |

The user never has to re-photograph the batch every few hours — the sensor stream keeps the prediction alive between scans. A rescan is only requested if the model's confidence drops (e.g., an unexplained environmental spike), which keeps this a **hybrid** system rather than a "sensor knows everything" black box.

---

## 4. System Architecture (Refined)

```
📷 CV MODEL  →  Quality / Defect Score
                        │
🌡 Environmental + ⏱ Time → FEATURE FUSION
                        │
              SHELF-LIFE ENGINE  ← (refined below)
                        │
               SPOILAGE-RISK MODEL
                        │
                DECISION ENGINE
                        │
            INTERVENTION RECOMMENDATION
```

### The one change that matters most: make the Shelf-Life Engine physics-informed, not purely data-driven

The original plan implied training a shelf-life model from a small, self-collected dataset (a handful of produce types, a few dozen observations). That's not enough data to train a reliable model from scratch — and judges with any ML background will ask about it.

**The fix:** use established post-harvest physiology as the model's backbone, and use your own data to calibrate it rather than train it from zero.

- **Q10 respiration-rate scaling** and the **Arrhenius temperature-dependence equation** are well-documented in food science literature — they describe how a produce type's decay rate scales with temperature. Published Q10/activation-energy coefficients exist for common produce (tomato, banana, leafy greens, etc.).
- Use these published coefficients as the model's core kinetic engine for your chosen produce types.
- Let your CV score adjust the *starting point* (a lower initial quality score = effectively "older" on the decay curve), and let your small controlled dataset **calibrate and validate** the kinetic model rather than train a black box.
- This is a legitimate, recognized technique (physics-informed ML). It needs far less data, is far more defensible in Q&A ("we grounded this in published food-science kinetics, not just a small dataset"), and is a genuine differentiator — most student CV projects are pure black boxes.

**Practical scope cut:** the original plan mentioned 5 produce types for the pilot dataset. For an MVP, **narrow to 2–3** (e.g., tomato, banana, one leafy green) — enough to prove the model generalizes across different decay physiology (climacteric vs. non-climacteric produce) without spreading data-collection effort too thin.

---

## 5. Decision Engine & Multi-Batch Intelligence

Don't stop at "this batch has 2 days left." The real value is in the decision layer.

**Example — three batches, one decision:**

| Batch | Remaining Life | Recommended Action |
|---|---|---|
| A | 6 days | Continue normal storage |
| B | 2 days | **Prioritize for sale** |
| C | 4 days | Monitor |

For Batch B specifically, the engine can go further: comparing a 4-hour route to Market A against an 18-hour route to Market B, and recommending the faster route so the batch doesn't spend most of its remaining life in transit.

**Action set (keep it to these six — a limited, defensible set reads as more credible than an open-ended list):**
🟢 Continue normal storage · 🟡 Prioritize for sale · 🟠 Move to better storage · 🔴 Reroute for faster distribution · 🔵 Send for processing · 🟣 Redistribution/recovery pathway

---

## 6. The What-If Simulator — Your Centerpiece Demo

This is the single best differentiator in the concept, and it's **computationally cheap to build well**: because the shelf-life engine is a kinetics formula (not a heavy model), you can re-run it instantly against modified inputs. That means the simulator can be genuinely real-time in front of judges — no lag, no "please wait while it processes."

Let the judge drag:
- Temperature: 28°C → 34°C
- Transport delay: 4h → 18h
- Storage condition: Current → Controlled

...and watch remaining life, risk level, and recommendation update live. This proves the system is *modeling* the process, not just classifying a photo — make sure this moment is not rushed in your demo script.

---

## 7. MVP Build Plan — What to Actually Build vs. What Stays on a Slide

This is the most important addition for your prep timeline. The original concept has excellent breadth, but not all of it should be *built*.

### ✅ Build this (core working prototype)
- CV quality/defect scorer for 2–3 produce types (transfer learning on a public dataset + your own photos)
- ESP32 + DHT22 sensor pod streaming temperature/humidity over WiFi/BLE
- Hybrid Q10/Arrhenius + ML-calibrated shelf-life engine for those same 2–3 produce types
- Four-stage risk bands (🟢 Normal / 🟡 Watch / 🟠 Action / 🔴 Critical)
- Rule-based decision engine (sell first / store better / reroute / process) with a simple 3–5 batch prioritization view
- The what-if simulator — non-negotiable, this is your best five minutes on stage
- One clean dashboard: batch card, degradation curve, current risk, recommended action

### 🗺️ Roadmap slide only — mention, don't build
- QR/NFC full digital lifecycle timeline
- Separate role-based dashboards (consumer/retailer/warehouse/admin) — for the demo, one view with a role toggle is enough
- Additional sensors: light exposure, shock/vibration, VOC/ethylene
- Warehouse zone-level aggregation across many devices
- Full multi-market routing optimization
- Redistribution/recovery marketplace pathway

**Rule of thumb:** if a feature doesn't directly support *Assess → Predict → Prevent Loss*, it goes on the roadmap slide, not into the build.

---

## 8. Smart Hardware — Sensor Pod

**MVP components:**
- ESP32 dev board (processing + connectivity) — approx. ₹300–400
- DHT22 temperature/humidity sensor — approx. ₹150–250
- Small Li-ion battery + basic enclosure — approx. ₹200–300
- Misc (wiring, mounting) — approx. ₹100

**Indicative total: well under ₹1,000 per unit** (exact pricing varies by supplier/quantity — verify before printing this on a slide, but it supports a strong "low-cost, scalable for smallholder farmers" claim, which matters a lot to government judges thinking about real deployment).

**Deployment contexts:** home storage, retail crates/bins, warehouse zones, transport (future).

**Be upfront in Q&A:** don't claim the sensor measures every spoilage factor. Different produce behaves differently and gas sensors are noisy — the MVP deliberately concentrates on temperature, humidity, and time because those are the variables you can measure reliably.

---

## 9. Additional Differentiators to Weave In

1. **Physics-informed hybrid model** (Section 4) — scientific credibility with minimal data.
2. **The what-if simulator** (Section 6) — judge-interactive, not just a static demo.
3. **Vernacular/regional-language interface** — since your named end-users are farmers, warehouse staff, and small retailers, a Hindi/regional-language voice or text interface for batch creation and alerts is a genuine usability upgrade, not a cosmetic one. Most smallholder farmers aren't comfortable with English-only apps. This is a strong "built for Bharat" line for your future-scope slide, and a simple version (Hindi labels + voice input for batch creation) is low-effort enough to actually build if time allows.
4. **Loss-prevention KPI framing** (already in the original plan — keep it). Lead with "expected loss prevented," not model accuracy. "98% classification accuracy" is a vanity metric; "X kg of produce saved across the demo batches" is an impact metric.

---

## 10. Explainability & Confidence (Keep — This Is a Strength)

Never show a bare number with no explanation.

- ❌ "Remaining life = 2.37 days"
- ✅ "Estimated usable life: 2.1–2.8 days · Confidence: Medium · Driven by: rising temperature exposure, batch age, elevated humidity"

Showing a range and a confidence level, not false precision, reads as more scientifically mature and helps enormously in judge Q&A.

---

## 11. What NOT to Add (Discipline Checklist)

❌ Blockchain · ❌ Generic chatbot · ❌ AR/VR · ❌ Marketplace · ❌ Drone integration · ❌ Duplicate mobile + web builds · ❌ Dozens of unvalidated sensors · ❌ Claiming "AI detects everything"

Every feature must trace back to: **Assess → Predict → Prevent loss.**

---

## 12. Your 10-Slide PPT Blueprint

**Slide 1 — Title**
PerishNet · "Scan Once. Monitor Continuously. Prevent Waste." · SIH26197 · Team name

**Slide 2 — Problem**
Open with the ₹92,651 crore annual loss figure and the up-to-15% F&V spoilage stat. Then: freshness assessment today is visual → subjective → periodic → reactive. "This batch looks okay" ≠ "how much life remains, and what do I do now."

**Slide 3 — Why current approaches fall short**
Manual inspection / static best-before dates / single-point freshness classifiers — none model the continuous, multi-factor nature of spoilage.

**Slide 4 — Our solution**
One-liner + the three-source intelligence framing (photo = start state, sensor = ongoing environment, AI = trajectory).

**Slide 5 — How PerishNet works**
The end-to-end flow diagram: photo → CV baseline → batch created → sensor attached → continuous readings → AI Life Engine → dynamic shelf-life + risk → decision engine → recommended action.

**Slide 6 — Core AI**
CV quality scorer + the physics-informed shelf-life engine (Q10/Arrhenius, calibrated with your own data) + 4-stage risk bands. This slide is where you earn technical credibility — spend real time on the "why kinetics, not just ML" explanation.

**Slide 7 — Decision intelligence**
The batch-priority table (Section 5) + the six-action decision set + **the what-if simulator**, ideally live or as a short embedded clip.

**Slide 8 — Smart hardware**
ESP32 + DHT22 sensor pod, approximate sub-₹1,000 BOM, deployment contexts. This is your "this is actually deployable at scale" slide.

**Slide 9 — Demo / impact**
Walk through Tomato Batch T-042: healthy (4.2 days) → temperature rises → risk escalates (2.6 days) → recommend prioritized sale → simulate controlled storage (forecast improves) → simulate 18-hour transport delay (risk rises). Close with the loss-prevention KPI, not an accuracy number.

**Slide 10 — Scalability & future**
Vernacular-language interface, additional sensors (light/shock/ethylene), QR/NFC digital lifecycle, warehouse zone monitoring, full routing optimization, redistribution pathway.

---

## 13. Team & Strategy Notes (Not Slide Content)

- SIH26197 is a **self-defined Student Innovation** slot — there's no ministry SPOC mandating this exact solution, which gives creative freedom but not the institutional backing a named PS carries. Confirm with your internal SIH coordinator that this slot is actually open/available at your college before locking in.
- At the internal-hackathon stage, Student Innovation entries across **all** themes compete together for your college's limited number of forwarding slots — a different funnel than a named ministry PS, where competition is spread nationally instead of concentrated at your own college.
- A Hardware-track twin of this theme exists (SIH26214) if you ever wanted the sensor pod itself to be the primary judged innovation rather than the AI layer — but staying on the Software track (26197) is the right call given the AI/decision layer is genuinely the heart of this project.

---

## One Sentence to Memorize

*"We're not making an AI app for fruits — we're building an intelligence layer for perishable inventory."*
