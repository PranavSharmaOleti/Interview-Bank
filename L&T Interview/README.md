# L&T Interview Bank — Mechanical Engineering Question Bank

> A structured, GATE-aligned mechanical engineering interview question bank for core company interviews (automobiles, petrochem, construction, power, heavy engineering). Built by a mechanical undergrad (2027 pass-out) who sat an L&T GET interview and realised a 250-question bank was insufficient because it lacked CO1 fundamentals and was too narrow.

## Overarching Vision

Most interview prep material falls into one of two traps:

1. **Too narrow** — questions lifted from one company's past papers, useless the moment the panel changes.
2. **Too shallow** — derivations and formulas without the physical meaning, definitions, and "why it matters" that panels actually probe at CO1 (course outcome 1) level.

This bank aims for **broad, industry-agnostic fundamentals**. Every question is framed so it transfers across employers: the same thermodynamics, SOM, fluids, or machine design fundamentals are what automobile, petrochem, construction, and power panels all test — only the application changes. The bank targets **400–600 questions** spread across the subjects a mechanical undergrad is actually examined on, in a format a candidate can speak in 30–60 seconds.

The design philosophy:

- **Fundamentals first.** Definitions, physical meaning, and "why it matters" before derivations. A panel can tell in ten seconds whether you understand the concept or memorised a formula.
- **Speakable answers.** Hard cap ~90 words per answer. If you cannot say it in a minute, you do not understand it yet.
- **Tagged by yield.** `[H]` asked very commonly, `[M]` asked regularly, `[L]` occasional — so a candidate with limited time can prioritise.
- **Trap-aware.** Each question names the common misconception panels use to filter out rote learners.
- **Standard values consistent.** E steel 200 GPa, E aluminium 70 GPa, G steel 80 GPa, Poisson 0.3, steel density 7850, water 1000, oil 900–950, g = 9.81, π = 3.1416, Re laminar < 2300, turbulent > 4000.
- **ASCII only.** No LaTeX, no unicode math symbols, no emoji — so answers paste cleanly into any notes app or flashcard tool.

## Repository Structure

```
L&T Interview/
├── ver1_bank/          # Original 9-file bank (the starting point)
│   ├── 00_The_Spine_Behavioural_and_LT.md
│   ├── 01_SOM_and_Vibrations.md
│   ├── 02_Thermodynamics_and_IC_Engines.md
│   ├── 03_Fluids_and_Heat_Transfer.md
│   ├── 04_Manufacturing_Welding_NDT.md
│   ├── 05_Machine_Design.md
│   ├── 06_ToM_and_Engineering_Mechanics.md
│   ├── 07_CAD_GDNT_FEA.md
│   ├── 08_Electrical_for_Mechanics.md
│   └── _BRIEF_TEMPLATE.md
│
└── ver2_bank/          # GATE-aligned bank, 457 unique questions, 10 subjects
    ├── 01_Thermodynamics_and_Heat_Engines.md
    ├── 02_Strength_of_Materials.md
    ├── 03_Fluid_Mechanics_and_Piping.md
    ├── 04_Theory_of_Machines.md
    ├── 05_Machine_Design.md
    ├── 06_Engineering_Mechanics.md
    ├── 07_Heat_Transfer.md
    ├── 08_Manufacturing_Welding_NDT.md
    ├── 09_CAD_GDNT_FEA.md
    └── 10_Electrical_Drives.md
```

## Subject Coverage (ver2_bank)

| # | Subject | Questions | Topics |
|---|---------|-----------|--------|
| 01 | Thermodynamics & Heat Engines | 55 | First/second law, entropy, Carnot, cycles, steam properties, boilers, refrigeration, IC engines, Otto/Diesel |
| 02 | Strength of Materials | 49 | Stress/strain, beams, torsion, columns, buckling, fatigue, vibrations, failure theories |
| 03 | Fluid Mechanics & Piping | 36 | Fluid properties, Bernoulli, pipe flow, pumps, turbines, NPSH, cavitation, compressible flow |
| 04 | Theory of Machines | 40 | Mechanisms, kinematics, cams, gears, balancing, governors, vibration isolation |
| 05 | Machine Design | 37 | Design process, shafts, keys, couplings, belts, gears, bearings, springs, fasteners, welded joints |
| 06 | Engineering Mechanics | 40 | FBD, equilibrium, trusses, frames, friction, work-energy, impulse-momentum, kinematics, dynamics |
| 07 | Heat Transfer | 50 | Conduction, convection, radiation, fins, heat exchangers, LMTD, NTU-effectiveness, insulation |
| 08 | Manufacturing, Welding & NDT | 50 | Casting, forming, machining, heat treatment, welding processes, NDT methods, tolerances, GD&T |
| 09 | CAD, GD&T & FEA | 50 | CAD fundamentals, GD&T characteristics, datums, MMC/LMC, tolerance stack-up, FEA workflow, elements, BCs |
| 10 | Electrical & Drives | 50 | AC/DC, three-phase, power factor, transformers, induction motors, VFDs, earthing, protection, cables, switchgear |

**Total: 457 unique questions, zero duplicates.**

## Question Format

Every question follows the same block:

```
### Qn. <Question text> [H|M|L]
**A:** <2-5 sentence answer, key result first>
**Push:** <1-2 sentence follow-up the panel may ask>
**Trap:** <1 line — the common misconception>
**What they're really testing:** <one line — the intent behind the question>
```

- `[H]` high-yield, `[M]` medium-yield, `[L]` occasional
- Answers are speakable in 30–60 seconds (hard cap ~90 words)
- Push questions extend the answer into a deeper probe
- Traps name the misconception that filters rote learners

## How to Use

1. **First pass** — read all `[H]` questions in the subject you are weak in. Say the answer out loud without reading. If you stumble, that is your gap.
2. **Second pass** — attempt the `[M]` questions. Use the Push line as a self-test.
3. **Third pass** — `[L]` questions for breadth and to handle "what if" panels.
4. **Numericals** — work the numeric examples in the answers on paper, not in your head.
5. **Mock panel** — have a peer ask questions from a random subject; answer within 60 seconds.

## Roadmap

- Expand toward 600 questions with deeper coverage of automobile-specific systems (IC engine subsystems, vehicle dynamics, NVH, emissions after-treatment)
- Add a behavioural/spine file (already in ver1) covering L&T-specific and HR rounds
- Add a quick-reference formula sheet per subject
- Add worked numerical problems as a separate file

## Contributing

This is a personal prep bank, but improvements are welcome. If you spot a wrong formula, a missing fundamental, or a better trap, open an issue or PR. Please keep the format, ASCII-only rule, and standard values consistent.

## License

Personal educational use. Share freely, attribute if you can.