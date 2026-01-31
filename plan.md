# Analog IC Design Roadmap: From Basics to Market-Ready

## **Phase 1: Foundation Strengthening (2-3 months)**

### Core Knowledge
**Books:**
- *Razavi's "Fundamentals of Microelectronics"* (2nd ed) - Your main companion, read chapters 1-10
- *Sedra/Smith "Microelectronic Circuits"* (7th ed) - Reference for deeper dives

**Video Resources:**
- Razavi's own YouTube lectures (UC Berkeley EE105)
- Ali Hajimiri's Caltech lectures on analog circuits
- Jordan Edmunds' YouTube channel (excellent practical explanations)

**Labs/Simulation:**
- Install LTSpice (free) - Learn basic circuit simulation
- Practice: Single-stage amplifiers, current mirrors, differential pairs
- **Critical**: Build intuition by tweaking parameters and observing behavior

### YouTube Video Ideas (Phase 1):
1. *"I simulated 100 MOSFETs to finally understand gm"* - Show how transconductance changes with bias, size, load
2. *"Building intuition: Why differential pairs reject noise (animated)"* - Visual explanations beat equations
3. *"Common mistakes in current mirror design (and how to fix them)"* - Debug real simulation failures

---

## **Phase 2: Advanced Circuit Techniques (3-4 months)**

### Deep Dive
**Books:**
- *Gray/Meyer "Analysis and Design of Analog Integrated Circuits"* (5th ed) - Industry standard
- *Razavi's "Design of Analog CMOS Integrated Circuits"* (2nd ed) - Essential, read cover to cover

**Video Resources:**
- Boris Murmann's Stanford lectures (available online)
- ISSCC/VLSI Symposium tutorial videos (check IEEE Xplore if you have access)

**Labs:**
- Design multi-stage op-amps in LTSpice
- Frequency compensation techniques
- Layout basics in Magic or Electric (open-source)
- **Join:** eFabless/Google's Open MPW shuttle program for free tape-outs

**Skills to Master:**
- Op-amp design (two-stage, folded cascode)
- Frequency response & stability
- Noise analysis (thermal, flicker, shot)
- Mismatch and offset considerations

### YouTube Video Ideas (Phase 2):
4. *"I designed an op-amp from scratch (complete process)"* - Show entire workflow: specs → topology → sizing → simulation
5. *"Why your op-amp oscillates (and 5 ways to fix it)"* - Compensation techniques with Bode plots
6. *"Layout parasitics destroyed my circuit (layout vs schematic)"* - Show how real layout changes performance

---

## **Phase 3: Specialized Blocks & Industry Skills (3-4 months)**

### Advanced Topics
**Books:**
- *Razavi's "RF Microelectronics"* (2nd ed) - If interested in RF
- *Johns/Martin "Analog Integrated Circuit Design"* - Excellent for data converters
- *Baker's "CMOS Circuit Design, Layout, and Simulation"* - Layout-focused

**Focus Areas (pick 2-3):**
- **Data Converters:** ADCs (SAR, pipeline, delta-sigma), DACs
- **PLLs/Frequency Synthesis:** Phase-locked loops, VCOs
- **Power Management:** LDOs, bandgap references, DC-DC converters
- **High-Speed Circuits:** TIAs, CDRs for SerDes

**Tools to Learn:**
- Cadence Virtuoso (industry standard) - Try to get academic access or online courses
- Mentor/Siemens Pyxis or Synopsys Custom Compiler
- Post-layout simulation with parasitic extraction

**Labs:**
- Design a complete ADC or PLL
- Do full layout with DRC/LVS checks
- Learn about process corners, Monte Carlo, PVT variations

### YouTube Video Ideas (Phase 3):
7. *"I built a 10-bit ADC: Architecture decisions explained"* - SAR vs pipeline vs delta-sigma comparison
8. *"Race condition debugging in my PLL design"* - Show real timing issues
9. *"Process corners ruined my specs (corner analysis deep-dive)"* - FF vs SS vs FS corners

---

## **Phase 4: Market Readiness (2-3 months)**

### Industry Preparation
**Practical Experience:**
- **Open-source:** Contribute to SkyWater PDK designs, OpenRAM, or other open-source analog projects
- **Tape-out:** Participate in Efabless/ChipIgnite shuttles (free silicon!)
- **Build portfolio:** 3-5 complete designs with documentation

**Interview Prep:**
- Solve analog design problems on paper (common in interviews)
- Know trade-offs cold: speed vs power, noise vs area, etc.
- Study job descriptions to identify key skills employers want

**Resources:**
- IEEE Solid-State Circuits Magazine (easier than JSSC papers)
- Attend virtual ISSCC, VLSI, CICC conferences (student rates)
- Join Analog IC Design communities on LinkedIn, Reddit (r/chipdesign)

### Final YouTube Video Series:
10. *"Designing for manufacturing: My first tape-out"* - Document the entire process
11. *"5 analog IC projects for your portfolio (with specs)"* - Guide others
12. *"I got an analog IC design job: Interview questions & what actually mattered"*

---

## **Competition/Community Platforms**

### Hackathons & Challenges:
- **Efabless Open MPW Shuttle** - Design, submit, get fabricated (FREE)
- **DAC System Design Contest** - Annual competition for data converters
- **ISSCC Student Research Preview** - Showcase your work
- **IEEE Analog Signal Processing Technical Committee contests**

### No "Kaggle for Analog" Yet, But:
- **ChipIgnite** (Efabless platform) - Closest thing, community designs
- **Open-source PDK projects** - Contribute to real designs (SkyWater 130nm, GlobalFoundries)
- **Start a blog/GitHub** - Document designs, share Spice netlists

---

## **Compact 12-Month Learning Plan**

| Timeline | Focus | Deliverable | Video Topic |
|----------|-------|-------------|-------------|
| Month 1-2 | Transistor fundamentals, basic circuits | 5 simulated circuits | Video #1-2 |
| Month 3 | Differential pairs, current mirrors | Simple diff-amp | Video #3 |
| Month 4-5 | Op-amp design, frequency response | Two-stage op-amp | Video #4-5 |
| Month 6-7 | Layout basics, parasitics | Layout-verified op-amp | Video #6 |
| Month 8-9 | Specialized block (ADC/PLL/LDO) | Complete design + layout | Video #7-8 |
| Month 10 | Corners, Monte Carlo, PVT | Robust design | Video #9 |
| Month 11 | Tape-out preparation | Submit to MPW shuttle | Video #10 |
| Month 12 | Portfolio, interviews | Job applications | Video #11-12 |

---

## **YouTube Strategy for Maximum Impact**

### What Made That AI YouTuber Successful:
- **Incremental complexity** - Each video builds on the last
- **Show the struggle** - Debugging failures is more engaging than perfect results
- **Teach fundamentals through projects** - Don't just lecture

### Your Analog IC Approach:
1. **Series structure:** "30 Days of Analog Design" or "Beginner to Tape-out"
2. **Show simulations live** - Waveforms, debugging, parameter sweeps
3. **Explain trade-offs visually** - Power vs speed curves, noise plots
4. **Include mistakes** - "This is why my circuit didn't work"
5. **End with challenges** - Ask viewers to modify your design

### Video Format Template:
- **Hook (0-15s):** "I spent 40 hours designing this op-amp and it oscillated"
- **Context (15-60s):** What you're building and why
- **Process (bulk):** Show the design, explain decisions, debug issues
- **Results:** Simulation results, what you learned
- **Challenge:** "Can you improve the bandwidth by 20%?"

---

## **Key Success Metrics**

After 12 months, you should be able to:
- ✅ Design common analog blocks from specs (op-amp, ADC, PLL, LDO)
- ✅ Perform complete layout with DRC/LVS clean
- ✅ Analyze circuits for noise, matching, PVT corners
- ✅ Have 1 tape-out submission (via free shuttles)
- ✅ Portfolio of 3-5 documented designs
- ✅ 12+ YouTube videos showing your journey
- ✅ Ready for entry-level analog IC design positions

**Start today:** Install LTSpice, download Razavi's book, and simulate your first differential pair. Document it. That's your first video.


-----------------------------------------------------


# Daily Analog IC Design Plan + Documentation Strategy

## **Daily Schedule Structure**

### **Weekday Schedule (3-4 hours/day)**

#### **Morning Block (1.5-2 hours) - Deep Learning**
- **6:00-6:15 AM:** Review previous day's notes
- **6:15-7:30 AM:** Theory study (books/lectures)
  - Read 5-10 pages from main textbook
  - Watch 1 lecture segment (20-30 min)
  - Take handwritten notes with key equations
- **7:30-8:00 AM:** Concept mapping
  - Create visual diagrams of what you learned
  - Connect to previous concepts

#### **Evening Block (1.5-2 hours) - Hands-on Practice**
- **7:00-8:30 PM:** Lab/Simulation work
  - Implement concept from morning in LTSpice/Cadence
  - Follow structured exercises (see below)
  - Debug and document results
- **8:30-9:00 PM:** Daily documentation
  - Update design journal (template below)
  - Screenshot key simulations
  - Note problems encountered + solutions

### **Weekend Schedule (6-8 hours/day)**

#### **Saturday - Project Day**
- **9:00-12:00 PM:** Major design work
  - Work on monthly project deliverable
  - Full circuit design iterations
- **12:00-1:00 PM:** Break
- **1:00-4:00 PM:** Continue design + layout
- **4:00-6:00 PM:** Video content creation
  - Record screen captures
  - Draft script for weekly video

#### **Sunday - Review & Community**
- **9:00-11:00 AM:** Weekly review
  - Summarize week's learning
  - Update portfolio documentation
  - Prepare next week's plan
- **11:00-1:00 PM:** Content creation
  - Edit video footage
  - Create thumbnails/titles
- **2:00-4:00 PM:** Community engagement
  - Post on LinkedIn/GitHub
  - Read papers/industry articles
  - Participate in forums
- **4:00-5:00 PM:** Interview prep
  - Practice 5 analog design questions
  - Review common interview concepts

---

## **Monthly Milestone Structure**

### **Month 1-3: Foundations**
**Week 1:** MOS transistor operation, small-signal models
**Week 2:** Single-stage amplifiers (CS, CG, CD)
**Week 3:** Current mirrors and biasing
**Week 4:** Differential pairs

**Monthly Deliverable:** Complete simulation library of basic building blocks

### **Month 4-6: Complex Circuits**
**Week 1-2:** Two-stage op-amp design
**Week 3:** Frequency compensation
**Week 4:** Noise and offset analysis

**Monthly Deliverable:** Fully characterized op-amp with datasheet

### **Month 7-9: Specialization**
**Week 1-2:** Choose specialized block (ADC/PLL/LDO)
**Week 3-4:** Design and simulate
**Week 5-6:** Layout basics
**Week 7-8:** Layout of your specialized block

**Monthly Deliverable:** Complete design with layout (DRC/LVS clean)

### **Month 10-12: Market Readiness**
**Week 1-2:** Tape-out preparation
**Week 3-4:** Portfolio documentation
**Week 5-6:** Interview preparation
**Week 7-8:** Job applications + portfolio refinement

**Monthly Deliverable:** Tape-out submission + complete portfolio

---

## **Documentation System for Maximum Hirability**

### **1. GitHub Repository Structure**

```
analog-ic-journey/
├── README.md (Your story + quick links)
├── projects/
│   ├── 01-differential-amp/
│   │   ├── README.md (specs, design choices, results)
│   │   ├── schematics/
│   │   ├── simulations/
│   │   ├── layout/
│   │   └── documentation/
│   │       ├── design-report.pdf
│   │       ├── test-results.pdf
│   │       └── lessons-learned.md
│   ├── 02-opamp-two-stage/
│   ├── 03-sar-adc/
│   └── 04-pll/
├── learning-notes/
│   ├── week-01-mosfet-basics.md
│   ├── week-02-amplifiers.md
│   └── ...
├── simulations/
│   ├── ltspice-models/
│   └── cadence-testbenches/
└── resources/
    ├── useful-papers.md
    └── tool-tutorials.md
```

### **2. Project Documentation Template**

For each major design, create this structure:

#### **README.md for Each Project:**
```markdown
# [Project Name] - [Month/Year]

## Overview
One-paragraph description of what you built and why

## Specifications
| Parameter | Target | Achieved | Unit |
|-----------|--------|----------|------|
| Gain | >60 | 64.3 | dB |
| Bandwidth | >10 | 12.4 | MHz |
| Power | <5 | 3.8 | mW |

## Design Approach
- Topology selection rationale
- Key design equations used
- Trade-offs considered

## Schematic
[Insert annotated schematic image]

## Simulation Results
[Bode plots, transient responses, Monte Carlo]

## Layout
[Layout screenshot with annotations]

## Challenges & Solutions
1. **Problem:** Op-amp oscillated at high frequencies
   **Solution:** Added Miller compensation with...
   **Learning:** Always check phase margin >60°

## Files
- Schematic: `schematic.sch`
- Netlist: `netlist.sp`
- Layout: `layout.gds`
- Test results: `results.pdf`

## Video
[Link to YouTube video explaining this design]
```

### **3. Weekly Design Journal**

Keep a **Notion** or **Google Docs** journal:

#### **Daily Entry Template:**
```
Date: [Date]
Time Spent: [Hours]

📚 Theory Studied:
- Sections read: Razavi Ch 3.4-3.6
- Key concept: Cascode current mirrors improve output impedance
- Equation learned: rout = gm*ro²

🔬 Lab Work:
- Designed: 3 cascode current mirror variants
- Simulated: Output impedance vs current
- Results: Achieved 10MΩ output impedance

❌ Problems Encountered:
- Issue: Current mirror mismatch caused 5% error
- Debug steps: Checked W/L ratios, increased L
- Solution: Increased length from 0.5µm to 2µm

✅ Wins:
- Successfully matched current to within 1%
- Understood length impact on matching

🎯 Tomorrow's Plan:
- Apply cascode mirrors to op-amp input stage
- Study noise in current mirrors
```

### **4. LinkedIn Portfolio Posts**

**Post weekly micro-updates** (these are gold for recruiters):

**Template:**
```
Week [X] of my analog IC design journey ⚡

This week I designed [specific circuit]:
📊 Key specs achieved: [metric]
🎓 Major learning: [insight]
🐛 Biggest challenge: [problem + solution]

The most surprising thing: [unexpected insight]

Next week: [what's coming]

#AnalogDesign #ICDesign #VLSI #Engineering

[Include: Circuit diagram or simulation plot]
```

**Why this works:**
- Shows consistent progress
- Demonstrates problem-solving
- Proves technical depth
- Builds your personal brand
- Recruiters search these hashtags

### **5. Portfolio Website**

Create a **simple website** (use GitHub Pages, free):

**Homepage sections:**
1. **Hero:** "Analog IC Designer | 12 Months to Tape-out"
2. **About:** Your journey, background, motivation
3. **Projects Grid:** 
   - Thumbnail images
   - Project name
   - Key specs
   - Tech used
   - Link to detailed page
4. **Skills Matrix:**
   - Tools: LTSpice ⭐⭐⭐⭐⭐, Cadence ⭐⭐⭐⭐, Layout ⭐⭐⭐⭐
   - Circuits: Op-amps ⭐⭐⭐⭐⭐, ADCs ⭐⭐⭐⭐, PLLs ⭐⭐⭐
5. **Learning Journey:** Timeline visualization
6. **Blog:** Weekly learnings
7. **Videos:** Embedded YouTube
8. **Contact**

**Tools to build it:**
- GitHub Pages (free hosting)
- Jekyll or Hugo (static site generators)
- Carrd.co (super simple, drag-and-drop)

### **6. YouTube Channel Strategy**

**Channel Structure:**

**Playlists:**
1. "Analog IC Basics" (Month 1-3 videos)
2. "Op-amp Design Series" (Month 4-6)
3. "Advanced Circuits" (Month 7-9)
4. "Tape-out Journey" (Month 10-12)
5. "Weekly Progress Logs" (short updates)

**Video Types:**

**A) Tutorial Videos (15-25 min):**
- Deep dive into specific concept
- Show simulation process
- Explain trade-offs
- Give homework problem

**B) Progress Vlogs (5-10 min):**
- Weekly update format
- Show what you built
- Share struggles
- Quick tips

**C) Project Showcases (20-30 min):**
- Complete design walkthrough
- Design decisions explained
- Results and analysis
- Post-mortem

**Thumbnail Formula:**
- Circuit diagram background (blurred)
- Your face (if comfortable) or key waveform
- Bold text: "I Built a [X]" or "Why [Y] Happens"
- Yellow/Orange accent colors (high CTR)

### **7. Resume/CV Optimization**

**Projects Section (Most Important):**

```
ANALOG IC DESIGN PROJECTS

Two-Stage Op-Amp (Fully Differential) | LTSpice, Cadence Virtuoso
• Achieved 80dB gain, 15MHz GBW, 65° phase margin in 180nm process
• Designed folded-cascode input stage for high CMRR (>90dB)
• Performed Monte Carlo analysis (100 runs) to ensure <5mV offset variation
• Complete layout with DRC/LVS clean (450µm x 350µm area)
[GitHub] [Video] [Report]

10-bit SAR ADC | Cadence, Python (for INL/DNL analysis)
• Designed capacitive DAC, comparator, and SAR logic for 1MSPS
• Achieved INL <0.5 LSB, DNL <0.3 LSB, ENOB = 9.4 bits
• Optimized comparator for <10mV offset through careful layout matching
• Verified functionality across PVT corners (FF, TT, SS)
[GitHub] [Video] [Paper]
```

**Skills Section:**
```
Tools: Cadence Virtuoso, LTSpice, Magic, Ngspice, Python (circuit analysis)
Circuits: Op-amps, ADCs (SAR, Pipeline), PLLs, Current mirrors, Bandgap references
Analysis: AC/Transient/Noise simulation, Monte Carlo, Corner analysis, Stability
Layout: Analog layout techniques, Matching, Shielding, DRC/LVS verification
```

**Add at top:**
```
Portfolio: github.com/yourname/analog-ic-journey
Website: yourname.github.io
YouTube: youtube.com/@yourname (500+ subscribers, 15K+ views)
```

---

## **Interview Preparation System**

### **Daily Interview Prep (Last 15 min of day)**

**Monday:** Fundamental questions
- "Explain how a MOSFET works"
- "Draw small-signal model of common-source amp"

**Tuesday:** Design questions
- "Design a current mirror with 100µA output"
- "How do you improve op-amp PSRR?"

**Wednesday:** Troubleshooting
- "Your op-amp oscillates, what do you check?"
- "How do you debug offset issues?"

**Thursday:** Trade-off questions
- "Speed vs power in an ADC?"
- "Increasing W/L ratio: pros and cons?"

**Friday:** Your projects
- Practice explaining your designs in 2 minutes
- Prepare for "Tell me about your op-amp design"

### **Weekly Mock Interview (Sunday)**

**Set up a spreadsheet:**
| Date | Question | Your Answer | Key Points Missed | Rating |
|------|----------|-------------|-------------------|---------|
| Week 1 | Design current source | [record yourself] | Didn't mention headroom | 6/10 |

**Improve weekly based on gaps**

---

## **Tracking Progress: The Dashboard**

**Create a Notion dashboard with:**

### **1. Learning Tracker**
- Total hours logged: [X/1000]
- Books completed: [X/5]
- Circuits designed: [X/20]
- Videos published: [X/12]

### **2. Skill Matrix**
Rate yourself weekly (1-5):
| Skill | Month 1 | Month 3 | Month 6 | Month 9 | Month 12 |
|-------|---------|---------|---------|---------|----------|
| MOSFET theory | 2 | 4 | 5 | 5 | 5 |
| Op-amp design | 1 | 2 | 4 | 5 | 5 |
| Layout | 1 | 1 | 3 | 4 | 5 |

### **3. Project Status Board**
- Project 1: ✅ Complete
- Project 2: 🟡 Layout phase
- Project 3: ⚪ Planning
- Tape-out: 🟡 Design review

### **4. Job Application Tracker**
| Company | Date Applied | Status | Follow-up | Notes |
|---------|--------------|--------|-----------|-------|

---

## **What Makes You Hire-able: The Checklist**

After 12 months, you should have:

### **Technical Evidence:**
- ✅ 5+ complete designs with specs/schematics/layouts
- ✅ 1 tape-out submission (even if not fabricated yet)
- ✅ GitHub with organized, documented projects
- ✅ Can explain every design decision in your projects
- ✅ Know trade-offs for common circuit topologies

### **Online Presence:**
- ✅ LinkedIn with weekly posts (50+ posts total)
- ✅ YouTube channel (12+ videos, showing growth)
- ✅ Portfolio website (professional, mobile-friendly)
- ✅ Active in analog design communities
- ✅ 200+ connections with IC designers on LinkedIn

### **Soft Skills Evidence:**
- ✅ Document debugging process (shows problem-solving)
- ✅ Show iteration (Version 1 → Version 2 improvements)
- ✅ Explain clearly in videos (communication skills)
- ✅ Consistent posting (reliability, discipline)
- ✅ Accept feedback (comments on videos/posts)

### **The "Proof of Work":**
When HR/interviewers Google your name, they find:
1. Your portfolio website (first result)
2. Your LinkedIn with clear progress
3. Your GitHub with real code
4. Your YouTube showing you actually know this stuff
5. Evidence you can finish projects (tape-out)

---

## **First Week Action Plan (Start TODAY)**

### **Day 1 (Today):**
- [ ] Install LTSpice
- [ ] Create GitHub account + first repository
- [ ] Set up daily journal (Notion/Docs)
- [ ] Read Razavi Chapter 1 (15 pages)
- [ ] Simulate your first MOSFET I-V curve
- [ ] Document it with screenshots
- [ ] Post on LinkedIn: "Day 1 of my analog IC journey"

### **Day 2:**
- [ ] Read Razavi Ch 2.1-2.3
- [ ] Watch Razavi's lecture on MOSFET operation
- [ ] Simulate MOSFET in different regions (linear, sat, subthreshold)
- [ ] Take notes on gm, ro equations
- [ ] Update journal

### **Day 3:**
- [ ] Read Razavi Ch 2.4-2.6
- [ ] Design common-source amplifier
- [ ] Vary load resistor, measure gain
- [ ] Plot gain vs load resistance
- [ ] Document results

### **Day 4:**
- [ ] Review week's concepts (2 hours deep review)
- [ ] Create visual concept map
- [ ] Start planning Week 1 video
- [ ] Record screen capture of simulations

### **Day 5:**
- [ ] Read Razavi Ch 3.1-3.2 (current mirrors)
- [ ] Design simple current mirror
- [ ] Test matching with Monte Carlo
- [ ] Document mismatch results

### **Weekend:**
- Saturday: Edit first video, finish Week 1 project
- Sunday: Publish video, write LinkedIn post, plan Week 2

---

## **The Competitive Edge: What Separates You**

**Most candidates have:** Degree, decent GPA, some projects

**You will have:**
1. **Public learning journey** - Shows growth mindset
2. **Video proof** - Can't fake understanding on camera
3. **Consistent output** - 12 months of weekly content
4. **Real silicon submission** - Tape-out experience
5. **Community presence** - Known quantity in the field

**When an interviewer asks "Tell me about yourself":**

*"I spent the last 12 months intensively learning analog IC design. I documented everything on my GitHub and YouTube channel. I've designed 5 major circuits including a two-stage op-amp and SAR ADC, completed layouts for all of them, and submitted a design for tape-out through Efabless. Here's my portfolio website where you can see everything. Which project would you like me to walk you through?"*

**This is instantly more compelling than:** *"I took some courses and did a senior project."*

---

## **Final Tips**

1. **Consistency beats intensity** - 2 hours daily > 14 hours on Sunday
2. **Document EVERYTHING** - Your memory is unreliable
3. **Show the struggle** - Failures make better stories than perfection
4. **Engage with community** - Comment on others' work, they'll remember
5. **Quality > quantity** - One great project > three mediocre ones
6. **Make it searchable** - Use keywords, hashtags, clear titles
7. **Update weekly** - Momentum is visible and attractive to employers

**Start today. Document today. Ship today.**

Your Day 1 post tonight: "Starting my journey to become an analog IC designer. Today I simulated my first MOSFET. Here's what I learned... [screenshot]"

That's it. You're now ahead of 99% of people who "plan to start."