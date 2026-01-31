# 6-Month Analog IC Design Roadmap - Daily Tasks (Days 31-51)

**Month 2 Continuation: March 2 - March 31, 2026**

---

## **Week 6: Paper Recreation & Layout Introduction**

#### **Day 31 - Sunday, March 2, 2026**

**Review & Planning Day (9:00 AM - 5:00 PM) - 8 hours**

```
☐ 9:00-10:00: Week 5 Final Review
  - Complete Week 5 summary document
  - Op-amp design milestone achieved ✓
  - Self-quiz:
    * Design op-amp from specs (no notes)
    * Explain Miller compensation
    * Calculate phase margin

☐ 10:00-11:30: Video Publishing
  - Upload op-amp video to YouTube
  - Title: "I Designed an Op-Amp from Scratch - Complete Process"
  - Description:
    "In this video, I walk through the complete design of a two-stage 
    CMOS op-amp from specifications to final characterization. 
    
    Topics covered:
    • Input differential pair design
    • Second stage common-source amplifier
    • Frequency compensation (Miller)
    • Stability analysis and phase margin
    • Complete performance verification
    
    Resources:
    GitHub: [link to detailed design files]
    Design Report: [link to PDF]
    
    Timestamps:
    0:00 - Introduction
    1:00 - Specifications
    2:00 - First Stage Design
    6:00 - Second Stage Design
    9:00 - Frequency Compensation
    14:00 - Results & Performance
    17:00 - Challenges & Learnings
    
    #AnalogICDesign #OpAmp #CMOSDesign #FrequencyCompensation"
  
  - Tags: op-amp, analog design, CMOS, frequency compensation
  - Custom thumbnail with op-amp schematic and "From Scratch" text

☐ 11:30-12:30: Lunch

☐ 12:30-2:00: Community Engagement
  - Reddit: Update post in r/chipdesign
  - Twitter: Thread on op-amp completion
  - Engage with comments from previous posts

☐ 2:00-3:30: Paper Selection for Recreation
  - Task: Choose paper to recreate in Week 6
  - Review saved papers from Month 1
  
  - Target Paper: "A Micropower Low-Noise Amplifier for Neural Recording"
    * Authors: R. R. Harrison, C. Charles
    * Venue: IEEE JSSC, Jan 2003, Vol. 38, No. 6, pp. 958-965
    * Why chosen:
      - Well-documented with component values
      - Manageable complexity for learning
      - Clear design methodology
      - Good for portfolio (bio-medical application)
  
  - Download paper from IEEE Xplore
  - Complete Pass 1 reading (10-minute survey):
    * Abstract: Low-power, low-noise amp for neural signals
    * Figures: Check for schematic details
    * Conclusion: 40 nV/√Hz noise, 7 µW power
    * Decision: ✓ Good candidate for recreation
  
  - Create paper recreation project folder:
    * Title: "Harrison Neural Amplifier Recreation"
    * Status: Planning
    * Target: Complete by Day 37 (Saturday)

☐ 3:30-5:00: Week 6 Detailed Planning
  - Overview: Paper recreation + Layout introduction
  
  - Daily breakdown:
    * Mon-Tue: Paper deep reading, extract all values
    * Wed-Thu: Build circuit blocks, test individually
    * Fri: Integrate and initial testing
    * Sat: Complete characterization and comparison
    * Sun: Layout introduction (Magic VLSI)
  
  - Prepare tools:
    * Verify LTspice ready
    * Download Magic VLSI if not done
    * Bookmark Magic tutorials
  
  - Set Week 6 goals:
    ☐ Complete paper recreation (>80% match)
    ☐ Document recreation process thoroughly
    ☐ Learn basic layout concepts
    ☐ Create first simple layout in Magic
    ☐ Publish video on paper recreation process
```

**Total Time Today:** 8 hours
**Week 5 Total:** 40 hours

---

#### **Day 32 - Monday, March 3, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Paper Deep Reading - Pass 2
  - Paper: "A Micropower Low-Noise Amplifier for Neural Recording"
  - Authors: Harrison & Charles, IEEE JSSC 2003
  
  - Section-by-section analysis:
    
    I. Introduction (Pages 1-2):
    * Problem: Neural signals are µV-level, need low-noise amp
    * Challenge: Battery-powered implants need µW power
    * Solution: Sub-threshold operation for low power
    * Application: Brain-machine interfaces
    
    II. Architecture (Pages 2-3, Figure 1):
    * Topology: OTA (operational transconductance amplifier)
    * Input: Differential pair
    * Load: Current mirror
    * Special: Operates in weak inversion (sub-threshold)
    * Output: Direct from diff pair (no second stage)
    
    Key Innovation:
    * Sub-threshold operation: V_GS < V_T
    * Benefits: Much higher g_m/I_D ratio
    * Trade-off: Slower, but OK for neural signals (< 10 kHz)
  
  - Take detailed Cornell notes:
    * Left column: Keywords (sub-threshold, g_m/I_D, noise)
    * Right column: Detailed explanations
    * Bottom: 3-sentence summary
  
  - Extract circuit topology:
    * Hand-draw schematic from Figure 2
    * Label all components
    * Note any values given in text
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:30: Information Extraction
  - Create detailed extraction document:
  
  ## Component Values Extraction
  
  ### Transistor Sizes (From text and figures):
  | Device | Width | Length | Type | Notes |
  |--------|-------|--------|------|-------|
  | M1, M2 | 2000 µm | 8 µm | NMOS | Input pair |
  | M3, M4 | 500 µm | 8 µm | PMOS | Current mirror load |
  | M5 | 200 µm | 8 µm | NMOS | Tail current |
  
  **Critical note:** "All transistors biased in weak inversion"
  
  ### Bias Conditions:
  - Supply voltage: V_DD = 2.8V (single supply)
  - Total power: 7 µW
  - Bias current: I_bias = 2.5 µA (calculated from power)
  - Input common-mode: V_CM = 1.4V (mid-rail)
  
  ### Process Technology:
  - Process: 1.5 µm CMOS (older process - good for learning)
  - V_TN ≈ 0.7V (typical for this process)
  - V_TP ≈ -0.9V
  - Sub-threshold slope: n ≈ 1.5 (given in paper)
  
  ### Performance Specifications:
  | Metric | Value | Unit |
  |--------|-------|------|
  | Input-referred noise | 40 | nV/√Hz |
  | Midband gain | 40.8 | dB |
  | Bandwidth | 7.2 | kHz |
  | Power | 7 | µW |
  | CMRR | > 60 | dB |
  | Input impedance | 100 | MΩ |
  
  ### Sub-Threshold Equations (From paper):
  In weak inversion region (V_GS < V_T):
  
  I_D = I_0(W/L)exp((V_GS - V_T)/(nV_T))
  
  where:
  - I_0 = process-dependent constant ≈ 1-10 nA
  - n = sub-threshold slope factor ≈ 1.5
  - V_T = thermal voltage = kT/q ≈ 26 mV at 300K
  
  Transconductance:
  g_m = I_D/(nV_T)  ← Much higher than strong inversion!
  
  Key advantage: g_m/I_D ratio is maximum in sub-threshold

☐ 8:30-9:00: Missing Information Assessment
  - Identify what's NOT explicitly given:
    * Exact V_GS values (need to calculate from I_D)
    * Load capacitance (assumed ~10 pF typical)
    * Exact bias circuit topology
    * Temperature coefficients
  
  - Strategy for missing info:
    * Use given I_D and W/L to back-calculate V_GS
    * Reference typical values for 1.5µm process
    * Focus on matching the final performance metrics
  
  - Document assumptions clearly:
    "Assumption 1: Load capacitance C_L = 10 pF (not specified)
     Rationale: Typical for neural recording front-ends
     Will verify by matching bandwidth"
```

**Documentation (9:00-9:30 PM)**

```
☐ Paper recreation notes updated:
  - Status: Information Extraction Complete ✓
  - Next phase: Block-level implementation

☐ Create checklist for recreation:
  ☐ Build input differential pair
  ☐ Test sub-threshold operation
  ☐ Add current mirror load
  ☐ Characterize noise performance
  ☐ Measure bandwidth and gain
  ☐ Compare to paper specs
  ☐ Document differences

☐ GitHub commit:
  - Folder: /projects/harrison-neural-amp/
  - Files: 
    * paper_notes.md (extraction document)
    * recreation_plan.md
    * component_values.csv
```

**Total Time Today:** 4 hours

---

#### **Day 33 - Tuesday, March 4, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-6:30: Sub-Threshold Operation Study
  - Read: Razavi "Design of Analog CMOS IC" Ch 2.2.4
  - Topic: Weak inversion / sub-threshold region
  - Understand:
    * When transistor operates sub-threshold (V_GS < V_T)
    * Exponential I-V relationship (not square-law)
    * Why g_m/I_D is maximum here
    * Application: Ultra-low-power designs

☐ 6:30-7:30: Watch Supplementary Video
  - YouTube: Search "sub-threshold MOSFET operation"
  - Recommended: Hesam Sadeghi Gougheri's videos on sub-threshold
  - Take notes on:
    * How to bias transistor in sub-threshold
    * Practical considerations
    * Noise characteristics in weak inversion
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:30: Build Input Differential Pair (Sub-Threshold)
  - LTspice setup:
    * M1, M2: NMOS W=2000µm, L=8µm
    * M5: Tail current source, I_SS = 2.5µA (very small!)
    * V_DD = 2.8V
    * V_CM = 1.4V
  
  - Challenge: LTspice default models assume strong inversion
  - Solution: Use real SPICE model for 1.5µm process
    * Search online: "1.5um CMOS SPICE model" or use generic
    * Or adjust model parameters for sub-threshold behavior
  
  - Key parameters to set/adjust:
    .model NMOS_SUB NMOS (
    + VTO=0.7        ; Threshold voltage
    + KP=20u         ; Transconductance parameter (low for old process)
    + LAMBDA=0.05    ; Channel-length modulation
    + TOX=30n        ; Oxide thickness (thick for 1.5um)
    )
  
  - DC Operating Point Check:
    1. Run .op
    2. Verify V_GS < V_T (sub-threshold!)
       Expected: V_GS ≈ 0.5-0.6V (below V_T = 0.7V)
    3. Check I_D ≈ 1.25µA per transistor
    4. Verify both in sub-threshold region
  
  - Calculate g_m manually:
    * g_m = I_D / (n × V_T)
    * With I_D = 1.25µA, n = 1.5, V_T = 26mV
    * g_m = 1.25µA / (1.5 × 26mV) = 32 µS
    * Compare to simulation: .op should show g_m
  
  - Test differential operation:
    * Apply small differential signal (1mV)
    * Measure transconductance
    * Should be in µS range (much smaller than strong inversion)

☐ 8:30-9:00: Documentation
  - Lab journal: Sub-threshold differential pair
  - Key measurements:
    * V_GS values (should be < V_T)
    * I_D per transistor
    * Calculated vs simulated g_m
    * Verification of sub-threshold operation
  
  - Challenges log:
    * "LTspice default models don't capture sub-threshold well"
    * Solution: Adjusted VTO and KP parameters
    * Need to verify if behavior matches paper
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal entry complete
☐ Screenshot: DC operating point showing V_GS < V_T
☐ Note: "Sub-threshold requires careful model setup"
☐ Commit to GitHub: /harrison-neural-amp/schematics/input_pair.asc
```

**Total Time Today:** 4 hours

---

#### **Day 34 - Wednesday, March 5, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:00: Reading - Noise in Amplifiers
  - Book: Razavi "Design of Analog CMOS IC" Ch 7.3-7.4
  - Pages: 285-310 (Noise Analysis, Input-Referred Noise)
  - Key concepts:
    * Thermal noise in resistors and MOSFETs
    * Flicker noise (1/f noise)
    * Input-referred noise calculation
    * How to minimize noise in amplifiers
  
  - Critical for this paper:
    * Neural signals: 10-100 µV
    * Amplifier noise must be << signal
    * Target: < 100 nV/√Hz
    * Paper achieves: 40 nV/√Hz

☐ 7:00-7:30: Noise Calculation
  - Hand-calculate expected noise:
    * Thermal noise from input pair: 4kT × (2/3) × g_m
    * With g_m = 32 µS
    * Calculate input-referred noise voltage
    * Compare to paper's 40 nV/√Hz target
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:30: Complete Circuit Assembly
  - Add current mirror load to differential pair:
    * M3, M4: PMOS W=500µm, L=8µm
    * Configure as current mirror
    * Both should be in sub-threshold too
  
  - Full circuit now:
    [M1-M2 diff pair] → [M3-M4 PMOS load] ← [V_DD]
           ↓
    [M5 tail current] ← [I_bias = 2.5µA]
           ↓
         [GND]
  
  - DC Verification:
    1. All transistors in sub-threshold?
    2. Currents balanced?
    3. Output DC voltage ≈ 1.4V (mid-rail)?
  
  - AC Analysis:
    .ac dec 100 1 100k
    
    Measurements:
    * Midband gain (100 Hz - 1 kHz)
      - Paper reports: 40.8 dB
      - Calculate: A_v = g_m × r_out
      - In sub-threshold, r_out very high
    
    * Bandwidth (3dB frequency)
      - Paper reports: 7.2 kHz
      - Verify: f_3dB = 1/(2π × R_out × C_L)
    
    * Gain-bandwidth product
      - GBW = A_v × BW
  
  - Results table:
    | Metric | Paper | My Simulation | Error % | Status |
    |--------|-------|---------------|---------|--------|
    | Gain | 40.8 dB | __dB | __% | ☐ |
    | BW | 7.2 kHz | __kHz | __% | ☐ |
    | Power | 7 µW | __µW | __% | ☐ |

☐ 8:30-9:00: Noise Simulation
  - LTspice noise analysis:
    .noise V(out) V_in dec 100 1 100k
  
  - Plot: Input-referred noise spectral density
  - Measure at 1 kHz (midband)
  - Compare to paper: 40 nV/√Hz
  
  - Identify noise contributors:
    * Input pair (dominant)
    * Load resistors
    * Tail current source
  
  - Document noise breakdown
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: Complete circuit characterization
☐ Bode plot: Gain and phase response
☐ Noise spectrum plot
☐ Comparison table: Paper vs simulation
☐ Note any discrepancies and hypotheses why
☐ Commit updated schematic and results
```

**Total Time Today:** 4 hours

---

#### **Day 35 - Thursday, March 6, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Paper Analysis - Remaining Sections
  - Paper: Harrison & Charles (Sections IV-V)
  - Pages: Measurement results, comparison with prior art
  
  - Study carefully:
    * Figure 5: Measured frequency response
    * Figure 6: Noise spectrum
    * Table II: Performance comparison with other designs
  
  - Understand:
    * How they measured noise (setup)
    * Test conditions
    * Why performance better than prior art
  
  - Complete Pass 3 (Critical Analysis):
    * Strengths of this design
    * Any limitations not mentioned
    * What could be improved
    * How applicable to modern processes
  
  - Write 3-sentence synthesis:
    "[What problem it solves]
     [How it solves it uniquely]
     [Why this matters for your learning]"
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:30: Optimization and Troubleshooting
  - If simulation doesn't match paper:
    
    Common issues and fixes:
    
    1. Gain too low?
       - Check: Are all transistors truly sub-threshold?
       - Verify: Output resistance (should be very high)
       - Try: Increase transistor length (higher r_out)
    
    2. Bandwidth wrong?
       - Check: Load capacitance assumption
       - Try: Vary C_L to match bandwidth
       - Document: What C_L value works
    
    3. Noise too high?
       - Check: Device sizes (larger = lower noise)
       - Verify: Bias conditions
       - Note: Noise scales with √(W×L)
    
    4. Power consumption off?
       - Verify: All bias currents
       - Check: Supply voltage exactly 2.8V
       - Confirm: Sub-threshold operation (not strong inv)
  
  - Iteration log:
    | Iteration | Change Made | Result | Match Improved? |
    |-----------|-------------|--------|-----------------|
    | v1 | Initial (from paper values) | 38 dB gain | Baseline |
    | v2 | Increased L to 10µm | 41 dB gain | ✓ Better |
    | v3 | Adjusted C_L to 12pF | BW = 7.0 kHz | ✓ Closer |
  
  - Final tuning:
    * Adjust until >80% match on all key specs
    * Document all deviations from paper values
    * Explain rationale for each change

☐ 8:30-9:00: CMRR Testing
  - Measure common-mode rejection:
    * Apply common-mode signal
    * Measure output variation
    * CMRR = A_dm / A_cm
    * Target: > 60 dB (from paper)
  
  - If CMRR low:
    * Check tail current source impedance
    * May need cascode tail (not shown in paper)
    * Document trade-off
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: Optimization process
☐ Iteration log with all changes
☐ Final performance comparison table
☐ Assumptions document:
  "Changed X because..."
  "Assumed Y since paper didn't specify..."
☐ Commit final working version
```

**Total Time Today:** 4 hours

---

#### **Day 36 - Friday, March 7, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Complete Recreation Documentation
  - Create comprehensive recreation report:
  
  # Harrison Neural Amplifier Recreation
  
  ## Original Paper
  - Title: "A Micropower Low-Noise Amplifier for Neural Recording"
  - Authors: R. R. Harrison, C. Charles
  - Venue: IEEE JSSC, Jan 2003
  
  ## Recreation Objective
  Understand sub-threshold design techniques for ultra-low-power
  applications by recreating this classic neural amplifier design.
  
  ## Design Approach
  ### Phase 1: Information Extraction
  - Extracted transistor sizes from paper
  - Calculated bias conditions from power spec
  - Identified sub-threshold operation as key technique
  
  ### Phase 2: Circuit Implementation
  - Built differential pair in weak inversion
  - Added PMOS current mirror load
  - Verified sub-threshold operation (V_GS < V_T)
  
  ### Phase 3: Performance Verification
  [Detailed measurements]
  
  ## Results Comparison
  | Specification | Paper | Recreation | Match % | Status |
  |---------------|-------|------------|---------|--------|
  | Gain | 40.8 dB | __dB | __% | ☐ |
  | Bandwidth | 7.2 kHz | __kHz | __% | ☐ |
  | Noise | 40 nV/√Hz | __nV/√Hz | __% | ☐ |
  | Power | 7 µW | __µW | __% | ☐ |
  | CMRR | >60 dB | __dB | __% | ☐ |
  
  Overall Match Quality: __%
  
  ## Key Learnings
  1. Sub-threshold operation achieves 10× better g_m/I_D ratio
  2. Trade-off: Lower speed, but adequate for neural signals
  3. Noise optimization: Larger input transistors help
  4. [Other insights]
  
  ## Challenges Encountered
  1. **Challenge:** LTspice models don't capture sub-threshold well
     **Solution:** Adjusted model parameters VTO and KP
     **Learning:** Real process models essential for accuracy
  
  2. **Challenge:** Exact load capacitance not specified
     **Solution:** Tuned C_L to match bandwidth
     **Learning:** Some iteration always necessary
  
  ## Deviations from Paper
  - Changed: [List any component value changes]
  - Reason: [Explain why each was necessary]
  - Impact: [How it affected performance]
  
  ## Design Insights
  [Your understanding of why this design works]
  [What you'd do differently]
  [How this applies to your future designs]
  
  ## Files
  - Schematic: neural_amp_final.asc
  - Results: /results/characterization.txt
  - Plots: /plots/
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:30: Create Comparison Visualizations
  - Generate side-by-side plots:
    
    1. Frequency Response:
       - Paper Figure 5 (reference)
       - Your simulation
       - Overlaid if possible
    
    2. Noise Spectrum:
       - Paper Figure 6
       - Your noise simulation
       - Annotate differences
    
    3. Performance Summary:
       - Bar chart comparing all specs
       - Paper vs Recreation
       - % match shown
  
  - Export high-quality images for portfolio
  - Annotate all plots professionally

☐ 8:30-9:00: Week 6 Summary Preparation
  - Summarize paper recreation experience:
    * Time invested: ~__ hours
    * Match quality: __%
    * Difficulty: __/10
    * Learning value: __/10
  
  - Identify next paper to recreate (for later)
```

**Documentation (9:00-9:30 PM)**

```
☐ Complete recreation report (portfolio piece #4)
☐ Export report as PDF
☐ All plots saved and organized
☐ GitHub: Full project pushed
  - /projects/harrison-neural-amp/
    * README.md (overview)
    * recreation_report.pdf
    * /schematics
    * /results
    * /plots
    * /documentation
☐ Prepare for tomorrow's major content day
```

**Total Time Today:** 4 hours

---

#### **Day 37 - Saturday, March 8, 2026**

**Major Project & Content Day (9:00 AM - 6:00 PM) - 8 hours**

```
☐ 9:00-12:00: Layout Introduction - Magic VLSI
  - **New skill: Physical layout of circuits**
  
  - Install Magic VLSI (if not done):
    * Download from: opencircuitdesign.com/magic
    * Install SkyWater 130nm PDK
    * Follow setup tutorial
  
  - Magic Tutorial - Part 1 (2 hours):
    
    Hour 1: Basic Magic Interface
    * Launch Magic: `magic -T sky130A`
    * Learn keyboard shortcuts:
      - Space: Select/deselect
      - p: Paint layer
      - e: Erase
      - w: Wire (routing)
      - x: Expand selection
    * Create simple shapes
    * Understand layers:
      - nwell (n-type well)
      - pwell (p-type well)
      - poly (polysilicon - gates)
      - li1 (local interconnect)
      - metal1, metal2 (routing)
      - nsd, psd (source/drain diffusions)
    
    Hour 2: First Layout - Single NMOS Transistor
    * Step-by-step:
      1. Paint nwell region
      2. Paint poly for gate
      3. Paint nsd (n+ diffusion) on both sides
      4. Paint contacts (li1 to nsd)
      5. Extract to verify: `extract all`
      6. Check DRC: `drc check`
      7. View netlist: `ext2spice`
    
    * Verify:
      - DRC clean (Design Rule Check)
      - Correct connectivity
      - Proper W/L ratio
    
    * Screenshot your first transistor layout!
  
  - Take detailed notes on:
    * Layer stack understanding
    * Minimum spacing rules
    * Contact placement
    * Common DRC errors

☐ 12:00-1:00: Lunch

☐ 1:00-3:00: Layout Practice - Current Mirror
  - Project: Layout a simple current mirror
  - Reference: Week 3 current mirror schematic
  
  - Layout strategy:
    1. Floorplan:
       - M1 (reference) on left
       - M2 (mirror) on right
       - Symmetric placement
    
    2. Match considerations:
       - Same orientation (both horizontal or both vertical)
       - Same surroundings (dummy transistors)
       - Interdigitation for best matching
       - Common-centroid if possible
    
    3. Implementation:
       - Draw M1: W=10µm, L=2µm
       - Draw M2: W=10µm, L=2µm (match M1 exactly)
       - Connect gates together (poly)
       - Connect M1 gate-drain (diode connection)
       - Add contacts and metal routing
       - Add guard rings (nwell contacts)
    
    4. Verification:
       - Run DRC: Should be clean
       - Extract: `extract all`
       - LVS check: `ext2spice lvs`
       - Compare to schematic netlist
  
  - Document:
    * Screenshot of layout
    * DRC report
    * LVS report
    * Notes on matching techniques used

☐ 3:00-4:00: Layout Learning Consolidation
  - Read: Baker "CMOS Circuit Design, Layout, and Simulation"
  - Chapter 3: "The Layout of a CMOS Circuit" (pages 1-30)
  
  - Key concepts:
    * Design rules and why they exist
    * Via and contact sizing
    * Parasitic capacitance sources
    * Layout for matching
    * Common layout mistakes
  
  - Create layout design rules reference sheet:
    * Minimum widths
    * Minimum spacings
    * Contact sizes
    * Via stack rules
  
  - Add to reference document: "Layout Best Practices"

☐ 4:00-6:00: Video Content Creation
  - Edit video: "Paper Recreation: Neural Amplifier"
  
  - Video structure (12-15 min):
    1. Intro (0:00-1:00):
       * Why recreate papers?
       * What paper chosen
       * What you'll learn
    
    2. Paper Overview (1:00-3:00):
       * Neural recording application
       * Sub-threshold technique
       * Key innovation: µW power, nV noise
    
    3. Recreation Process (3:00-8:00):
       * Information extraction challenges
       * Building the circuit
       * Sub-threshold operation setup
       * Debugging and iteration
    
    4. Results Comparison (8:00-11:00):
       * Side-by-side spec comparison
       * What matched well
       * What was different and why
       * Show actual simulations
    
    5. Key Learnings (11:00-13:00):
       * Sub-threshold design insights
       * Recreation process lessons
       * How to approach future papers
    
    6. Outro (13:00-14:00):
       * Layout teaser (next topic)
       * Links to full documentation
       * GitHub and resources
  
  - Include:
    * Paper figures (properly cited)
    * Your simulation results
    * Comparison plots
    * Schematic walkthroughs
  
  - Export: week06_paper_recreation.mp4
```

**Evening (6:00-8:00 PM)**

```
☐ 6:00-7:00: Portfolio Updates
  - GitHub:
    * Add paper recreation project
    * Add first layout screenshots
    * Update main README:
      "✓ First paper recreation complete (Harrison Neural Amp)
       ✓ Layout learning begun (Magic VLSI)"
  
  - Portfolio website update (if you have one):
    * Add "Paper Recreations" section
    * Link to Harrison amp project
    * Include performance comparison

☐ 7:00-8:00: Community Engagement
  - Reddit post in r/chipdesign:
    "Recreated a classic paper: Sub-threshold neural amplifier"
    
    Include:
    * Brief description of paper
    * Your results vs paper
    * Challenges overcome
    * Link to full documentation
    * "Happy to answer questions about paper recreation process!"
  
  - Twitter/X thread:
    1/ "Just finished recreating my first research paper! 📄
       Harrison & Charles' ultra-low-power neural amplifier
       
       Their design: 7 µW, 40 nV/√Hz noise
       My recreation: 7.2 µW, 42 nV/√Hz (94% match!)
       
       Thread on what I learned... 🧵"
    
    2/ "The key innovation: Sub-threshold operation
       Running transistors below threshold voltage gives 10× better 
       g_m/I_D ratio. Perfect for µW power budgets."
    
    3/ "Challenge: LTspice doesn't model sub-threshold well by default
       Solution: Adjusted SPICE model parameters
       Learning: Always validate your simulator setup!"
    
    [Continue with 5-7 more tweets covering key insights]
    
    Final: "Full recreation on GitHub: [link]
    #AnalogDesign #ICDesign #PaperRecreation"
  
  - Engage with comments and questions
```

**Total Time Today:** 8 hours

---

#### **Day 38 - Sunday, March 9, 2026**

**Review & Planning Day (9:00 AM - 5:00 PM) - 8 hours**

```
☐ 9:00-10:30: Week 6 Comprehensive Review
  - Complete Week 6 summary document
  
  - Achievements:
    ✓ Paper recreation completed (94% match)
    ✓ Sub-threshold design understood
    ✓ Layout basics learned (Magic VLSI)
    ✓ First transistor and current mirror layouts
  
  - Self-quiz:
    * Explain sub-threshold operation (no notes)
    * List steps for paper recreation
    * Draw layout of NMOS transistor from memory

☐ 10:30-12:00: Month 2 Completion Review
  - **Major milestone: Month 2 complete!**
  
  - Month 2 Summary:
    
    Weeks 4-6 Completed:
    * Week 4: Differential amplifiers
    * Week 5: Two-stage op-amp design
    * Week 6: Paper recreation + layout intro
    
    Major Designs:
    1. High-CMRR differential amplifier (82dB)
    2. Two-stage op-amp (72dB gain, 64° PM)
    3. Harrison neural amplifier recreation (94% match)
    
    New Skills:
    * Frequency compensation (Miller)
    * Stability analysis
    * Paper recreation methodology
    * Layout basics (Magic VLSI)
    * Sub-threshold design
  
  - Month 2 Metrics:
    * Total hours: ~120 hours
    * Circuits designed: 10+ (including variations)
    * Papers read: 2 (deep analysis)
    * Videos published: 6
    * Portfolio pieces: 4 major projects

☐ 12:00-1:00: Lunch

☐ 1:00-2:30: Video Publishing
  - Upload Week 6 video:
    * Title: "Recreating a Research Paper: Neural Amplifier Design"
    * Description with detailed explanation
    * Link to GitHub documentation
    * Add to playlist
  
  - Community engagement:
    * Twitter update
    * Reddit progress post

☐ 2:30-4:30: Month 3 Detailed Planning
  - Preview: Specialization & Advanced Topics
  
  - Month 3 Overview (Weeks 7-10):
    * Week 7: Data converter basics (ADC fundamentals)
    * Week 8: SAR ADC design (comparator, DAC)
    * Week 9: Advanced layout (op-amp layout project)
    * Week 10: Second paper recreation + PVT analysis
  
  - Primary resources for Month 3:
    * Book: Johns & Martin "Analog Integrated Circuit Design" 
      Ch 11-12 (Data Converters)
    * Book: Baker "CMOS Circuit Design, Layout, and Simulation"
      Ch 4-6 (Layout)
    * Paper: "A 10-bit 50-MS/s SAR ADC With Monotonic Capacitor 
      Switching" (Huang et al., JSSC 2010)
  
  - Create Week 7 detailed schedule:
    * Day-by-day tasks
    * Reading assignments
    * Simulation milestones
    * Documentation checkpoints
  
  - Prepare tools and resources:
    * Download papers for Month 3
    * Bookmark tutorial videos
    * Prepare lab templates
  
  - Month 3 goals:
    ☐ Design complete SAR ADC
    ☐ Layout complete op-amp with DRC/LVS clean
    ☐ Recreate second paper (>85% match)
    ☐ Learn corner analysis (PVT corners)
    ☐ Monte Carlo analysis proficiency
    ☐ Publish 4+ videos
    ☐ 5 portfolio pieces total

☐ 4:30-5:00: Cadence Check-in
  - If Cadence access now available:
    * Plan Week 7 Cadence learning sessions
    * Identify tutorials to complete
    * Set up library for Month 3 designs
  
  - If Cadence still unavailable:
    * Continue applying for academic license
    * Meanwhile, maximize LTspice expertise
    * Focus on concepts (transferable to Cadence later)
```

**Total Time Today:** 8 hours
**Week 6 Total:** 40 hours
**Month 2 Total:** 120 hours

---

## **MONTH 3: DATA CONVERTERS & ADVANCED LAYOUT (March 10 - April 9, 2026)**

### **Week 7: Data Converter Fundamentals**

#### **Day 39 - Monday, March 10, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - ADC Introduction
  - Book: Johns & Martin "Analog Integrated Circuit Design" Ch 11.1-11.2
  - Pages: 433-458 (Introduction to Data Converters, Quantization)
  - Key concepts:
    * ADC vs DAC fundamentals
    * Sampling theory basics
    * Quantization noise
    * Resolution vs accuracy
    * Key specs: ENOB, SNR, THD, SFDR
  
  - Understand performance metrics:
    * ENOB (Effective Number of Bits)
    * SNR (Signal-to-Noise Ratio)
    * THD (Total Harmonic Distortion)
    * SFDR (Spurious-Free Dynamic Range)
    * INL (Integral Non-Linearity)
    * DNL (Differential Non-Linearity)
  
  - Hand-derive:
    * Quantization noise: e_q = Δ/√12
    * SNR for ideal N-bit ADC: SNR = 6.02N + 1.76 dB
  
  - Note applications:
    * Audio (16-24 bits, 44-192 kHz)
    * Communications (8-12 bits, GHz)
    * Instrumentation (16-24 bits, kHz-MHz)
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:30: Video Lectures on ADCs
  - Watch: Boris Murmann Stanford Lecture on ADC Basics
  - YouTube: Search "Murmann ADC lecture Stanford"
  - Duration: ~60 minutes
  
  - Take detailed notes:
    * [Timestamp]: ADC architecture overview
    * [Timestamp]: Performance metrics explained
    * [Timestamp]: Nyquist-rate vs oversampling
    * [Timestamp]: ADC types comparison
  
  - Create comparison table of ADC architectures:
    | Type | Speed | Resolution | Power | Complexity | Application |
    |------|-------|------------|-------|------------|-------------|
    | Flash | Very High | Low (6-8b) | High | High | Communications |
    | SAR | Medium | Medium (8-16b) | Low | Medium | IoT, Sensors |
    | Pipeline | High | High (10-14b) | Medium | Medium | Video, Imaging |
    | Sigma-Delta | Low | Very High (16-24b) | Low | High | Audio |

☐ 8:30-9:00: Sampling Theory Review
  - Read: Johns & Martin Ch 11.3
  - Topic: Nyquist sampling theorem
  - Key points:
    * Sampling frequency f_s > 2 × f_max (Nyquist criterion)
    * Aliasing and anti-aliasing filters
    * Sample-and-hold circuits
  
  - Hand-draw:
    * Frequency domain representation of sampling
    * Aliasing visualization
```

**Documentation (9:00-9:30 PM)**

```
☐ Create ADC fundamentals summary document
☐ ADC architecture comparison table
☐ Notes on sampling theory
☐ Commit to GitHub: /notes/week07/day39_adc_intro.md
```

**Total Time Today:** 4 hours

---

#### **Day 40 - Tuesday, March 11, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - Sample and Hold
  - Book: Johns & Martin Ch 11.4
  - Pages: 480-502 (Sample-and-Hold Circuits)
  - Key concepts:
    * Track mode vs hold mode
    * Switch design (NMOS, PMOS, transmission gate)
    * Hold capacitor sizing
    * Droop rate
    * Acquisition time
    * Settling behavior
  
  - Design equations:
    * Acquisition time: t_acq ≈ 10 × R_on × C_hold
    * Droop rate: dV/dt = I_leak / C_hold
    * Thermal noise: v_n² = kT/C
  
  - Understand trade-offs:
    * Larger C_hold: Lower noise, slower acquisition
    * Smaller C_hold: Faster, but more noise and droop
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Design Sample-and-Hold Circuit
  - Build in LTspice:
    * Transmission gate switch (NMOS + PMOS parallel)
    * Hold capacitor: C_hold = 1pF
    * Unity-gain buffer (op-amp) after capacitor
    * Clock signal for switching
    * V_DD = 1.8V
  
  - Switch design:
    * NMOS: W=5µm, L=0.18µm (minimum length for speed)
    * PMOS: W=10µm, L=0.18µm (2× wider, mobility difference)
    * Calculate R_on: ~1kΩ typical
  
  - Simulations:
    
    1. Track Mode (switch closed):
       * Apply sinusoidal input (1kHz, 0.5V amplitude)
       * Verify output follows input
       * Measure tracking error
    
    2. Hold Mode (switch open):
       * Open switch, verify voltage held
       * Measure droop rate over 100µs
       * Calculate from slope: dV/dt
    
    3. Acquisition Time:
       * Apply step input
       * Measure time to settle within 0.1% of final value
       * Compare to calculated: t_acq = 10×R_on×C_hold
    
    4. Clock Feedthrough:
       * Observe voltage spike when switch opens
       * Caused by parasitic capacitance
       * Note magnitude
  
  - Results table:
    | Parameter | Calculated | Simulated | Match? |
    |-----------|------------|-----------|--------|
    | R_on | ~1kΩ | __kΩ | ☐ |
    | t_acq | __ns | __ns | ☐ |
    | Droop rate | __mV/µs | __mV/µs | ☐ |
    | Clock feedthrough | - | __mV | - |

☐ 8:45-9:00: Documentation
  - Lab journal: Sample-and-hold design
  - Key finding: "Clock feedthrough is significant issue"
  - Note: "Will need bottom-plate sampling technique"
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal entry with S/H characterization
☐ Waveforms showing track and hold modes
☐ Annotated schematic
☐ Commit to GitHub
```

**Total Time Today:** 4 hours

---

#### **Day 41 - Wednesday, March 12, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - Comparators
  - Book: Johns & Martin Ch 11.5
  - Pages: 503-525 (Comparator Design for ADCs)
  - Key concepts:
    * Comparator vs op-amp (no stability needed!)
    * Metastability and regeneration
    * Offset voltage
    * Propagation delay
    * Kickback noise
  
  - Comparator architectures:
    * Pre-amp + latch
    * Dynamic comparator (clocked)
    * Continuous-time comparator
  
  - Design considerations:
    * Speed (propagation delay)
    * Resolution (minimum detectable voltage)
    * Offset (matching)
    * Kickback to input
  
  - Key equations:
    * Regeneration time constant: τ = C_L / g_m
    * Resolution time: t_res ≈ τ × ln(V_out / V_in)
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Design Dynamic Comparator
  - Build in LTspice: StrongARM latch comparator
  
  - Circuit topology:
    * Input differential pair (M1, M2)
    * Cross-coupled latch (M3, M4, M5, M6)
    * Tail switch (M7) for clocking
    * Reset switches
  
  - Component sizing:
    * Input pair: W=10µm, L=0.18µm
    * Latch: W=5µm, L=0.18µm
    * Tail: W=20µm, L=0.18µm (large for speed)
  
  - Operation:
    1. Reset phase (CLK=0):
       * Output nodes pre-charged
       * Latch disabled
    
    2. Comparison phase (CLK=1):
       * Tail switch closes
       * Input pair amplifies difference
       * Latch regenerates to rail
  
  - Simulations:
    
    1. DC Sweep (Input Differential):
       * Sweep V_in+ - V_in- from -100mV to +100mV
       * Observe sharp transition at 0mV
       * Measure transition width (resolution)
    
    2. Transient with Small Input:
       * Apply V_diff = 1mV
       * Measure propagation delay (50% to 90% output)
       * Typical: 1-5ns for this design
    
    3. Resolution Test:
       * Start with V_diff = 10mV
       * Reduce until comparator fails (50% success rate)
       * Minimum detectable: ~100µV with this design
    
    4. Kickback Measurement:
       * Monitor input node during comparison
       * Observe voltage spike on input
       * Quantify kickback amplitude
  
  - Performance metrics:
    | Metric | Target | Achieved | Status |
    |--------|--------|----------|--------|
    | Delay | <5ns | __ns | ☐ |
    | Resolution | <1mV | __mV | ☐ |
    | Offset | <10mV | __mV | ☐ |
    | Kickback | <20mV | __mV | ☐ |

☐ 8:45-9:00: Analysis
  - Understand speed vs power trade-off:
    * Larger tail current → faster, more power
    * Larger input pair → faster, more area/power
  - Document design choices
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: Dynamic comparator design
☐ Transient waveforms showing regeneration
☐ Key insight: "StrongARM is very fast and low power"
☐ Commit schematic and results
```

**Total Time Today:** 4 hours

---

#### **Day 42 - Thursday, March 13, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - Flash ADC
  - Book: Johns & Martin Ch 11.6
  - Pages: 526-545 (Flash ADC Architecture)
  - Key concepts:
    * Fastest ADC architecture
    * 2^N - 1 comparators for N bits
    * Resistor ladder for reference voltages
    * Thermometer code to binary encoder
    * Bubble errors and encoding
  
  - Understand:
    * Why flash is fast: All comparisons parallel
    * Why limited resolution: Exponential comparator count
    * Typical: 6-8 bits practical
    * Power consumption high
  
  - Design blocks:
    * Resistor ladder (reference generation)
    * Comparator array
    * Thermometer-to-binary encoder
  
  - Calculate for 4-bit flash ADC:
    * Number of comparators: 2^4 - 1 = 15
    * Reference levels: 0, V_ref/16, 2V_ref/16, ..., 15V_ref/16
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Design 3-bit Flash ADC
  - Simplified design to understand concept
  
  - Build in LTspice:
    * 3-bit resolution = 8 levels = 7 comparators
    * Reference voltage: V_ref = 1.6V
    * Resistor ladder: 8 resistors (all equal value, e.g., 10kΩ)
    * 7 comparators (use simplified model or sub-circuit)
  
  - Reference voltages (from resistor ladder):
    * V_ref[0] = 0.2V (1/8 of V_ref)
    * V_ref[1] = 0.4V (2/8)
    * V_ref[2] = 0.6V (3/8)
    * V_ref[3] = 0.8V (4/8)
    * V_ref[4] = 1.0V (5/8)
    * V_ref[5] = 1.2V (6/8)
    * V_ref[6] = 1.4V (7/8)
  
  - Simulation:
    1. DC sweep input from 0 to 1.6V
    2. Plot all 7 comparator outputs
    3. Observe thermometer code:
       * Input = 0.5V → Outputs: 1100000 (2 comparators high)
       * Input = 0.9V → Outputs: 1111000 (4 comparators high)
       * Input = 1.5V → Outputs: 1111111 (all high)
    
    4. Verify transition points align with reference voltages
  
  - Encoder (conceptual):
    * Thermometer to binary conversion
    * 0000001 → 001 (binary)
    * 0000011 → 010
    * 0000111 → 011
    * ... etc
    
    * Can implement with digital logic or behavioral model
  
  - Performance analysis:
    * Speed: Limited only by comparator delay (~ns)
    * Resolution: 3 bits (8 levels)
    * Power: 7 comparators × power per comparator
    * Area: Dominated by comparators

☐ 8:45-9:00: Documentation
  - Lab journal: Flash ADC design
  - Thermometer code output visualization
  - Calculate power consumption
  - Note scaling problem: 10-bit would need 1023 comparators!
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: Flash ADC implementation
☐ Plot showing all comparator outputs vs input
☐ Analysis of why flash limited to 6-8 bits
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 43 - Friday, March 14, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - SAR ADC Introduction
  - Book: Johns & Martin Ch 11.7
  - Pages: 546-570 (Successive Approximation ADC)
  - Key concepts:
    * Binary search algorithm
    * DAC for reference generation
    * Comparator + control logic
    * N bits requires N clock cycles
    * Low power, moderate speed
  
  - Understand SAR operation:
    1. Sample input
    2. Try MSB = 1, compare to input
    3. If DAC > input: MSB = 0, else MSB = 1
    4. Repeat for each bit (MSB to LSB)
    5. N iterations for N bits
  
  - SAR advantages:
    * Only 1 comparator (vs 2^N-1 for flash)
    * Low power
    * Moderate speed (MHz to 100s MHz)
    * Scalable resolution
  
  - SAR challenges:
    * DAC settling time
    * Comparator offset
    * Switching noise
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Paper Reading - SAR ADC
  - Paper: "A 10-bit 50-MS/s SAR ADC With a Monotonic Capacitor Switching Procedure"
  - Authors: G.-Y. Huang et al.
  - Venue: IEEE JSSC, April 2010, Vol. 45, No. 4, pp. 731-740
  
  - Apply 3-Pass Method:
    
    Pass 1 (15 min):
    * Abstract: What's the innovation?
      - Monotonic switching reduces DAC capacitor size by 50%
      - Achieves 50 MS/s with 0.8mW power
    * Figures: Study Figure 2 (switching scheme)
    * Conclusion: 57dB SNDR, 9.1 ENOB
    * Decision: Excellent paper for recreation next week
    
    Pass 2 (60-90 min):
    * Section II: Conventional SAR switching
      - Binary-weighted capacitor array
      - 2^N total capacitance for N bits
      - Energy inefficient
    
    * Section III: Monotonic switching (KEY INNOVATION)
      - Switches only up (never down)
      - Reduces total capacitance
      - Lower power consumption
      - Study Figure 3 carefully
    
    * Section IV: Circuit implementation
      - Capacitor array: 1C, 2C, 4C, 8C, 16C... (binary weighted)
      - Comparator: Dynamic latch type
      - SAR logic: Digital control
      - Extract component values if given
    
    * Section V: Measurement results
      - 10-bit resolution
      - 50 MS/s sampling rate
      - 0.8mW power (very efficient!)
      - FOM (Figure of Merit) calculation
  
  - Take detailed notes:
    * Draw switching sequence diagram
    * Understand why "monotonic" saves power
    * Note any tricks or techniques
    * List questions for deeper understanding

☐ 8:45-9:00: Week 7 Summary
  - Create Week 7 summary document:
    * ADC fundamentals learned
    * Sample-and-hold designed
    * Comparator designed
    * Flash ADC understanding
    * SAR ADC introduction
  - Ready for Week 8: Full SAR ADC design
```

**Documentation (9:00-9:30 PM)**

```
☐ Paper notes: Pass 1 & 2 complete
☐ Week 7 summary document
☐ Prepare for weekend major project
☐ Commit all week's notes and designs
```

**Total Time Today:** 4 hours

---

#### **Day 44 - Saturday, March 15, 2026**

**Major Project Day (9:00 AM - 6:00 PM) - 8 hours**

```
☐ 9:00-12:00: Building Block Library
  - Consolidate Week 7 designs into reusable library
  
  - Create LTspice library with:
    
    1. Sample-and-Hold Module:
       * Parameterized C_hold
       * Transmission gate switch
       * Buffer amplifier
       * Test bench included
       * Symbol for hierarchical use
    
    2. Dynamic Comparator Module:
       * StrongARM latch topology
       * Parameterized sizing
       * Clock input
       * Differential inputs
       * Digital output
       * Symbol created
    
    3. Resistor Ladder DAC:
       * 3-bit version (8 resistors)
       * Reference voltage generation
       * Parameterized
    
    4. Flash ADC 3-bit:
       * Complete system
       * Uses above building blocks
       * Includes encoder logic (behavioral)
  
  - Documentation for each:
    * Usage instructions
    * Parameter descriptions
    * Performance characteristics
    * Test bench examples
  
  - Test each module:
    * Verify functionality
    * Check parameter ranges
    * Document any limitations

☐ 12:00-1:00: Lunch

☐ 1:00-4:00: Comparative Analysis Project
  - Project: Compare ADC architectures quantitatively
  
  - Create test framework:
    * Same input signal (1kHz sine, 1Vpp)
    * Same resolution (compare 4-bit versions)
    * Same supply voltage (1.8V)
  
  - Designs to compare:
    1. Flash ADC (4-bit: 15 comparators)
    2. SAR ADC (simplified 4-bit for next week)
    3. Theoretical limits
  
  - Metrics to compare:
    | Metric | Flash | SAR | Winner |
    |--------|-------|-----|--------|
    | Speed (conversions/sec) | | | |
    | Power consumption | | | |
    | Area estimate (# transistors) | | | |
    | Complexity | | | |
    | Accuracy (INL, DNL) | | | |
  
  - Create visualization:
    * Bar charts comparing metrics
    * Spider/radar chart for overall comparison
    * Trade-off plots (speed vs power, etc.)
  
  - Write analysis report:
    * When to use flash
    * When to use SAR
    * Application recommendations
  
  - Export as portfolio piece #5

☐ 4:00-6:00: Video Content Creation
  - Edit video: "ADC Fundamentals - Building Blocks Explained"
  
  - Video structure (15-18 min):
    1. Intro (0:00-1:00):
       * What are ADCs?
       * Why they matter
       * What we'll build
    
    2. Sample-and-Hold (1:00-5:00):
       * How it works
       * Design and simulation
       * Key challenges (clock feedthrough)
    
    3. Comparator (5:00-9:00):
       * StrongARM latch design
       * Regeneration explained
       * Speed vs power trade-off
    
    4. Flash ADC Demo (9:00-12:00):
       * 3-bit example simulation
       * Thermometer code visualization
       * Scaling limitations
    
    5. SAR Preview (12:00-14:00):
       * Binary search concept
       * Why SAR is popular
       * Setup for next week
    
    6. Comparison (14:00-16:00):
       * Flash vs SAR trade-offs
       * Application guidance
    
    7. Outro (16:00-17:00):
       * Week 8 preview: Full SAR design
       * Links to designs
  
  - Export: week07_adc_fundamentals.mp4
```

**Evening (6:00-8:00 PM)**

```
☐ 6:00-7:00: GitHub Organization
  - Create /projects/adc-building-blocks/
    * README with overview
    * /sample-hold/
    * /comparator/
    * /flash-adc/
    * /analysis/ (comparison report)
  
  - Update main README:
    * Week 7 complete: ADC fundamentals
    * Building block library created
    * Link to comparison analysis

☐ 7:00-8:00: Community Engagement
  - Reddit post in r/chipdesign:
    "Built ADC building blocks from scratch - Here's what I learned"
    
    Include:
    * Sample-and-hold design
    * Comparator performance
    * Flash vs SAR comparison
    * Link to GitHub
  
  - Twitter thread on ADC week:
    "Week 7: Dove into ADC design 📊
     
     Built from ground up:
     • Sample-and-hold circuit
     • Dynamic comparator (StrongARM)
     • 3-bit flash ADC
     
     Key learning: Speed, power, and resolution form an
     impossible triangle. You pick two. 🔺
     
     Flash = fast + accurate, but power-hungry
     SAR = accurate + efficient, but slower
     
     Full designs: [GitHub link]"
  
  - Engage with comments
```

**Total Time Today:** 8 hours

---

#### **Day 45 - Sunday, March 16, 2026**

**Review & Planning Day (9:00 AM - 5:00 PM) - 8 hours**

```
☐ 9:00-11:00: Week 7 Deep Review
  - Review all ADC concepts learned:
    * Quantization theory
    * Sampling theory
    * Sample-and-hold design
    * Comparator design
    * Flash ADC architecture
    * SAR ADC introduction
  
  - Self-quiz (no notes):
    * Derive SNR formula for N-bit ADC
    * Explain StrongARM comparator operation
    * Draw 3-bit flash ADC block diagram
    * Explain SAR binary search algorithm
  
  - Practice problems:
    * Design S/H for given specs
    * Calculate flash ADC power consumption
    * Determine SAR conversion time

☐ 11:00-12:00: Video Publishing
  - Upload Week 7 video to YouTube
  - Title: "ADC Building Blocks: From Sample-Hold to Flash ADC"
  - Description with resources and timestamps
  - Tags: ADC, data converter, comparator, analog design
  - Add to playlist

☐ 12:00-1:00: Lunch

☐ 1:00-2:30: Community Engagement
  - Respond to comments on previous videos
  - Engage with ADC-related discussions
  - Share Week 7 results

☐ 2:30-5:00: Week 8 Detailed Planning
  - Topic: Complete SAR ADC Design
  
  - Week 8 structure:
    * Mon: Binary-weighted capacitor DAC design
    * Tue: SAR control logic (digital)
    * Wed: Complete SAR ADC integration
    * Thu: Testing and characterization (DNL, INL, ENOB)
    * Fri: Optimization and performance tuning
    * Sat: Full characterization and documentation
    * Sun: Start advanced layout project
  
  - Resources to prepare:
    * Re-read SAR paper (Huang et al.)
    * Bookmark SAR ADC tutorials
    * Prepare Verilog for digital control (if using)
    * Set up comprehensive test benches
  
  - Download additional reference:
    * Application notes on SAR ADCs
    * Example SAR designs (open-source if available)
  
  - Week 8 goals:
    ☐ Complete 10-bit SAR ADC design
    ☐ Achieve ENOB > 9 bits
    ☐ Full characterization (DNL, INL, FFT)
    ☐ Understand capacitor switching schemes
    ☐ Monte Carlo analysis of ADC
    ☐ Document complete design process
    ☐ Prepare for paper recreation in Week 10
  
  - Set up simulation framework:
    * Prepare input signal generators
    * FFT analysis scripts
    * DNL/INL calculation methods
    * Python scripts for post-processing (if needed)
```

**Total Time Today:** 8 hours
**Week 7 Total:** 40 hours

---

### **Week 8: SAR ADC Design**

#### **Day 46 - Monday, March 17, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - Capacitor DAC
  - Book: Johns & Martin Ch 11.7.2
  - Pages: 551-565 (Capacitive DAC for SAR)
  - Key concepts:
    * Binary-weighted capacitor array
    * Charge redistribution principle
    * Bottom-plate sampling
    * Split capacitor array
    * Parasitic insensitive design
  
  - Understand charge redistribution:
    * V_DAC = V_ref × (b_N-1 × 2^(N-1) + ... + b_1 × 2 + b_0) / 2^N
    * Each bit corresponds to binary-weighted capacitor
    * Capacitors: C, 2C, 4C, 8C, 16C... for 5-bit
  
  - Binary-weighted array:
    * Total capacitance: (2^N - 1) × C_unit
    * 10-bit: 1023 × C_unit (large!)
    * This is why split array used
  
  - Split capacitor technique:
    * Divides array into MSB and LSB sections
    * Bridge capacitor connects sections
    * Reduces total capacitance
  
  - Design considerations:
    * Unit capacitor size (matching vs area)
    * Parasitic capacitance
    * Settling time
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Design 4-bit Capacitor DAC
  - Simplified 4-bit for understanding
  
  - Build in LTspice:
    * Unit capacitor: C = 100fF
    * Binary-weighted array: 1C, 2C, 4C, 8C
    * Total: 15C = 1.5pF
    * Reference voltage: V_ref = 1.6V
    * Bottom plate switches (to V_ref or GND)
    * Top plate connected together (output node)
  
  - Switch configuration:
    * Each capacitor has switch to V_ref or GND
    * Controlled by digital bit (1 = V_ref, 0 = GND)
  
  - Simulation setup:
    1. Initial: All bottom plates to GND (DAC output = 0V)
    
    2. Test all digital codes (0000 to 1111):
       * 0000 → V_out = 0V
       * 0001 → V_out = V_ref/16 = 0.1V
       * 0010 → V_out = 2V_ref/16 = 0.2V
       * 0011 → V_out = 3V_ref/16 = 0.3V
       * ...
       * 1111 → V_out = 15V_ref/16 = 1.5V
    
    3. DC sweep of digital input:
       * Use voltage sources to represent bits
       * Sweep through all 16 codes
       * Plot V_out vs code
       * Should be perfectly linear staircase
  
  - Verification:
    * Check linearity (straight line)
    * Calculate INL (integral non-linearity)
      - Should be near zero for ideal capacitors
    * Calculate DNL (differential non-linearity)
      - Check each step is exactly 1 LSB
      - DNL = (actual step - ideal step) / ideal step
  
  - Results:
    | Code | Expected V_out | Simulated V_out | Error |
    |------|----------------|-----------------|-------|
    | 0000 | 0.0 V | __ V | __ mV |
    | 0001 | 0.1 V | __ V | __ mV |
    | ...  | ...   | ...  | ...   |
    | 1111 | 1.5 V | __ V | __ mV |
    
    * INL (max): __ LSB
    * DNL (max): __ LSB

☐ 8:45-9:00: Analysis
  - Understand perfect linearity with ideal components
  - Consider real-world effects:
    * Capacitor mismatch (manufacturing)
    * Parasitic capacitance
    * Switch resistance
  - Document how these affect INL/DNL
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: Capacitor DAC design
☐ Plot: DAC transfer characteristic (code vs voltage)
☐ INL/DNL analysis
☐ Schematic with annotations
☐ Commit to GitHub
```

**Total Time Today:** 4 hours

---

#### **Day 47 - Tuesday, March 18, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - SAR Logic
  - Book: Johns & Martin Ch 11.7.3
  - Pages: 565-578 (SAR Control Logic)
  - Key concepts:
    * Shift register for sequential control
    * Comparator output processing
    * Timing requirements
    * Synchronous vs asynchronous SAR
  
  - Understand SAR algorithm:
    ```
    1. Sample input voltage on capacitor array
    2. For bit N-1 to 0:
       a. Set bit[i] = 1
       b. DAC generates test voltage
       c. Compare to input
       d. If DAC > input: bit[i] = 0
          else: bit[i] = 1 (keep it)
    3. Output N-bit result
    ```
  
  - Timing diagram:
    * Clock cycle breakdown
    * DAC settling time
    * Comparator decision time
    * Logic propagation time
    * Total conversion time = N × T_clk
  
  - State machine design:
    * IDLE state
    * SAMPLE state
    * CONVERT[N-1:0] states (one per bit)
    * DONE state
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Design SAR Logic (Simplified)
  - Two approaches possible:
    
    Approach A: Behavioral Verilog/VHDL (if comfortable)
    Approach B: LTspice with digital primitives (simpler)
  
  - Using LTspice behavioral approach:
    
    * Create digital control block using:
      - Voltage-controlled switches
      - Behavioral voltage sources
      - Logic gates (if available in LTspice)
    
    * Or use simplified control:
      - Pre-program switching sequence
      - Use timed voltage sources
      - Focus on understanding algorithm
  
  - 4-bit SAR example:
    
    Conversion sequence for input = 0.65V (with V_ref = 1.6V):
    
    Clock 0 (Sample):
    * DAC = 0V, sample input = 0.65V
    
    Clock 1 (MSB):
    * Try bit[3] = 1: DAC = 0.8V
    * Compare: 0.8V > 0.65V → bit[3] = 0
    
    Clock 2 (bit 2):
    * Try bit[2] = 1: DAC = 0.4V
    * Compare: 0.4V < 0.65V → bit[2] = 1 (keep)
    
    Clock 3 (bit 1):
    * Current: bit[3:2] = 01 (DAC = 0.4V)
    * Try bit[1] = 1: DAC = 0.6V
    * Compare: 0.6V < 0.65V → bit[1] = 1 (keep)
    
    Clock 4 (LSB):
    * Current: bit[3:1] = 011 (DAC = 0.6V)
    * Try bit[0] = 1: DAC = 0.7V
    * Compare: 0.7V > 0.65V → bit[0] = 0
    
    Final: bit[3:0] = 0110 = 6
    DAC voltage = 6/16 × 1.6V = 0.6V
    Actual input = 0.65V
    Quantization error = 50mV (within 1 LSB = 100mV)
  
  - Implement control sequence:
    * Use piecewise linear voltage source or
    * Use time-delayed switches
    * Step through algorithm manually
  
  - Verify correct operation:
    * Try multiple input voltages
    * Check final code matches expected
    * Verify N clock cycles taken

☐ 8:45-9:00: Documentation
  - Document SAR algorithm clearly
  - Create timing diagram
  - Show step-by-step example
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: SAR control logic
☐ Algorithm flowchart
☐ Timing diagram
☐ Example conversion sequence documented
☐ Commit
```

**Total Time Today:** 4 hours

---

#### **Day 48 - Wednesday, March 19, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Review and Integration Planning
  - Review all components built:
    ✓ Sample-and-hold (Week 7)
    ✓ Comparator (Week 7)
    ✓ Capacitor DAC (Day 46)
    ✓ SAR logic (Day 47)
  
  - Plan integration:
    * Signal flow: Input → S/H → DAC (top plate) → Comparator → Logic → DAC control
    * Clock distribution
    * Timing constraints
    * Interface between analog and digital
  
  - Create system block diagram:
    * Draw complete SAR ADC
    * Label all connections
    * Note clock phases
    * Identify critical paths
  
  - List integration challenges:
    * Timing synchronization
    * Kickback from comparator to DAC
    * Clock feedthrough
    * Reference voltage stability
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Integrate Complete 4-bit SAR ADC
  - Build complete system in LTspice:
    
    Components:
    * Sample-and-hold circuit (from Week 7)
    * 4-bit capacitor DAC (from Day 46)
    * Dynamic comparator (from Week 7)
    * SAR control logic (simplified from Day 47)
    * Clock generator
  
  - Connections:
    1. Input signal → S/H input
    2. S/H output → DAC top plate (all capacitors)
    3. DAC output → Comparator positive input
    4. Comparator output → SAR logic
    5. SAR logic outputs → DAC switches (4 control signals)
  
  - Clock phases:
    * Phase 1: Sample (S/H tracks, DAC reset)
    * Phase 2: Hold + Convert (SAR algorithm runs)
    * N+1 clock cycles total (1 sample + N comparison)
  
  - Simulation setup:
    * Input: DC voltage (start simple: 0.65V)
    * Reference: 1.6V
    * Clock: 10 MHz (100ns period)
    * Observe:
      - Sample phase (100ns)
      - Bit 3 decision (100ns)
      - Bit 2 decision (100ns)
      - Bit 1 decision (100ns)
      - Bit 0 decision (100ns)
      - Total: 500ns conversion
  
  - Debug and iterate:
    * First attempt may not work!
    * Check each stage:
      - Is S/H holding voltage?
      - Is DAC producing correct voltages?
      - Is comparator deciding correctly?
      - Is logic sequencing properly?
    * Fix issues one by one
  
  - Verify operation:
    * Try different input voltages:
      - 0.2V → Should get code 0010 (2)
      - 0.5V → Should get code 0101 (5)
      - 1.0V → Should get code 1010 (10)
      - 1.4V → Should get code 1110 (14)
    * Check quantization error within 1 LSB

☐ 8:45-9:00: Initial Testing
  - Document any issues encountered
  - Note deviations from ideal behavior
  - Plan fixes for tomorrow
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: SAR ADC integration
☐ System block diagram
☐ Timing waveforms from simulation
☐ Issues log and resolutions
☐ Commit complete SAR ADC schematic
```

**Total Time Today:** 4 hours

---

#### **Day 49 - Thursday, March 20, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Reading - ADC Testing
  - Book: Johns & Martin Ch 11.9
  - Pages: 600-625 (ADC Testing and Characterization)
  - Key concepts:
    * Static testing: INL, DNL
    * Dynamic testing: ENOB, SNDR, THD, SFDR
    * FFT analysis
    * Histogram testing
  
  - Static metrics:
    * INL (Integral Non-Linearity):
      - Maximum deviation from ideal transfer curve
      - Measured in LSB
      - Should be < 0.5 LSB ideally
    
    * DNL (Differential Non-Linearity):
      - Deviation of step size from ideal 1 LSB
      - Should be < 1 LSB (else missing codes!)
      - DNL[i] = (V[i+1] - V[i]) / LSB - 1
  
  - Dynamic metrics:
    * SNDR (Signal-to-Noise-and-Distortion Ratio):
      - Includes all noise and distortion
      - SNDR = 10×log10(P_signal / P_noise+distortion)
    
    * ENOB (Effective Number of Bits):
      - ENOB = (SNDR - 1.76) / 6.02
      - Actual resolution accounting for all non-idealities
      - 10-bit ADC might have ENOB = 9.2 bits
    
    * THD (Total Harmonic Distortion):
      - Power in harmonics vs fundamental
    
    * SFDR (Spurious-Free Dynamic Range):
      - Difference between fundamental and largest spur
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Complete ADC Characterization
  - Test 1: Static Testing (DNL/INL)
    
    Method: Code Density (Histogram) Test
    * Apply ramp input (0 to V_ref)
    * Capture many samples
    * Count occurrences of each code
    * Calculate DNL and INL from histogram
    
    Simplified approach for LTspice:
    * DC sweep input from 0 to 1.6V in small steps
    * Record output code at each input voltage
    * Find transition points
    * Calculate step sizes
    * Plot INL and DNL
    
    Expected results:
    * DNL < 0.5 LSB (good)
    * INL < 1 LSB (good)
    * No missing codes
  
  - Test 2: Dynamic Testing (FFT)
    
    Setup:
    * Input: Sine wave at frequency f_in
      - Choose: f_in = f_s / 17.3 (avoid coherent sampling issues)
      - If f_s = 10 MS/s, then f_in ≈ 578 kHz
      - Amplitude: 90% of full scale (avoid clipping)
    
    * Capture: 4096 or 8192 samples
    * Export to file
    * Post-process with FFT (Python/MATLAB or LTspice FFT)
    
    Measurements from FFT:
    * Fundamental power (at f_in)
    * Noise floor
    * Harmonic distortion (2×f_in, 3×f_in, etc.)
    * SFDR: Largest spur relative to fundamental
    
    Calculate:
    * SNDR from FFT
    * ENOB = (SNDR - 1.76) / 6.02
    * For 4-bit: Ideal ENOB = 4, typical real = 3.5-3.8
  
  - Test 3: Conversion Time
    * Measure time from sample to valid output
    * Should be N+1 clock cycles (5 for 4-bit)
    * Verify timing
  
  - Results summary table:
    | Specification | Target | Achieved | Status |
    |---------------|--------|----------|--------|
    | Resolution | 4 bits | 4 bits | ✓ |
    | DNL (max) | <1 LSB | __ LSB | ☐ |
    | INL (max) | <1 LSB | __ LSB | ☐ |
    | ENOB | >3.5 bits | __ bits | ☐ |
    | SNDR | >22 dB | __ dB | ☐ |
    | Conversion time | 500 ns | __ ns | ☐ |
    | Power | <1 mW | __ mW | ☐ |

☐ 8:45-9:00: Analysis
  - Compare to specifications
  - Identify performance bottlenecks
  - Plan improvements for tomorrow
```

**Documentation (9:00-9:30 PM)**

```
☐ Lab journal: Complete characterization
☐ Plots: INL, DNL, FFT spectrum
☐ Performance summary table
☐ Commit test results
```

**Total Time Today:** 4 hours

---

#### **Day 50 - Friday, March 21, 2026**

**Morning Session (6:00-7:30 AM) - 1.5 hours**

```
☐ 6:00-7:30: Comprehensive Review
  - Review complete SAR ADC design
  - Check each component:
    * Sample-and-hold: Working properly?
    * Comparator: Fast enough? Low offset?
    * DAC: Linear? Good settling?
    * Logic: Correct sequencing?
  
  - Identify weak points:
    * Where is performance limited?
    * What causes non-linearity?
    * What adds noise?
  
  - Plan optimizations:
    * Component improvements
    * Timing adjustments
    * Power optimization
  
  - Solve problems:
    * Johns & Martin Ch 11 problems on SAR ADCs
    * Focus on design calculations
```

**Evening Session (7:00-9:00 PM) - 2 hours**

```
☐ 7:00-8:45: Optimization and Improvements
  - Based on characterization, improve design:
    
    1. If DNL/INL poor:
       * Check capacitor matching
       * Increase unit capacitor size (better matching)
       * Consider split-capacitor array
       * Verify settling time adequate
    
    2. If ENOB low:
       * Reduce comparator offset (better input pair matching)
       * Reduce noise (larger capacitors, lower bandwidth)
       * Check for kickback issues
       * Improve reference voltage stability
    
    3. If too slow:
       * Increase comparator speed (more current)
       * Reduce DAC settling time (lower resistance)
       * Optimize clock frequency
    
    4. If power too high:
       * Reduce comparator bias current
       * Use asynchronous SAR (variable conversion time)
       * Minimize unnecessary switching
  
  - Re-run characterization:
    * Verify improvements
    * Document changes
    * Update performance table
  
  - Final optimization:
    * Balance power, speed, accuracy
    * Make design trade-offs explicit
    * Choose operating point

☐ 8:45-9:00: Week 8 Summary
  - Summarize SAR ADC design experience:
    * Designed complete 4-bit SAR ADC
    * Learned capacitor DAC design
    * Understood SAR algorithm deeply
    * Performed complete characterization
    * Achieved ENOB = __ bits
  
  - Prepare for weekend documentation
```

**Documentation (9:00-9:30 PM)**

```
☐ Week 8 summary document
☐ Optimization log with before/after
☐ Final performance specifications
☐ Prepare for weekend major documentation
☐ Commit final SAR ADC design
```

**Total Time Today:** 4 hours

---

#### **Day 51 - Saturday, March 22, 2026**

**Major Documentation Day (9:00 AM - 6:00 PM) - 8 hours**

```
☐ 9:00-12:00: Complete SAR ADC Design Report
  - Create comprehensive professional document:
  
  # 4-bit Successive Approximation ADC Design
  
  ## Executive Summary
  - Designed complete 4-bit SAR ADC from ground up
  - Achieved [X] ENOB with [Y] mW power consumption
  - Sampling rate: [Z] MS/s
  - Technology: Behavioral/1.8V CMOS
  
  ## Architecture Overview
  - Block diagram with signal flow
  - Description of each block
  - Design choices explained
  
  ## Component Design
  
  ### 1. Sample-and-Hold
  - Circuit schematic
  - Design equations
  - Performance: acquisition time, droop rate
  
  ### 2. Capacitor DAC
  - Binary-weighted capacitor array
  - Unit capacitor: 100 fF
  - Total capacitance: 1.5 pF
  - INL/DNL analysis
  
  ### 3. Comparator
  - StrongARM latch topology
  - Delay: [X] ns
  - Offset: [Y] mV
  - Power: [Z] µW
  
  ### 4. SAR Logic
  - Algorithm description
  - Timing diagram
  - State machine (if applicable)
  
  ## System Integration
  - Complete schematic
  - Timing analysis
  - Critical paths identified
  - Clock distribution
  
  ## Characterization Results
  
  ### Static Performance
  - DNL: max = __ LSB (plot included)
  - INL: max = __ LSB (plot included)
  - No missing codes verified
  
  ### Dynamic Performance
  - FFT spectrum (plot)
  - SNDR: __ dB
  - ENOB: __ bits
  - SFDR: __ dB
  - THD: __ dB
  
  ### Timing and Power
  - Conversion time: __ ns
  - Sampling rate: __ MS/s
  - Power consumption: __ mW
  - Energy per conversion: __ pJ
  
  ## Performance Summary
  [Complete table comparing targets vs achieved]
  
  ## Design Insights
  1. [Key learning about capacitor matching]
  2. [Insight about comparator design]
  3. [Understanding of DAC settling]
  4. [Trade-offs in SAR design]
  
  ## Challenges and Solutions
  1. **Challenge:** [Specific issue]
     **Solution:** [How solved]
     **Learning:** [What learned]
  
  ## Future Improvements
  - 10-bit version with split-capacitor array
  - Monotonic switching for power reduction
  - Asynchronous operation for variable conversion time
  - On-chip calibration for INL/DNL
  
  ## References
  - Textbooks used
  - Papers referenced
  - Application notes
  
  ## Appendices
  - Complete schematics
  - Simulation settings
  - Post-processing scripts
  - Raw data
  
  - Export as PDF: "4-bit SAR ADC Design Report"
  - This is portfolio piece #6

☐ 12:00-1:00: Lunch

☐ 1:00-4:00: Expand to 10-bit Design (Conceptual)
  - Don't implement full 10-bit, but plan it:
    
    1. Calculate requirements:
       * Unit capacitor: Need better matching
         - 10-bit: 1024 levels → <0.5 LSB INL → <0.05% matching
         - Implies larger unit cap: ~500 fF to 1 pF
       * Total capacitance: (2^10 - 1) × C_unit = 1023 × C_unit
         - With split array: Much reduced
       * Reference voltage distribution
       * Comparator offset: < LSB/2 = V_ref/2048
    
    2. Split-capacitor array design:
       * MSB array: 5 bits (C to 16C)
       * LSB array: 5 bits (C to 16C)  
       * Bridge capacitor: C
       * Total: 63C (vs 1023C for non-split!)
       * Reduction: ~16× less capacitance
    
    3. Switching scheme options:
       * Conventional (up-down switching)
       * Monotonic (only up switching - from paper)
       * VCM-based (charge-sharing reduction)
       * Compare power consumption of each
    
    4. Design challenges at 10-bit:
       * Matching: Need layout techniques
       * Settling: More capacitance = longer settling
       * Comparator: Lower noise, lower offset
       * Reference: Very stable required
    
    5. Create scaling analysis:
       | Parameter | 4-bit | 10-bit | Scaling Factor |
       |-----------|-------|--------|----------------|
       | # Capacitors | 15 | 1023 → 63 (split) | 4.2× |
       | Total C | 1.5 pF | ~50 pF | 33× |
       | Comparator offset | <100 mV | <0.8 mV | 125× better |
       | Matching | 10% | 0.05% | 200× better |
       | Conversion time | 500 ns | 1.1 µs | 2.2× |
    
    6. Document 10-bit design plan:
       * Block diagram
       * Component specifications
       * Expected performance
       * Challenges and mitigation strategies
       * This prepares for paper recreation next week

☐ 4:00-6:00: Video Content Creation
  - Edit video: "Designing a SAR ADC from Scratch"
  
  - Video structure (18-22 min):
    1. Intro (0:00-1:30):
       * What is SAR ADC?
       * Why it's popular
       * What we'll build
    
    2. Binary Search Algorithm (1:30-4:00):
       * Visual explanation
       * Step-by-step example
       * Why efficient
    
    3. Capacitor DAC (4:00-8:00):
       * Binary-weighted array
       * Charge redistribution
       * Simulation demonstration
       * INL/DNL testing
    
    4. Complete SAR System (8:00-13:00):
       * Integration of all blocks
       * Timing diagram explained
       * Full conversion shown in simulation
       * Sample input waveforms
    
    5. Characterization (13:00-17:00):
       * DNL/INL results
       * FFT analysis shown
       * ENOB calculation
       * Performance discussion
    
    6. Design Insights (17:00-20:00):
       * Key challenges
       * Trade-offs made
       * What I learned about data converters
    
    7. Outro (20:00-21:00):
       * Week 9 preview: Advanced layout
       * Links to design files
       * Encourage questions
  
  - Include:
    * Live simulation clips
    * Annotated schematics
    * FFT plots
    * Before/after optimization comparison
  
  - Export: week08_sar_adc_design.mp4
```

**Evening (6:00-8:00 PM)**

```
☐ 6:00-7:00: GitHub Major Update
  - Create /projects/sar-adc-4bit/
    * README with complete description
    * /schematics (all LTspice files)
    * /results (characterization data)
    * /documentation (design report PDF)
    * /analysis (DNL, INL, FFT scripts if used)
  
  - Update main README:
    * Week 8 complete: SAR ADC designed
    * Link to full project
    * Performance highlights

☐ 7:00-8:00: Community Engagement
  - Reddit major post in r/chipdesign:
    "Designed a complete SAR ADC from ground up (4-bit)"
    
    Include:
    * Block diagram
    * Performance summary (ENOB, DNL, INL)
    * FFT spectrum
    * Link to GitHub with full documentation
    * Offer to answer questions
  
  - Twitter thread:
    "Week 8: Designed a complete SAR ADC