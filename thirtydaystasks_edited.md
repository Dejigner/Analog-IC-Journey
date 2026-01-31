cd "d:\Career 26\Analog IC\Portfolio Website\Website versions\v2" ; git add -A ; git commit -m "t" ; git push

# 6-Month Analog IC Design Roadmap - Daily Tasks (Days 1-30)

**Start Date:** Friday, January 31, 2026  
**Month 1-2 Complete Daily Schedule**


---

## **MONTH 1: FOUNDATIONS (January 31 - March 1, 2026)**

### **Week 1: MOS Transistor Fundamentals**

---

#### **Day 1 - Friday, January 31, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-6:30: Setup
  - Create GitHub account: github.com/[yourname]
  - Create repository: "analog-ic-journey"
  - Add README.md with journey goals

☐ 6:30-7:30: Reading
  - Book: Razavi "Fundamentals of Microelectronics" Ch 1.1-1.3
  - Pages: 1-25 (Introduction to Microelectronics)
  - Focus: Why analog matters, basic semiconductor physics
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:00: Software Installation
  - Download and install LTspice XVII from analog.com/ltspice
  - Complete LTspice tutorial (Help → Examples)
  - Run example schematic: RC circuit
  - Familiarize with: component placement, wiring, simulation commands

☐ 8:00-8:45: First Simulation
  - Build: Voltage divider (10kΩ, 10kΩ, 5V source)
  - Simulate: .op (DC operating point)
  - Verify: Middle node = 2.5V
  - Screenshot and save: day01_first_simulation.png

☐ 8:45-9:00: Lab Journal
  - Create lab journal document
  - Document: What you built, results, screenshots
  - Note key learning: "LTspice basics"
```

**Documentation (9:00-9:30 PM) - 30 minutes**
```
☐ Commit to GitHub:
  - Create folder: /notes/week01/
  - Add file: day01_notes.md with today's notes
  - Add screenshot to /circuits/week01/
  - Commit message: "Day 1: Introduction and first simulation"
```

**Total Time Today:** 4 hours

---

#### **Day 2 - Saturday, February 1, 2026**

**Morning Session (9:00-12:00 PM) - 3 hours**
```
☐ 9:00-10:30: Reading
  - Book: Razavi "Fundamentals" Ch 2.1-2.2
  - Pages: 27-50 (MOS Device Physics, I-V Characteristics)
  - Key concepts:
    * MOSFET structure (gate, source, drain, body)
    * Three regions: cutoff, triode, saturation
    * Equations: I_D = f(V_GS, V_DS)
  - Hand-draw: MOSFET cross-section
  - Copy key equations into notes

☐ 10:30-10:45: Break

☐ 10:45-12:00: Video Lecture
  - Watch: Ali Hajimiri Caltech EE105 Lecture 3
  - YouTube: Search "Hajimiri Lecture 3 MOSFET"
  - Duration: ~50 minutes
  - Note timestamps of key concepts:
    * [Time]: Threshold voltage explanation
    * [Time]: Saturation region
  - Take Pass 1 notes (timestamps only)
```

**Afternoon Session (1:00-4:00 PM) - 3 hours**
```
☐ 1:00-2:30: LTspice Practice
  - Create MOSFET I-V curve simulation
  - Circuit:
    * NMOS: Use built-in model (right-click → pick device)
    * V_GS: 0.6V (DC source)
    * V_DS: 0V (we'll sweep this)
    * Ground and connections
  - Simulation command:
    .dc V_DS 0 1.8 0.01 V_GS 0.3 0.9 0.1
  - Run and observe: Family of I-V curves
  - Screenshot: Annotate regions (triode, saturation)

☐ 2:30-3:30: Analysis
  - Identify on plot:
    * Where is triode region?
    * Where is saturation region?
    * What is V_DSsat for each V_GS?
  - Compare to textbook Figure 2.8 (Razavi)
  - Document observations in lab journal

☐ 3:30-4:00: Organized Documentation
  - Save LTspice file: /circuits/week01/day02_mosfet_iv.asc
  - Export plot data: File → Export
  - Create comparison: Theory (from book) vs Simulation
  - Add to GitHub
```

**Evening Session (4:00-6:00 PM) - 2 hours**
```
☐ 4:00-5:00: Video Content Planning
  - Review week's topic: MOSFET basics
  - Outline first video:
    1. Intro: What is a MOSFET? (2 min)
    2. Simulating I-V curves (5 min)
    3. Understanding the regions (3 min)
  - Screen record: Simulation process (don't edit yet)
  - Save recording: /content/week01/raw_footage.mp4

☐ 5:00-6:00: Deep Review
  - Re-read today's textbook pages
  - Watch Hajimiri lecture segments marked "important"
  - Create visual concept map: MOSFET operation
  - Self-quiz: Explain saturation condition without notes
```

**Documentation (6:00-6:30 PM)**
```
☐ Lab journal: MOSFET I-V simulation entry complete
☐ GitHub commit: 
  - Schematic file
  - Screenshots
  - Notes from reading and lecture
☐ Plan tomorrow: Preview Ch 2.3
```

**Total Time Today:** 8 hours

---

#### **Day 3 - Sunday, February 2, 2026**

**Morning Session (9:00-12:00 PM) - 3 hours**
```
☐ 9:00-10:30: Reading
  - Book: Razavi "Fundamentals" Ch 2.3
  - Pages: 50-72 (MOS Device Models, Small-Signal Operation)
  - Key concepts:
    * Small-signal model
    * Transconductance: g_m = ∂I_D/∂V_GS
    * Output resistance: r_o = ∂V_DS/∂I_D
  - Hand-derive g_m formula:
    g_m = μₙCox(W/L)(V_GS - V_T)
    Also: g_m = √(2μₙCox(W/L)I_D)

☐ 10:30-10:45: Break

☐ 10:45-12:00: Practice Problems
  - Solve: Razavi Problems 2.1, 2.3, 2.5
  - Show all work in notebook
  - Focus on: Given W/L and V_GS, find I_D and g_m
```

**Afternoon Session (1:00-4:00 PM) - 3 hours**
```
☐ 1:00-2:30: Small-Signal Simulation
  - Build in LTspice: Common-source amplifier
    * NMOS: W=10µm, L=1µm
    * R_D = 10kΩ (load resistor)
    * V_DD = 1.8V
    * V_GS = 0.6V (DC bias)
    * V_in = small AC signal (10mV amplitude)
  
  - Simulations:
    1. .op → Check DC operating point
       Verify: V_DS > V_GS - V_T (saturation?)
    
    2. .ac dec 100 1 1G → AC analysis
       Measure: Low-frequency gain
    
    3. Manual g_m calculation:
       From .op, note I_D
       Calculate: g_m = √(2μₙCox(W/L)I_D)
       Compare to gain: A_v = -g_m × R_D

☐ 2:30-3:30: Verification
  - Does simulation match hand calculation?
  - If not, why? (usually process parameters)
  - Adjust MOSFET model if needed
  - Document discrepancy and resolution

☐ 3:30-4:00: Documentation
  - Lab journal: Small-signal amplifier
  - Screenshot: AC response plot
  - Table: Calculated vs Simulated g_m
```

**Evening Session (4:00-6:00 PM) - 2 hours**
```
☐ 4:00-5:00: Weekly Review Prep
  - Re-read all week's notes
  - Create summary sheet: Key equations and concepts
  - Identify weak areas for next week

☐ 5:00-6:00: Video Content
  - Edit Day 2 screen recording
  - Add annotations to I-V curves
  - Keep it simple (don't over-edit)
  - Export draft: week01_mosfet_basics.mp4
```

**Documentation (6:00-7:00 PM)**
```
☐ Week 1 Summary document:
  - Topics covered: MOSFET structure, I-V, small-signal
  - Circuits built: 3 (divider, I-V sweep, CS amp)
  - Questions remaining: List for Week 2

☐ Plan Week 2 in detail
☐ GitHub: Push all week's work
```

**Total Time Today:** 8 hours

---

#### **Day 4 - Monday, February 3, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-6:15: Review
  - Re-read Week 1 summary
  - Quiz yourself on g_m and r_o

☐ 6:15-7:30: Reading
  - Book: Razavi "Fundamentals" Ch 2.4
  - Pages: 72-88 (Body Effect, Channel-Length Modulation)
  - Key concepts:
    * Body effect: How V_SB affects V_T
    * λ (lambda): Channel-length modulation parameter
    * Output resistance: r_o = 1/(λI_D)
  - Note when body effect matters (source not at ground)
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Simulation - Output Resistance
  - Build circuit to measure r_o:
    * NMOS with fixed V_GS
    * Sweep V_DS in saturation region
    * Plot: I_D vs V_DS
  
  - Measure r_o:
    * Pick two points in saturation
    * r_o = ΔV_DS / ΔI_D
    * Compare to: r_o = 1/(λI_D)
  
  - Vary device length:
    * Try L = 0.5µm, 1µm, 2µm, 5µm
    * Observe: Longer L → higher r_o
    * Plot: r_o vs L

☐ 8:30-9:00: Documentation
  - Lab journal: Output resistance measurement
  - Key finding: "Longer channel → better current source"
  - Screenshot: r_o vs L plot
```

**Documentation (9:00-9:30 PM)**
```
☐ Add finding to "Design Rules" document:
  "Use L ≥ 2µm for current sources (high r_o needed)"
☐ GitHub commit: r_o measurement results
```

**Total Time Today:** 4 hours

---

#### **Day 5 - Tuesday, February 4, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:00: Reading
  - Book: Razavi "Fundamentals" Ch 3.1-3.2
  - Pages: 89-110 (Single-Stage Amplifiers, CS Configuration)
  - Key concepts:
    * Common-Source (CS) amplifier
    * Common-Gate (CG) amplifier  
    * Common-Drain (CD) amplifier / Source Follower
  - Note trade-offs: Gain vs input/output impedance

☐ 7:00-7:30: Video
  - Watch: Jordan Edmunds "Common Source Amplifier"
  - YouTube: Search "Jordan Edmunds common source"
  - Take Pass 2 notes (detailed)
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:45: Design Exercise
  - Task: Design CS amplifier for gain = -10
  
  - Design process:
    1. Choose V_DD = 1.8V, I_D = 100µA
    2. Calculate needed g_m:
       A_v = -g_m × R_D = -10
       Pick R_D = 10kΩ → g_m = 1mS needed
    3. Calculate W/L:
       g_m = √(2μₙCox(W/L)I_D)
       Solve for W/L
    4. Choose practical values (W = ?µm, L = 2µm)
  
  - Build in LTspice and verify
  - Iterate if gain not exactly -10

☐ 8:45-9:00: Documentation
  - Design process documented
  - Hand calculations vs simulation
```

**Documentation (9:00-9:30 PM)**
```
☐ Create design methodology document:
  "CS Amp Design Flow: Specs → g_m → W/L → Verify"
☐ Commit design files and notes
```

**Total Time Today:** 4 hours

---

#### **Day 6 - Wednesday, February 5, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Fundamentals" Ch 3.2-3.3
  - Pages: 110-135 (CG and CD Configurations)
  - Compare all three:
    * CS: High gain, moderate Z_in, moderate Z_out
    * CG: Low Z_in, high Z_out, gain ≈ CS
    * CD: High Z_in, low Z_out, gain ≈ 1
  - Create comparison table in notes
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Build All Three Topologies
  - Common-Source: (already have)
  - Common-Gate: Build new
  - Common-Drain: Build new
  
  - For each, measure:
    * Voltage gain
    * Input impedance (AC analysis)
    * Output impedance
  
  - Create comparison table:
    | Topology | A_v | Z_in | Z_out | Use Case |
    |----------|-----|------|-------|----------|
    | CS       |     |      |       |          |
    | CG       |     |      |       |          |
    | CD       |     |      |       |          |

☐ 8:30-9:00: Analysis
  - When to use each topology?
  - Document decision flowchart
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Three amplifier topologies
☐ Create "Amplifier Selection Guide" document
☐ Commit with comparison table
```

**Total Time Today:** 4 hours

---

#### **Day 7 - Thursday, February 6, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Review and Problems
  - Review all Week 2 material
  - Solve: Razavi Problems 3.1, 3.4, 3.7, 3.9
  - Focus on: Designing amplifiers from specs
  - Check solutions (back of book or solution manual)
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Frequency Response Introduction
  - Read: Razavi "Fundamentals" Ch 3.4 (preview)
  - Topic: Frequency response of amplifiers
  - Simulate: CS amp with load capacitor (5pF)
  - AC analysis: See gain roll-off
  - Identify: -3dB frequency
  - Calculate: f_-3dB = 1/(2πR_outC_L)
  - Compare to simulation

☐ 8:30-9:00: Documentation
  - Lab journal: Frequency response basics
  - Note: "Capacitance limits bandwidth"
```

**Documentation (9:00-9:30 PM)**
```
☐ Prepare for Week 2 review
☐ List questions for weekend study
```

**Total Time Today:** 4 hours

---

#### **Day 8 - Friday, February 7, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Comprehensive Review
  - Create Week 2 summary document
  - Topics: Body effect, λ, three amp configs, frequency response
  - Self-quiz: Design each amplifier type from memory
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Design Challenge
  - Specs: Design CS amplifier with:
    * Gain = -15
    * Bandwidth > 1MHz
    * Power < 500µW
    * V_DD = 1.8V
  
  - Design process:
    1. Calculate g_m from gain
    2. Calculate I_D from power
    3. Calculate W/L from g_m and I_D
    4. Check bandwidth
    5. Iterate if needed
  
  - Document entire process

☐ 8:30-9:00: Documentation
  - Complete design report
  - This is portfolio piece #1
```

**Documentation (9:00-9:30 PM)**
```
☐ Week 2 complete summary
☐ Prepare video footage for editing
```

**Total Time Today:** 4 hours

---

#### **Day 9 - Saturday, February 8, 2026**

**Project Day (9:00 AM - 6:00 PM) - 8 hours**
```
☐ 9:00-12:00: Major Project - Amplifier Library
  - Create LTspice library with:
    1. CS amplifier (3 variants: low-power, high-gain, high-BW)
    2. CG amplifier (2 variants)
    3. CD amplifier (2 variants)
  
  - For each:
    * Schematic
    * Symbol (for hierarchical design)
    * Test bench
    * Performance table
  
  - Document design choices

☐ 12:00-1:00: Lunch

☐ 1:00-4:00: Cadence Introduction (if available)
  - Install/access Cadence Virtuoso
  - Follow basic tutorial:
    * Create library
    * Create cell view (schematic)
    * Place components
    * Basic simulation setup
  
  - If no Cadence access yet:
    * Apply for academic license
    * Meanwhile, continue with LTspice
    * Practice advanced LTspice features

☐ 4:00-6:00: Video Content
  - Edit Week 1 video: "MOSFET Basics"
  - Structure:
    1. Intro: What I'm learning (30 sec)
    2. I-V curves simulation (3 min)
    3. Three regions explained (2 min)
    4. What I learned (1 min)
  - Add simple title/transitions
  - Export: week01_mosfet_basics.mp4
```

**Evening (6:00-8:00 PM)**
```
☐ 6:00-7:00: GitHub Organization
  - Clean up repository structure:
    /circuits
      /week01
      /week02
    /notes
      /week01
      /week02
    /content
      /week01
  
  - Update main README.md:
    * Journey progress
    * Circuits designed so far
    * Links to each week's work

☐ 7:00-8:00: Community Engagement
  - Reddit: Post in r/chipdesign
    "2 weeks into analog IC design journey - Here's what I built"
    Include screenshot of amplifier comparison
  - Respond to 3-5 posts from others
  - Ask one question about Week 3 topic (current mirrors)
```

**Total Time Today:** 8 hours

---

#### **Day 10 - Sunday, February 9, 2026**

**Content & Planning Day (9:00 AM - 5:00 PM) - 8 hours**
```
☐ 9:00-11:00: Video Editing
  - Edit Week 2 video: "Amplifier Topologies Compared"
  - Show all three topologies side-by-side
  - Explain when to use each
  - Include simulation results
  - Export video

☐ 11:00-12:00: Content Publishing
  - Upload both videos to YouTube:
    1. Week 1: MOSFET Basics
    2. Week 2: Amplifier Topologies
  
  - Video descriptions with timestamps:
    0:00 - Introduction
    0:30 - Concept explanation
    X:XX - Simulation demo
    etc.
  
  - Tags: Analog IC Design, MOSFET, LTspice, Electronics

☐ 12:00-1:00: Lunch

☐ 1:00-3:00: Community Engagement
  - Twitter/X posting (if you have account)
  - Engage with 10-15 posts in analog design community
  - Connect with analog designers
  - Comment thoughtfully on their content

☐ 3:00-5:00: Week 3 Planning
  - Preview: Razavi Ch 3.4-3.6 (Current Mirrors)
  - Watch: Hajimiri Lecture 12 (first 10 minutes)
  - Create Week 3 detailed schedule
  - Prepare lab templates for Week 3
```

**Total Time Today:** 8 hours
**Week 2 Total:** 40 hours

---

### **Week 3: Current Sources and Mirrors**

#### **Day 11 - Monday, February 10, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Fundamentals" Ch 3.4
  - Pages: 136-158 (Current Mirrors)
  - Key concepts:
    * Why we need current mirrors in analog design
    * Basic two-transistor mirror operation
    * Current matching: I_out = I_ref × (W/L)_2/(W/L)_1
    * Output resistance of simple mirror
  
  - Hand-draw:
    * Basic NMOS current mirror
    * Basic PMOS current mirror
    * Diode-connected transistor concept
  
  - Note applications:
    * Biasing for amplifiers
    * Active loads for differential pairs
    * Reference current distribution
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: First Current Mirror Simulation
  - Build in LTspice: Basic NMOS current mirror
    * M1: W=10µm, L=2µm (reference, diode-connected)
    * M2: W=10µm, L=2µm (mirror)
    * I_ref = 100µA (ideal current source)
    * V_DD = 1.8V
  
  - Tests:
    1. .op analysis:
       - Check I_D of M2 ≈ 100µA?
       - Verify both transistors in saturation
       - Note V_GS of both (should be equal)
    
    2. DC sweep V_out (drain of M2) from 0 to 1.8V:
       - Plot I_out vs V_out
       - Observe: Current constant in saturation
       - Find V_out,min (where current drops)
    
    3. Measure output resistance:
       - r_o = ΔV_out / ΔI_out (in saturation)
       - Typical value: 100-500kΩ

☐ 8:30-9:00: Analysis
  - Compare to hand calculation:
    * Expected I_out = I_ref (since W/L matched)
    * Expected r_o = 1/(λI_D)
  - Document discrepancies
  - Understand: r_o is moderate (not ideal current source)
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Basic current mirror characterization
☐ Screenshot: I_out vs V_out plot annotated
☐ Note key finding: "Simple mirror has r_o ~ 200kΩ, not ideal"
☐ GitHub commit
```

**Total Time Today:** 4 hours

---

#### **Day 12 - Tuesday, February 11, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-6:30: Review Day 11
  - Re-read yesterday's lab journal
  - Quiz: Draw current mirror from memory

☐ 6:30-7:30: Video Lecture
  - Watch: Ali Hajimiri Caltech Lecture 12 "Current Mirrors"
  - YouTube: Search "Hajimiri current mirrors"
  - Duration: ~55 minutes
  - Take Pass 2 notes (detailed):
    * [05:30] - Why current mirrors needed
    * [12:45] - Basic mirror analysis
    * [23:10] - Cascode improvement ⭐
    * [34:20] - Wide-swing cascode
    * [45:00] - Design example ⭐⭐
  
  - Pause and replay [23:10-28:00] section:
    * How cascode improves r_out
    * Derivation: r_out,cascode = g_m × r_o²
    * Trade-off: Headroom vs output impedance
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Current Ratio Experiment
  - Modify current mirror:
    * Keep M1: W=10µm, L=2µm
    * Vary M2: Try different W/L ratios
  
  - Test cases:
    1. W=10µm, L=2µm → I_out should = 100µA
    2. W=20µm, L=2µm → I_out should = 200µA
    3. W=5µm, L=2µm → I_out should = 50µA
    4. W=10µm, L=4µm → I_out should = 50µA
  
  - Create table:
    | (W/L)_1 | (W/L)_2 | Expected Ratio | Simulated I_out | Error % |
    |---------|---------|----------------|-----------------|---------|
    | 5       | 5       | 1:1            | 99.2µA          | 0.8%    |
    | 5       | 10      | 1:2            |                 |         |
    | etc.    |         |                |                 |         |

☐ 8:30-9:00: Mismatch Analysis (Introduction)
  - Read: Razavi "Fundamentals" Ch 3.4.2 (Mismatch)
  - Understand: Process variations affect matching
  - Preview: Monte Carlo simulation (will do tomorrow)
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Current ratio experiments
☐ Table of results
☐ Key insight: "Ratio matching works! Error < 2%"
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 13 - Wednesday, February 12, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Fundamentals" Ch 3.4.3-3.4.4
  - Pages: 158-175 (Cascode Current Mirror, Matching)
  - Key concepts:
    * Cascode topology stacks transistors
    * Output resistance improvement: 100x typical
    * r_out = g_m × r_o² derivation
    * Headroom cost: V_DSsat,M1 + V_DSsat,M3
  
  - Hand-derive r_out equation:
    [Follow textbook derivation step-by-step]
  
  - Note design trade-off:
    * Simple mirror: Low r_out, good headroom
    * Cascode: High r_out, poor headroom
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Cascode Current Mirror Design
  - Build in LTspice:
    * M1, M2: Bottom transistors (10/2)
    * M3, M4: Cascode devices (10/2)
    * Bias: V_b connected to gate of M1
    * I_ref = 100µA
  
  - Tests:
    1. DC operating point:
       - All transistors in saturation?
       - Check V_DS of each
    
    2. Output resistance measurement:
       - DC sweep V_out
       - Measure r_out from slope
       - Compare to simple mirror
    
    3. Headroom measurement:
       - Find minimum V_out before current drops
       - Compare to simple mirror
  
  - Results table:
    | Topology | r_out | V_out,min | Improvement Factor |
    |----------|-------|-----------|-------------------|
    | Simple   | 200kΩ | 0.2V      | 1×                |
    | Cascode  | ?     | ?         | ?×                |

☐ 8:30-9:00: Analysis
  - Did r_out improve by ~100×? (Theory predicts 50-100×)
  - What is headroom cost? (Typically 0.3-0.5V additional)
  - When is this trade-off worth it?
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Cascode vs simple mirror comparison
☐ Side-by-side schematics screenshot
☐ Comparison plots
☐ Design decision guide: "When to use cascode"
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 14 - Thursday, February 13, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:00: Reading
  - Book: Razavi "Fundamentals" Ch 3.4.5
  - Pages: 175-185 (Wide-Swing Cascode, Low-Voltage)
  - Key concepts:
    * Problem: Regular cascode wastes headroom
    * Solution: Lower V_GS on cascode devices
    * Implementation: Separate bias circuit
    * When to use: Low-voltage designs (<1.5V)

☐ 7:00-7:30: Problems
  - Solve: Razavi Problems 3.12, 3.14, 3.16
  - Focus: Current mirror design from specs
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Monte Carlo Simulation (Mismatch)
  - LTspice Monte Carlo setup:
    * .step param run 1 50 1
    * Add device mismatch:
      .param V_T_dev = gauss(0.4, 0.01)
      (Mean 0.4V, std dev 10mV)
    * Apply to both M1 and M2
  
  - Run 50 iterations
  - Plot histogram of I_out
  - Calculate:
    * Mean current
    * Standard deviation
    * Min/Max values
    * % within ±5% of target
  
  - Experiment: Effect of length on matching
    * Run with L=0.5µm
    * Run with L=2µm
    * Run with L=5µm
    * Compare σ/mean for each

☐ 8:30-9:00: Analysis
  - Key finding: Longer L → better matching
  - Document design rule:
    "Use L ≥ 2µm for critical current mirrors"
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Monte Carlo mismatch analysis
☐ Histogram plots for different L values
☐ Statistical summary table
☐ Design rule added to reference document
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 15 - Friday, February 14, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Comprehensive Review
  - Review all Week 3 notes
  - Create summary: Current Mirror Design Guide
  - Include:
    * When to use simple mirror
    * When to use cascode
    * When to use wide-swing
    * Matching considerations
    * Design procedure
  
  - Self-quiz:
    * Design a 200µA current mirror from specs
    * Choose topology based on constraints
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Current Mirror Library
  - Create LTspice symbols for:
    1. Simple NMOS mirror (parameterized)
    2. Simple PMOS mirror
    3. Cascode NMOS mirror
    4. Cascode PMOS mirror
  
  - For each:
    * Hierarchical symbol
    * Test bench
    * Performance verification
  
  - Document usage in README

☐ 8:30-9:00: Week 3 Summary
  - Complete all documentation
  - Identify any gaps
```

**Documentation (9:00-9:30 PM)**
```
☐ Week 3 complete summary
☐ Current mirror design guide (portfolio piece)
☐ Library documentation
☐ Prepare content for weekend video
☐ Commit all week's work
```

**Total Time Today:** 4 hours

---

#### **Day 16 - Saturday, February 15, 2026**

**Project Day (9:00 AM - 6:00 PM) - 8 hours**
```
☐ 9:00-12:00: Design Challenge
  - Project: Precision Current Reference
  - Specs:
    * Output current: 100µA ± 1%
    * Output impedance: >10MΩ
    * Supply voltage: 1.8V
    * Min output voltage: <0.5V
    * Temperature: 0-70°C
  
  - Design approach:
    1. Choose topology (cascode for high r_out)
    2. Calculate component sizes
    3. Simulate nominal performance
    4. Monte Carlo verification (matching)
    5. Temperature sweep
    6. Optimize if needed
  
  - Document entire design process

☐ 12:00-1:00: Lunch

☐ 1:00-4:00: Cadence Practice (if available)
  - Task: Rebuild current mirror in Cadence Virtuoso
  
  - Steps:
    1. Create new library: "analog_basics"
    2. Create cell: "current_mirror_simple"
    3. Schematic entry:
       - Place NMOS devices from PDK
       - Set W/L parameters
       - Add pins for connectivity
    4. Create symbol view
    5. Test bench setup
    6. ADE L (Analog Design Environment):
       - DC analysis
       - Parametric sweep
    7. Run simulation in Spectre
    8. Compare to LTspice results
  
  - If no Cadence access:
    * Continue refining LTspice designs
    * Practice hierarchical design
    * Advanced LTspice features (parameters, .measure)

☐ 4:00-6:00: Video Content Creation
  - Edit video: "Current Mirrors Explained"
  - Structure:
    1. Intro: Why current mirrors? (1 min)
    2. Simple mirror simulation (3 min)
    3. The problem with r_out (2 min)
    4. Cascode solution (3 min)
    5. Trade-offs summary (1 min)
  
  - Include:
    * Side-by-side comparison plots
    * Annotated schematics
    * Key equations on screen
  
  - Export: week03_current_mirrors.mp4
```

**Evening (6:00-8:00 PM)**
```
☐ 6:00-7:00: Portfolio Documentation
  - Update GitHub README:
    * Week 3 completed
    * Current mirror library added
    * Link to design challenge solution
  
  - Create project page: "Precision Current Reference"
    * Include full design report
    * Schematics, plots, analysis
    * Design decisions explained

☐ 7:00-8:00: Community Engagement
  - Reddit r/chipdesign post:
    "Week 3: Built precision current source with >10MΩ r_out"
    Include comparison: simple vs cascode performance
  
  - Comment on 5 other posts
  - Answer beginner questions if any
```

**Total Time Today:** 8 hours

---

#### **Day 17 - Sunday, February 16, 2026**

**Review & Planning Day (9:00 AM - 5:00 PM) - 8 hours**
```
☐ 9:00-11:00: Month 1 Comprehensive Review
  - Re-read all three weeks of notes
  - Create Month 1 Master Summary:
    * MOSFETs: I-V characteristics, small-signal model
    * Amplifiers: CS, CG, CD topologies
    * Current Mirrors: Simple, cascode, matching
  
  - Self-assessment quiz:
    * Design CS amp from specs (15 min)
    * Design current mirror from specs (15 min)
    * Explain trade-offs without notes (15 min)

☐ 11:00-12:00: Video Publishing
  - Upload Week 3 video to YouTube
  - Title: "Current Mirrors: From Basic to Cascode"
  - Detailed description with timestamps
  - Tags: current mirror, analog design, IC design
  
  - Create playlist: "Analog IC Design Journey"
    * Add all three videos
    * Organize by week

☐ 12:00-1:00: Lunch

☐ 1:00-3:00: Community Activity
  - Engage with comments on your previous videos
  - Twitter/X thread on Month 1 achievements
  - Reddit update post

☐ 3:00-5:00: Month 2 Planning
  - Preview topics:
    * Week 4-5: Differential pairs, CMRR, active loads
    * Week 6-7: Two-stage op-amp design
    * Week 8: First paper recreation
  
  - Read ahead: Razavi "Fundamentals" Ch 4.1
    "Differential Amplifiers" (first 10 pages)
  
  - Create detailed Week 4 schedule
  - Set up lab journal templates
  - Prepare simulation workspace
  
  - Month 2 goals:
    * Design complete two-stage op-amp
    * Recreate one research paper
    * Start learning Cadence layout basics
    * Publish 4 videos
```

**Total Time Today:** 8 hours
**Week 3 Total:** 40 hours
**Month 1 Total:** ~120 hours

---

## **MONTH 2: DIFFERENTIAL PAIRS & OP-AMPS (March 1-31, 2026)**

### **Week 4: Differential Amplifiers**

#### **Day 18 - Monday, February 17, 2026** (Presidents' Day - Extra time available)

**Extended Morning Session (9:00 AM - 12:00 PM) - 3 hours**
```
☐ 9:00-10:30: Reading
  - Book: Razavi "Fundamentals" Ch 4.1-4.2
  - Pages: 186-215 (Differential Pair Introduction, Operation)
  - Key concepts:
    * Why differential > single-ended
    * Differential vs common-mode signals
    * Basic diff pair with resistive load
    * Tail current source role
    * Input-output relationship
  
  - Hand-derive:
    * Differential gain: A_dm = g_m × R_D
    * Common-mode gain: A_cm ≈ 0 (ideally)
    * CMRR = A_dm / A_cm
  
  - Understand intuitively:
    * When V_in+ goes up and V_in- goes down:
      - M1 current increases
      - M2 current decreases
      - Differential output created

☐ 10:30-10:45: Break

☐ 10:45-12:00: Video Lecture
  - Watch: Ali Hajimiri Lecture 14 "Differential Amplifiers"
  - YouTube: Search "Hajimiri Lecture 14 differential"
  - Duration: ~55 minutes
  - Take detailed Pass 2 notes:
    * [Timestamp] - Why differential amplifiers
    * [Timestamp] - Diff mode vs common mode
    * [Timestamp] - CMRR explanation ⭐
    * [Timestamp] - Tail current source importance
  
  - Pause and replay CMRR section:
    * How tail resistance affects CMRR
    * Why cascode tail is better
```

**Afternoon Session (1:00-4:00 PM) - 3 hours**
```
☐ 1:00-3:00: First Differential Pair Simulation
  - Build in LTspice:
    * M1, M2: NMOS W=20µm, L=2µm (input pair)
    * R_D1, R_D2: 10kΩ each (loads)
    * M_tail: Current source, I_SS = 200µA
    * V_DD = 1.8V
    * V_CM = 0.9V (common-mode input)
  
  - Test 1: DC Operating Point
    .op
    - Verify: I_D1 = I_D2 = 100µA (split equally)
    - Check: Both M1, M2 in saturation
    - Note: V_out1 = V_out2 = V_DD - I_D×R_D
  
  - Test 2: Differential-Mode Gain
    * Apply: V_in+ = V_CM + 10mV, V_in- = V_CM - 10mV
    * .tran simulation
    * Measure: V_out1 - V_out2 (differential output)
    * Calculate: A_dm = ΔV_out,diff / ΔV_in,diff
    * Compare to: A_dm = g_m × R_D (hand calculation)
  
  - Test 3: Common-Mode Gain
    * Apply: V_in+ = V_in- = V_CM + 10mV
    * Measure: (V_out1 + V_out2)/2
    * Calculate: A_cm = ΔV_out,cm / ΔV_in,cm
    * Should be very small!
  
  - Test 4: CMRR Calculation
    * CMRR = A_dm / A_cm
    * Convert to dB: CMRR_dB = 20×log10(CMRR)
    * Target: >60dB for good design

☐ 3:00-4:00: Detailed Analysis
  - Create results table:
    | Metric | Hand Calc | Simulation | Match? |
    |--------|-----------|------------|--------|
    | I_D1 = I_D2 | 100µA | __µA | ☐ |
    | A_dm | __dB | __dB | ☐ |
    | A_cm | ~0 | __dB | ☐ |
    | CMRR | >60dB | __dB | ☐ |
  
  - Annotate waveforms:
    * Differential-mode response
    * Common-mode response
    * Save screenshots
```

**Evening Session (4:00-6:00 PM) - 2 hours**
```
☐ 4:00-5:30: Tail Current Source Effect
  - Experiment: Replace ideal tail current with:
    1. Resistor (poor CMRR)
    2. Simple NMOS current mirror (moderate CMRR)
    3. Cascode current mirror (excellent CMRR)
  
  - For each, measure CMRR:
    | Tail Type | r_tail | CMRR (dB) | Improvement |
    |-----------|--------|-----------|-------------|
    | Resistor 10kΩ | 10kΩ | __dB | Baseline |
    | Simple mirror | ~200kΩ | __dB | __× |
    | Cascode | ~10MΩ | __dB | __× |
  
  - Understand relationship:
    CMRR ≈ 2 × g_m × r_tail
    Higher r_tail → Higher CMRR ✓

☐ 5:30-6:00: Documentation
  - Lab journal: Differential pair characterization
  - Key finding: "Tail current source impedance critical for CMRR"
  - Design rule: "Use cascode tail for CMRR > 80dB"
```

**Documentation (6:00-6:30 PM)**
```
☐ Comparison plots: Different tail implementations
☐ CMRR vs r_tail graph
☐ Commit to GitHub
```

**Total Time Today:** 8 hours

---

#### **Day 19 - Tuesday, February 18, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:00: Reading
  - Book: Razavi "Fundamentals" Ch 4.3
  - Pages: 215-235 (Differential Pair with Active Load)
  - Key concepts:
    * Current mirror as active load
    * Why active load >> resistive load
    * Gain improvement
    * Single-ended vs differential output
  
  - Compare:
    * Resistive load gain: A_v = g_m × R_D
    * Active load gain: A_v = g_m × r_o (much higher!)

☐ 7:00-7:30: Problems
  - Solve: Razavi Problems 4.1, 4.3, 4.5
  - Focus: Calculating diff pair performance
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Differential Pair with Active Load
  - Build in LTspice:
    * M1, M2: NMOS input pair (20/2)
    * M3, M4: PMOS current mirror load (40/2)
    * M5: NMOS cascode tail (10/2)
    * I_ref = 200µA
    * V_DD = 1.8V
  
  - Design steps:
    1. Size input pair for desired g_m
    2. Size PMOS load (typically 2× wider for mobility difference)
    3. Verify all transistors saturated
  
  - Performance tests:
    1. DC gain (should be 40-50dB, vs ~20dB with resistors)
    2. CMRR (with cascode tail, should be >70dB)
    3. Output swing (check max/min output voltage)
  
  - Compare active vs resistive load:
    | Load Type | Gain (dB) | CMRR (dB) | Output Swing |
    |-----------|-----------|-----------|--------------|
    | Resistive | __dB | __dB | __V |
    | Active | __dB | __dB | __V |

☐ 8:30-9:00: Analysis
  - Why is gain higher?
    * r_o >> R_D (typically 10× or more)
  - Understand trade-off:
    * Higher gain ✓
    * Reduced output swing ✗ (due to PMOS V_DSsat)
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Active load diff pair
☐ Side-by-side comparison with resistive load
☐ Annotated schematic explaining current flow
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 20 - Wednesday, February 19, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Fundamentals" Ch 4.4
  - Pages: 235-255 (Frequency Response, Input Range)
  - Key concepts:
    * Frequency response of diff pair
    * Dominant pole at output
    * Input common-mode range (ICMR)
    * Why ICMR matters
  
  - Calculate ICMR limits:
    * Upper limit: V_CM,max
    * Lower limit: V_CM,min
    * Valid input range
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Frequency Response Analysis
  - LTspice AC analysis:
    .ac dec 100 1 1G
  
  - Measurements:
    1. Low-frequency gain (at 1Hz)
    2. -3dB bandwidth
    3. Dominant pole location
    4. Verify: f_p = 1/(2πR_outC_L)
  
  - Add load capacitor variations:
    * C_L = 1pF, 5pF, 10pF
    * Plot: Gain and phase for each
    * Observe: Bandwidth decreases with C_L
  
  - Create Bode plots:
    * Magnitude response
    * Phase response
    * Annotate pole locations

☐ 8:30-9:00: Input Common-Mode Range Test
  - DC sweep of V_CM:
    * Sweep from 0V to V_DD
    * Plot: I_D1, I_D2, V_out vs V_CM
  
  - Identify valid range:
    * Lower limit: Where tail leaves saturation
    * Upper limit: Where input pair enters triode
    * Document ICMR: [V_CM,min to V_CM,max]
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: Frequency response and ICMR
☐ Bode plots saved
☐ ICMR sweep plot with annotations
☐ Design note: "ICMR constraints for diff pair design"
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 21 - Thursday, February 20, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:00: Review Week 4 So Far
  - Re-read all diff pair notes
  - Create summary sheet:
    * Diff pair operation
    * CMRR and how to improve it
    * Active vs resistive loads
    * Frequency response
    * ICMR

☐ 7:00-7:30: Video
  - Watch: Razavi's own lectures on differential pairs
  - YouTube: "Razavi differential amplifier"
  - Take notes on any new insights
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Design Challenge
  - Specs: Design differential amplifier with:
    * Differential gain: >45dB
    * CMRR: >70dB
    * Bandwidth: >1MHz
    * Power: <2mW
    * V_DD = 1.8V
    * C_L = 5pF
  
  - Design process:
    1. Choose topology (active load for high gain)
    2. Calculate required g_m from gain and r_o
    3. Calculate I_D from power budget
    4. Size transistors (W/L)
    5. Design cascode tail for CMRR
    6. Simulate and verify all specs
    7. Iterate if needed
  
  - Document:
    * Hand calculations
    * Design decisions and trade-offs
    * Iteration log
    * Final performance

☐ 8:30-9:00: Verification
  - Create spec checklist:
    ☐ Gain >45dB: Measured __dB ✓/✗
    ☐ CMRR >70dB: Measured __dB ✓/✗
    ☐ BW >1MHz: Measured __MHz ✓/✗
    ☐ Power <2mW: Measured __mW ✓/✗
  
  - If any spec fails, identify bottleneck and fix
```

**Documentation (9:00-9:30 PM)**
```
☐ Complete design report: "Differential Amplifier Design"
☐ This is portfolio piece #2
☐ Include: specs, schematics, calculations, results
☐ Commit as project to GitHub
```

**Total Time Today:** 4 hours

---

#### **Day 22 - Friday, February 21, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Comprehensive Review
  - Complete Week 4 summary
  - Self-quiz (without notes):
    * Draw diff pair with active load from memory
    * Explain how to improve CMRR
    * Calculate gain given g_m and r_o
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Diff Pair Library Creation
  - Create LTspice symbols:
    1. Diff pair with resistive load
    2. Diff pair with active load
    3. Diff pair with cascode tail (high CMRR)
  
  - For each:
    * Parameterized design (W/L adjustable)
    * Test bench
    * Performance verification script
  
  - Document usage examples

☐ 8:30-9:00: Prep for Week 5
  - Preview: Two-stage op-amp design
  - Read: Razavi "Design of Analog CMOS IC" Ch 9.1 (intro)
  - Understand: Why we need two stages
```

**Documentation (9:00-9:30 PM)**
```
☐ Week 4 complete summary
☐ Diff pair library documentation
☐ Video footage preparation (screenshots, recordings)
☐ Commit all week's work
```

**Total Time Today:** 4 hours

---

#### **Day 23 - Saturday, February 22, 2026**

**Project Day (9:00 AM - 6:00 PM) - 8 hours**
```
☐ 9:00-12:00: Major Project - High-Performance Diff Amp
  - Challenge: Push performance limits
  - Goal: Achieve >50dB gain, >80dB CMRR
  
  - Advanced techniques to try:
    1. Cascoded input pair (higher r_out)
    2. Cascoded current mirror load
    3. Widlar current source for bias
  
  - Full characterization:
    * DC: Gain, CMRR, offset
    * AC: Frequency response
    * Transient: Step response
    * Monte Carlo: Mismatch analysis
  
  - Document every design decision

☐ 12:00-1:00: Lunch

☐ 1:00-4:00: Cadence Work
  - If Cadence available:
    * Recreate diff pair in Virtuoso
    * Learn: ADE XL for parametric analysis
    * Run corners: TT, FF, SS, FS, SF
    * Compare to LTspice results
  
  - If no Cadence:
    * Advanced LTspice techniques:
      - .measure statements for automation
      - Parametric sweeps (.step)
      - Temperature analysis
    * Practice hierarchical design
    * Create reusable blocks

☐ 4:00-6:00: Video Editing
  - Edit: "Differential Amplifiers Explained"
  - Structure:
    1. Intro: Why differential? (1 min)
    2. Basic operation demonstration (3 min)
    3. CMRR concept and improvement (3 min)
    4. Active load benefit (2 min)
    5. Design example walkthrough (3 min)
    6. Results and key takeaways (1 min)
  
  - Include:
    * Simulation demonstrations
    * Side-by-side comparisons
    * Annotated Bode plots
    * Key equations highlighted
  
  - Export: week04_differential_amplifiers.mp4
```

**Evening (6:00-8:00 PM)**
```
☐ 6:00-7:00: GitHub Portfolio Update
  - Add Week 4 projects
  - Update main README:
    * Progress: 4 weeks complete
    * Circuits: Now includes diff amps
    * Link to diff amp design project
  
  - Create dedicated page for high-performance diff amp:
    * Full design documentation
    * Performance summary table
    * Design insights

☐ 7:00-8:00: Community Engagement
  - Reddit post in r/chipdesign:
    "Designed differential amplifier with 80dB CMRR - Here's how"
    * Include performance comparison table
    * Link to GitHub
  
  - Twitter/X post:
    "Week 4: Differential amplifiers ✓
    Key insight: CMRR is all about tail impedance
    Simple mirror: 60dB
    Cascode tail: 82dB
    Details on my GitHub: [link]
    #AnalogDesign #ICDesign"
  
  - Engage with 5-10 posts in community
```

**Total Time Today:** 8 hours

---

#### **Day 24 - Sunday, February 23, 2026**

**Review & Planning Day (9:00 AM - 5:00 PM) - 8 hours**
```
☐ 9:00-11:00: Week 4 Deep Review
  - Review all notes and simulations
  - Create concept map: Differential amplifiers
    * Connect to previous knowledge (current mirrors)
    * Understand signal flow
    * Identify key design principles
  
  - Practice problems:
    * Design 3 different diff amps from varying specs
    * Check solutions
    * Time yourself (interview prep)

☐ 11:00-12:00: Video Publishing
  - Upload Week 4 video to YouTube
  - Title: "Differential Amplifiers: High Gain & CMRR Explained"
  - Description with detailed timestamps
  - Tags: differential amplifier, CMRR, analog IC
  - Add to "Analog IC Design Journey" playlist

☐ 12:00-1:00: Lunch

☐ 1:00-2:30: Community Engagement
  - Respond to any comments on previous posts/videos
  - Engage with new analog design posts
  - Answer questions in community if any

☐ 2:30-5:00: Week 5 Detailed Planning
  - Topic: Two-Stage Op-Amp Design
  - Read ahead: Razavi "Design of Analog CMOS IC" Ch 9.1-9.2
  
  - Understand what's coming:
    * Why two stages needed
    * Frequency compensation (Miller)
    * Stability requirements
    * Design procedure
  
  - Create Week 5 schedule:
    * Day-by-day learning plan
    * Simulation milestones
    * Video content plan
  
  - Download/bookmark resources:
    * Razavi's op-amp lectures
    * Reference op-amp papers
  
  - Set Week 5 goals:
    * Design complete two-stage op-amp
    * Achieve >60dB gain, >60° phase margin
    * Understand frequency compensation deeply
    * Document full design process
```

**Total Time Today:** 8 hours
**Week 4 Total:** 40 hours

---

### **Week 5-6: Two-Stage Op-Amp Design**

#### **Day 25 - Monday, February 24, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Design of Analog CMOS IC" Ch 9.1-9.2
  - Pages: 297-325 (Op-Amp Introduction, Two-Stage Topology)
  - Key concepts:
    * Op-amp requirements: High gain, stability, rail-to-rail output
    * Why single stage insufficient
    * Two-stage topology: Diff pair + CS output
    * General design flow
  
  - Understand block diagram:
    [Input Diff Pair] → [Second Stage CS] → [Output]
         ↓
    [Frequency Compensation]
  
  - Note key specs for op-amps:
    * DC gain: >60dB (typically 70-100dB)
    * Unity-gain bandwidth (GBW): MHz range
    * Phase margin: >60° (stability requirement)
    * Slew rate: V/µs
    * CMRR, PSRR: >60dB
    * Offset voltage: <10mV
    * Output swing: Close to rail-to-rail
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:30: Paper Reading - Classic Op-Amp
  - Paper: "A Compact Power-Efficient 3 V CMOS Rail-to-Rail 
            Input/Output Operational Amplifier for VLSI Cell Libraries"
  - Authors: R. Hogervorst et al.
  - Venue: IEEE JSSC, December 1994
  - Pages: Read pages 1-5 (Introduction and Architecture)
  
  - Apply 3-Pass Method:
    
    Pass 1 (15 min):
    * Abstract: What problem does it solve?
    * Figures: Look at op-amp architecture (Fig 1-3)
    * Conclusion: What performance achieved?
    * Decision: Worth deep read? (Should be YES)
  
    Pass 2 (60 min):
    * Block diagram understanding
    * Two-stage topology identification
    * Component values extraction (if given)
    * Performance metrics table
    * Take detailed notes
  
  - Focus on understanding:
    * How they chose transistor sizes
    * Compensation scheme used
    * Why this topology for rail-to-rail

☐ 8:30-9:00: Initial Op-Amp Specs
  - Define specs for your own op-amp design:
    * DC Gain: >60dB
    * GBW: >10MHz
    * Phase Margin: >60°
    * Power: <5mW
    * V_DD: 1.8V
    * C_L: 5pF
    * Slew Rate: >5V/µs
    * CMRR: >70dB
  
  - Document these as design targets
```

**Documentation (9:00-9:30 PM)**
```
☐ Paper reading notes (Pass 1 & 2)
☐ Op-amp design spec sheet
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 26 - Tuesday, February 25, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Design of Analog CMOS IC" Ch 9.3
  - Pages: 325-350 (Input Stage Design, Bias Design)
  - Key concepts:
    * Input stage design for required g_m
    * Trade-off: g_m vs power
    * Bias circuit design
    * Startup circuit necessity
  
  - Design equations:
    * g_m1 = √(2μₙCox(W/L)₁I_D)
    * First stage gain: A_v1 = g_m1 × r_out1
    * For diff pair with active load: r_out1 = r_o2 || r_o4
  
  - Hand calculation exercise:
    * Given I_D = 100µA, find W/L for g_m = 1mS
    * Calculate expected first-stage gain
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:45: Design First Stage (Input Differential Pair)
  - Build in LTspice:
    * Input diff pair: M1, M2 (NMOS)
    * Active load: M3, M4 (PMOS current mirror)
    * Tail current: M5 (NMOS, cascode for high CMRR)
    * Bias circuit for tail
  
  - Design steps:
    1. Choose I_SS (tail current):
       - Total power budget: 5mW / 1.8V = 2.78mA available
       - Allocate ~50% to first stage: I_SS = 200µA
    
    2. Size input pair (M1, M2):
       - Need g_m ≈ 1mS (for adequate gain)
       - Using g_m = √(2μₙCox × W/L × I_D)
       - With I_D = 100µA per side
       - Calculate W/L, choose W=20µm, L=2µm
    
    3. Size PMOS load (M3, M4):
       - Match current: Same I_D = 100µA
       - Account for mobility: W_p/W_n ≈ 2.5
       - Choose W=50µm, L=2µm
    
    4. Size tail current source (M5):
       - I_D = 200µA
       - Long channel for high r_out: L=4µm
       - Choose W for proper V_GS
  
  - Simulation verification:
    * .op: Check all currents and V_DS values
    * All transistors in saturation?
    * Measure first-stage gain (AC analysis)
    * Target: 40-50dB

☐ 8:45-9:00: Documentation
  - First stage design documented
  - Hand calculations vs simulation comparison
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: "Op-Amp First Stage Design"
☐ Include: Calculations, schematic, DC operating points
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 27 - Wednesday, February 26, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading
  - Book: Razavi "Design of Analog CMOS IC" Ch 9.4
  - Pages: 350-375 (Second Stage Design, Output Stage)
  - Key concepts:
    * Common-source second stage
    * Sizing for gain and drive capability
    * Total DC gain: A_v = A_v1 × A_v2
    * Current source load vs resistor
  
  - Design equations:
    * Second stage gain: A_v2 = g_m6 × r_out2
    * Output impedance: r_out2 = r_o6 || r_o7
    * Slew rate: SR = I_SS / C_c (will learn about C_c tomorrow)
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:45: Design Second Stage
  - Add to first stage schematic:
    * M6: NMOS common-source amplifier
    * M7: PMOS current source load
  
  - Design steps:
    1. Choose bias current for second stage:
       - Remaining power budget: ~2.5mA - 0.2mA = 2.3mA
       - Choose conservatively: I_6 = 500µA
       - Leaves margin for bias circuits
    
    2. Size M6 (CS amplifier):
       - Need good g_m for gain
       - Also need drive capability for C_L
       - Choose W=40µm, L=1µm (can be shorter than input)
    
    3. Size M7 (PMOS current source):
       - I_D = 500µA
       - Long channel for high r_out: L=2µm
       - Calculate W for proper current
    
    4. Connect stages:
       - Output of diff pair → Gate of M6
       - Need DC coupling
  
  - Simulation (without compensation yet):
    * Total DC gain: A_v1 × A_v2
    * Target: >60dB (typically 70-80dB achievable)
    * Measure at low frequency (1Hz)
  
  - AC analysis:
    * Will see TWO poles (one from each stage)
    * Phase will cross -180° (unstable!)
    * This is expected, we'll fix tomorrow with compensation

☐ 8:45-9:00: Analysis
  - Document two-pole problem:
    * First pole: f_p1 ≈ 1/(2π×r_out1×C_gs6)
    * Second pole: f_p2 ≈ 1/(2π×r_out2×C_L)
    * If both low frequency → phase issues
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: "Second Stage Design"
☐ Bode plot showing unstable response
☐ Note: "Stability problem to solve tomorrow"
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 28 - Thursday, February 27, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Reading - CRITICAL TOPIC
  - Book: Razavi "Design of Analog CMOS IC" Ch 9.5
  - Pages: 375-405 (Frequency Compensation - Miller)
  - Key concepts:
    * Why two-pole system is unstable
    * Pole-splitting technique
    * Miller compensation capacitor C_c
    * Nulling resistor R_z
    * Right-half-plane (RHP) zero problem
  
  - Understand pole-splitting:
    * C_c creates feedback from output to internal node
    * First pole moves DOWN in frequency (becomes dominant)
    * Second pole moves UP in frequency
    * Creates stable single-pole response
  
  - Design equations:
    * C_c ≈ g_m6 / (2π × GBW)
    * GBW ≈ g_m1 / (2π × C_c)
    * R_z = 1/g_m6 (to cancel RHP zero)
    * Phase margin: PM = 90° - tan⁻¹(GBW/f_p2)
  
  - Hand-calculate C_c for your design:
    * Target GBW = 10MHz
    * g_m1 ≈ 1mS (from first stage)
    * C_c = g_m1 / (2π × GBW) = 1mS / (2π × 10MHz)
    * C_c ≈ 16pF (starting point)
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:45: Miller Compensation Implementation
  - Add to op-amp schematic:
    * C_c: Miller cap from output to internal node (drain of M6)
    * R_z: Nulling resistor in series with C_c
  
  - Compensation process:
    1. Start with calculated C_c = 16pF
    2. Add R_z = 1/g_m6
    3. Run AC analysis
    4. Check:
       * Phase margin at unity gain frequency
       * Target: PM > 60°
    
    5. If PM too low: Increase C_c
    6. If PM too high: Decrease C_c (more bandwidth)
    7. Iterate to optimize
  
  - Measurements:
    * Unity-gain frequency (where gain = 0dB)
    * Phase at unity-gain frequency
    * Phase margin = 180° + phase
    * Verify: No RHP zero (phase doesn't dip below PM)
  
  - Optimization:
    | C_c | GBW | Phase Margin | Slew Rate | Optimum? |
    |-----|-----|--------------|-----------|----------|
    | 12pF | __MHz | __° | __V/µs | - |
    | 16pF | __MHz | __° | __V/µs | - |
    | 20pF | __MHz | __° | __V/µs | - |
  
  - Choose value with best PM while meeting GBW target

☐ 8:45-9:00: Verification
  - Complete AC analysis:
    * Bode plot: Gain and Phase
    * Verify single dominant pole
    * Check phase margin >60°
  - Save compensated vs uncompensated comparison
```

**Documentation (9:00-9:30 PM)**
```
☐ Lab journal: "Frequency Compensation"
☐ Before/after Bode plots (huge improvement!)
☐ Key insight: "Miller cap creates single-pole response"
☐ C_c optimization table
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 29 - Friday, February 28, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**
```
☐ 6:00-7:30: Complete Design Review
  - Review entire op-amp design
  - Check each stage:
    * Input diff pair: ✓ High CMRR, good gain
    * Second stage: ✓ Additional gain, drive capability
    * Compensation: ✓ Stable, adequate phase margin
  
  - Solve problems:
    * Razavi Ch 9: Problems 9.1, 9.3, 9.5, 9.7
    * Focus on op-amp design from specs
```

**Evening Session (7:00-9:00 PM) - 2 hours**
```
☐ 7:00-8:45: Complete Characterization
  - Full performance verification:
    
    1. DC Gain:
       * .ac dec 100 0.1 1G
       * Measure at 1Hz
       * Target: >60dB
    
    2. Unity-Gain Bandwidth:
       * Find frequency where gain = 0dB
       * Target: >10MHz
    
    3. Phase Margin:
       * Phase at unity-gain frequency
       * Target: >60°
    
    4. Slew Rate:
       * .tran with large step input (1V step)
       * Measure: dV/dt on rising/falling edges
       * SR = I_SS / C_c (verify formula)
       * Target: >5V/µs
    
    5. Settling Time:
       * Apply step input
       * Measure time to settle within 1% of final value
    
    6. CMRR:
       * Differential-mode gain vs common-mode gain
       * Target: >70dB
    
    7. PSRR (Power Supply Rejection Ratio):
       * Gain from V_DD variation to output
       * AC analysis with supply as input
       * Target: >60dB
    
    8. Output Swing:
       * Maximum/minimum output voltage
       * Ideally close to V_DD and GND
    
    9. Offset Voltage:
       * Ideally 0V, practically <10mV
       * Due to mismatch in practice
  
  - Create comprehensive results table:
    | Specification | Target | Achieved | Pass? |
    |---------------|--------|----------|-------|
    | DC Gain | >60dB | __dB | ☐ |
    | GBW | >10MHz | __MHz | ☐ |
    | Phase Margin | >60° | __° | ☐ |
    | Slew Rate | >5V/µs | __V/µs | ☐ |
    | Power | <5mW | __mW | ☐ |
    | CMRR | >70dB | __dB | ☐ |
    | PSRR | >60dB | __dB | ☐ |
    | Settling | <500ns | __ns | ☐ |
  
☐ 8:45-9:00: Iteration if Needed
  - If any spec fails:
    * Identify bottleneck
    * Adjust design
    * Re-simulate
    * Document change
```

**Documentation (9:00-9:30 PM)**
```
☐ Complete op-amp characterization report
☐ All performance plots
☐ This is major portfolio piece #3
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 30 - Saturday, March 1, 2026**

**Major Project Day (9:00 AM - 6:00 PM) - 8 hours**
```
☐ 9:00-12:00: Op-Amp Optimization
  - Now that basic design works, optimize:
    
    1. Power vs Performance:
       * Reduce I_SS, see effect on slew rate and GBW
       * Find minimum power while meeting specs
    
    2. Area Optimization:
       * Can any transistors be smaller?
       * C_c value affects area significantly
    
    3. Noise Analysis (NEW):
       * Read: Razavi Ch 9.6 (Noise in Op-Amps)
       * Run noise simulation in LTspice
       * Input-referred noise measurement
       * Identify dominant noise sources
    
    4. Monte Carlo Analysis:
       * 50-100 runs with device mismatch
       * Measure:
         - Offset voltage distribution
         - Gain variation
         - GBW variation
       * Calculate yield: % meeting all specs
  
  - Document optimization trade-offs

☐ 12:00-1:00: Lunch

☐ 1:00-3:00: Create Complete Design Package
  - Professional documentation:
    
    1. Cover page with specs
    2. Architecture overview
    3. Design procedure:
       * First stage sizing
       * Second stage sizing
       * Compensation design
    4. Simulation results with plots
    5. Performance summary table
    6. Design insights and learnings
    7. Future improvements possible
  
  - Export as PDF: "Two-Stage Op-Amp Design Report"
  - This is portfolio showpiece

☐ 3:00-4:00: Cadence Implementation (if available)
  - Rebuild op-amp in Cadence Virtuoso:
    * Create schematic
    * Use PDK transistors
    * Set up testbenches
    * Run same characterization
    * Compare to LTspice results
  
  - If no Cadence:
    * Advanced LTspice features:
      - Create subcircuit for op-amp
      - Build macro-models
      - Behavioral modeling introduction

☐ 4:00-6:00: Video Content - Major Production
  - Edit comprehensive video: "I Designed an Op-Amp from Scratch"
  
  - Video structure (Target: 15-20 min):
    1. Intro (0:00-1:00):
       * What is an op-amp?
       * Why this project matters
       * What you'll learn from video
    
    2. Specifications (1:00-2:00):
       * Design targets explained
       * Why these specs chosen
    
    3. First Stage Design (2:00-6:00):
       * Differential pair with active load
       * Hand calculations shown
       * Simulation verification
       * CMRR optimization
    
    4. Second Stage Design (6:00-9:00):
       * Common-source stage
       * Two-pole problem explained
    
    5. Frequency Compensation (9:00-14:00):
       * The stability problem
       * Miller compensation solution
       * Pole-splitting visualization
       * Phase margin optimization
    
    6. Results (14:00-17:00):
       * Full characterization
       * All specs verified
       * Step response demo
    
    7. Challenges & Learnings (17:00-19:00):
       * What went wrong initially
       * How I debugged
       * Key insights
    
    8. Outro (19:00-20:00):
       * Summary
       * Next steps in journey
       * Links to GitHub and resources
  
  - Include:
    * Screen recordings of simulation
    * Annotated schematics
    * Bode plots with voiceover explanation
    * Before/after compensation comparison
    * Final performance summary
  
  - Export: week05-06_opamp_design.mp4
```

**Evening (6:00-8:00 PM)**
```
☐ 6:00-7:00: GitHub Major Update
  - Create dedicated repository folder:
    /projects/two-stage-opamp/
      README.md (detailed description)
      /schematics (all LTspice files)
      /results (plots, data)
      /documentation (design report PDF)
      /scripts (any automation)
  
  - Update main README:
    * Highlight op-amp as major milestone
    * Link to detailed project page
    * Include performance summary
  
  - Add project to portfolio website (if created)

☐ 7:00-8:00: Community Engagement
  - Major Reddit post in r/chipdesign:
    "I designed a complete two-stage op-amp (beginner journey update)"
    
    Include:
    * Before/after compensation Bode plots
    * Performance summary table
    * Link to GitHub with full documentation
    * Link to YouTube video
  
  - Twitter thread (10-12 tweets):
    1/ "Just finished designing my first complete op-amp! 🎉
       Thread on what I learned about frequency compensation..."
    
    2/ "The challenge: Two-stage amplifier = two poles = unstable
       [Image: Unstable Bode plot]"
    
    3/ "The solution: Miller compensation
       One capacitor changes everything
       [Image: Compensated Bode plot]"
    
    [Continue thread with key insights...]
    
    Final tweet: "Full design on GitHub: [link]
    Video walkthrough: [link]
    #AnalogDesign #ICDesign"
```

**Total Time Today:** 8 hours

---
