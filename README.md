# <img width="600 height="100" alt="image" src="https://github.com/user-attachments/assets/6d30f2f1-b403-46f6-904e-452255a50154" />

https://perish-net-demo-dashboard--sagarrohan07.replit.app

### **Scan Once. Monitor Continuously. Prevent Waste.**
<img width="704" height="96" alt="image" src="https://github.com/user-attachments/assets/cbaed12c-ef8e-4d55-bda9-b0746f0b95ed" />


> **AI-powered predictive shelf-life and post-harvest loss prevention system for perishable fruits and vegetables.**

PerishNet combines **Computer Vision, IoT-based environmental sensing, Machine Learning, and decision intelligence** to continuously estimate the remaining usable life of perishable produce and recommend actions that can help prevent avoidable food loss.

Instead of simply asking:

> **“Is this fruit fresh?”**

PerishNet aims to answer:

> **“How long will it remain usable, how is its condition changing, and what should we do now to prevent it from becoming waste?”**

---

## 🎯 SIH 2026

PerishNet is being developed for **Smart India Hackathon 2026** under the agriculture/food-loss problem space.

The project focuses on moving beyond basic freshness classification toward:

**Visual Assessment → Continuous Monitoring → Shelf-Life Prediction → Spoilage Forecasting → Decision Support → Loss Prevention**

---

# 🚨 Problem

Fruits and vegetables are dynamic, perishable inventory. Their quality changes continuously due to factors such as:

* Temperature
* Humidity
* Time since harvest/purchase
* Storage conditions
* Transportation conditions
* Initial ripeness and quality
* Physical damage and visible defects

Conventional methods often rely on:

* Manual inspection
* Fixed shelf-life assumptions
* Periodic checks
* Reactive decisions

This creates a major gap:

> **Knowing the current condition is not enough. We need to predict what happens next and decide what action should be taken before the produce becomes waste.**

---

# 💡 Our Solution

PerishNet creates a **digital lifecycle profile for each produce batch**.

### The workflow

```text
📱 Initial Photo
       ↓
AI Visual Assessment
       ↓
Create Batch
       ↓
📦 Smart Sensor Pod
       ↓
Temperature + Humidity + Time
       ↓
AI Data Fusion
       ↓
Remaining Shelf-Life Prediction
       ↓
Spoilage Risk Forecast
       ↓
Decision Engine
       ↓
Sell First / Store / Reroute / Process
       ↓
♻️ Reduce Avoidable Food Loss
```

---

# ⭐ Core Concept

## **One Scan → Continuous Intelligence**

The user takes an initial photo only once to establish the produce's starting visual condition.

A small sensor device then continuously monitors the surrounding storage environment.

PerishNet combines both:

### 📸 Visual information

* Ripeness
* Color changes
* Bruises
* Spots
* Surface defects
* Mold-like visual patterns

### 🌡️ Environmental information

* Temperature
* Relative humidity
* Exposure duration
* Storage conditions

### ⏱️ Temporal information

* Harvest/purchase time
* Batch age
* Environmental history
* Previous observations

The AI then dynamically updates the estimated remaining usable life.

---

# 🧠 Key Features

## 1. AI-Based Visual Quality Assessment

A smartphone image is analyzed using Computer Vision to estimate the initial condition of the produce.

**Example:**

```text
Produce: Tomato
Initial Quality: Good
Quality Score: 78/100
Visual Confidence: High
```

---

## 2. Dynamic Shelf-Life Prediction

Instead of using a fixed expiry date, PerishNet estimates:

> **Remaining Usable Life**

Example:

```text
Estimated Remaining Life
2.1 – 2.8 Days

Prediction Confidence
Medium / High
```

The prediction changes when environmental conditions change.

---

## 3. Continuous Environmental Monitoring

A compact IoT sensor pod can monitor the storage environment.

### MVP sensors

* 🌡️ Temperature
* 💧 Relative Humidity

### Future possibilities

* Light exposure
* Transport vibration/shock
* Produce-specific gas/VOC sensing
* Additional environmental parameters

The system is designed so sensors provide **environmental intelligence**, rather than pretending that a sensor can directly observe every physical change in the produce.

---

## 4. Spoilage Risk Forecasting

PerishNet forecasts future risk rather than only reporting current condition.

Example:

```text
Today        🟢 Low Risk
+24 hours    🟡 Moderate Risk
+48 hours    🟠 High Risk
+72 hours    🔴 Critical Risk
```

---

## 5. Batch-Level Intelligence

PerishNet is designed for actual produce batches rather than only individual items.

Example:

```text
Batch ID: TOM-042
Produce: Tomato
Quantity: 500 kg
Age: 3 days
Temperature: 28.6°C
Humidity: 71%

Remaining Life: 2.4 days
Risk Level: High
Recommended Action: Prioritize Sale
```

This allows the platform to scale from:

**Home → Retail → Warehouse → Transportation → Supply Chain**

---

## 6. Decision Engine

PerishNet does not stop at:

> “This batch has 2 days left.”

It asks:

> **“What should we do now?”**

Possible actions include:

* Prioritize for sale
* Improve storage conditions
* Move to controlled storage
* Reroute to a closer destination
* Send for processing
* Redistribution/recovery pathways where appropriate

---

# 🔥 What Makes PerishNet Different?

Traditional freshness systems generally focus on:

```text
Image
 ↓
Fresh / Rotten
```

PerishNet aims to provide:

```text
Image
+
Environment
+
Time
 ↓
Current Condition
 ↓
Remaining Shelf Life
 ↓
Future Risk
 ↓
Best Intervention
```

### Our six major differentiators

**1. Dynamic instead of static**
Shelf life changes according to observed conditions.

**2. Predictive instead of reactive**
The system forecasts deterioration before critical spoilage.

**3. Batch-centric**
Designed for real inventory and supply-chain workflows.

**4. Action-oriented**
Recommends what should happen next.

**5. Continuous monitoring**
One initial visual scan can be followed by continuous sensor monitoring.

**6. What-if decision support**
Users can evaluate how changes in storage or transportation conditions may influence the forecast.

---

# 🎛️ What-If Simulator

One of PerishNet's key decision-support features.

Users can simulate scenarios such as:

```text
Temperature
28°C → 34°C

Transport Delay
4 hours → 18 hours

Storage
Current → Controlled
```

The system then recalculates:

* Remaining usable life
* Spoilage risk
* Expected loss
* Recommended action

This allows the user to ask:

> **“What happens if I change the storage conditions?”**

or:

> **“Which intervention should I choose?”**

---

# 📦 Smart Batch Identity

Each batch can have a unique:

### QR / NFC identifier

Example:

```text
TOM-042
```

Scanning the code can retrieve:

* Initial image
* Produce information
* Sensor history
* Temperature graph
* Humidity graph
* Shelf-life forecast
* Risk history
* Previous interventions
* Current recommendation

This creates a **digital lifecycle record** for the physical batch.

---

# 📊 PerishNet Dashboard

A typical batch dashboard can display:

```text
┌─────────────────────────────────────┐
│          TOMATO — TOM-042           │
├─────────────────────────────────────┤
│ Quality Score           78 / 100    │
│ Remaining Life          2.4 days    │
│ Spoilage Risk           HIGH        │
│ Temperature             28.6 °C     │
│ Humidity                71 %        │
│ Batch Age               3 days      │
├─────────────────────────────────────┤
│ Recommended Action                  │
│                                     │
│ 🔴 PRIORITIZE FOR SALE              │
└─────────────────────────────────────┘
```

---

# 🏠 Use Cases

## Consumer

> “Which vegetables should I consume first?”

## Farmer

> “Should this batch be sold now or stored?”

## Retailer

> “Which batch should be prioritized for sale?”

## Warehouse

> “Which batches require better storage?”

## Transport

> “Which batches require faster delivery?”

## Supply Chain

> “Where is the greatest spoilage risk right now?”

---

# 🧬 AI Architecture

```text
              📸 Image
                 │
                 ▼
       Computer Vision Model
                 │
                 ▼
        Visual Quality State
                 │
                 │
🌡️ Temperature ──┤
💧 Humidity ─────┤
⏱️ Time ─────────┤
📦 Batch Data ───┘
                 │
                 ▼
           Data Fusion
                 │
                 ▼
       Shelf-Life Prediction
                 │
                 ▼
        Spoilage Risk Model
                 │
                 ▼
          Decision Engine
                 │
                 ▼
       Intervention Ranking
```

---

# 🧰 Technology Stack

### AI / ML

* Python
* PyTorch
* OpenCV
* Scikit-learn
* XGBoost / equivalent models where appropriate
* Computer Vision
* Time-Series / Regression techniques

### IoT

* ESP32
* Temperature sensor
* Humidity sensor
* Bluetooth / Wi-Fi

### Backend

* Python
* FastAPI
* REST APIs

### Database

* PostgreSQL
* Potentially PostgreSQL + TimescaleDB for sensor time-series data

### Frontend

* React / Next.js
* Modern responsive UI
* Interactive charts and dashboards

### Deployment

* Docker
* Cloud deployment for demonstration and testing

---

# 🏗️ System Architecture

```text
                    USER
                     │
                     ▼
              📱 INITIAL SCAN
                     │
                     ▼
              VISUAL AI MODEL
                     │
                     ▼
                 BATCH ID
                     │
                     ▼
               SENSOR POD
           ┌─────────┼─────────┐
           │         │         │
      Temperature Humidity    Time
           │         │         │
           └─────────┼─────────┘
                     │
                     ▼
              DATA PIPELINE
                     │
                     ▼
               AI LIFE ENGINE
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       Quality    Shelf Life   Risk
          │          │          │
          └──────────┼──────────┘
                     ▼
              DECISION ENGINE
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
        SELL       STORE      REROUTE
          │          │          │
          └──────────┼──────────┘
                     ▼
              LOSS PREVENTION
```

---

# 🔬 Development Strategy

We will not attempt the complete system at once.

### Phase 1 — Computer Vision

```text
Image
 ↓
Produce Classification
 ↓
Quality / Defect Detection
```

### Phase 2 — Shelf-Life Prediction

```text
Visual Features
+
Age
+
Environmental Data
 ↓
Remaining Life Prediction
```

### Phase 3 — Smart Sensor

```text
Temperature
+
Humidity
 ↓
Continuous Monitoring
```

### Phase 4 — AI Data Fusion

```text
Vision + Sensor + Time
 ↓
Dynamic Prediction
```

### Phase 5 — Decision Engine

```text
Prediction
 ↓
Risk
 ↓
Recommended Intervention
```

### Phase 6 — Product Integration

```text
Mobile/Web
+
IoT
+
AI
+
Dashboard
```

### Phase 7 — SIH Demo

Build a polished end-to-end demonstration using a controlled set of produce categories and validated data.

---

# 📚 Dataset Strategy

The project requires two major classes of data:

### Visual Data

Images showing:

* Fresh produce
* Different ripeness stages
* Defects
* Deterioration

### Environmental + Temporal Data

* Temperature
* Humidity
* Batch age
* Storage conditions
* Observed condition over time
* Final outcome

We plan to use public datasets for initial model development and build a controlled experimental dataset for environmental/shelf-life modelling.

---

# ⚠️ Scientific Scope

PerishNet estimates **remaining usable life**; it does not claim to discover an exact universal expiration date.

Environmental sensors provide continuous information about the storage conditions, while visual rescans can be requested when the model needs additional physical verification.

The system is intended as **decision support**, not a guarantee of food safety.

---

# 📈 Evaluation Metrics

### Computer Vision

* Accuracy
* Precision
* Recall
* F1 Score
* IoU / Dice for segmentation where applicable

### Shelf-Life Prediction

* MAE
* RMSE
* Prediction interval coverage
* Error across different storage conditions

### Risk Prediction

* Precision / Recall
* ROC-AUC
* Calibration

### System

* Sensor reliability
* Prediction latency
* API response time
* End-to-end reliability

### Impact

* Potential loss prevented
* High-risk batches identified
* Reduction in unnecessary waste under controlled evaluation

---

# 👥 Team

### Product & AI Systems Architect

**Rohan Sagar**

Owns:

* Product architecture
* AI strategy
* System integration
* Shelf-life intelligence
* Decision-engine design
* Technical direction

### Machine Learning & Computer Vision Engineer

Owns:

* Produce recognition
* Visual quality assessment
* Defect detection
* ML training and evaluation

### IoT & Edge Intelligence Engineer

Owns:

* Sensor pod
* ESP32
* Environmental sensing
* Device communication
* Edge monitoring

### Software & Data Engineer

Owns:

* Backend
* APIs
* Database
* Sensor data pipeline
* Model integration

### Frontend & Decision Intelligence Engineer

Owns:

* Web/app interface
* Dashboards
* Alerts
* What-if simulator
* Visualization

---

# 🚀 Future Scope

PerishNet can evolve toward:

* Multi-produce support
* Smart cold-storage integration
* Fleet-level transport monitoring
* Predictive inventory management
* Produce-specific sensing
* Advanced IoT devices
* Supply-chain analytics
* Automated intervention workflows
* Large-scale post-harvest loss analytics

The long-term vision is:

> **From a smart sensor + AI application into an intelligence layer for perishable inventory.**

---

# 🌱 Vision

PerishNet aims to shift food management from:

> **Inspect → Discover Spoilage → Lose Product**

to:

> **Sense → Predict → Act → Prevent Loss**

### **Don't detect waste. Prevent it.**

---

## ⭐ Project Status

🚧 **Currently under development for Smart India Hackathon 2026**

The repository will evolve as the team develops:

* AI models
* IoT prototype
* Backend
* Frontend
* Dataset pipeline
* Experiments
* Documentation

---

## 🤝 Contributing

PerishNet is currently being developed as a hackathon project. Contributions, research ideas, testing feedback, and technical discussions are welcome as the project evolves.

---

## 📄 License

This project is currently developed for educational, research, and hackathon purposes.

License details will be added as the project reaches a stable release.

---

<p align="center">

### 🍃 PerishNet

**Scan Once. Monitor Continuously. Prevent Waste.**

</p>
