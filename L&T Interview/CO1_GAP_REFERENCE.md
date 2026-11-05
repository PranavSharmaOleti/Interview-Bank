# CO1 GAP REFERENCE CARD - L&T GET Interview Bank

## THE PROBLEM
Bank has 233 questions but answers frame for academic exam, not EPC interview.
**0% of answers systematically include site execution, cost, or safety framing.**

## THE FOUR GAPS

### GAP 1: SITE EXECUTION LENS (HIGHEST PRIORITY)
**What's missing:** Every technical answer should connect to how it plays out on an EPC project site.
- **Fix:** Add "How does this play out on site?" push/trap to all [H] questions
- **Example:** Q1 SOM - instead of just formula, add: "On site, if you get this wrong, the rod yields and the machine fails."

### GAP 2: COST-CONSCIOUSNESS LENS
**What's missing:** L&T is EPC; answers should address cost trade-offs.
- **Fix:** Add cost justification push/trap to [H] in files 01, 03, 05, 06
- **Example:** Q5 SOM - FoS = 1.5 per IS 800; choosing 2.0 adds 15% material cost for no benefit.

### GAP 3: SAFETY CULTURE CONNECTION
**What's missing:** Safety not just in file 00; must connect to technical answers.
- **Fix:** Add safety-focused push/trap to [H] in files 01, 03, 05, 06, 07, 08
- **Example:** Q1 SOM - "20% margin before yielding keeps us out of accident reports."

### GAP 4: CALCULATION [H] QUESTIONS WITHOUT CO1 FRAMING
**What's missing:** Several [H] are pure CO2 (derivations/numericals) without plain-words lead-in.
- **Fix:** Rewrite to lead with physical explanation, then formula as tool
- **Affected:** File 01 Q7, Q14, Q15; File 04 Q10

## RESTRUCTURED FORMAT (Per [H] Question)

```
### Q#. <question> [H]

**A:** <Answer leads with physical explanation, 2-3 sentences.
       Key result first, then mechanism, then why it matters in practice.

**Push:** <single most likely follow-up> [1-2 sentences]

**Trap:** <most common wrong answer> [1 line]

**What they're really testing:** <one line - intent>
```

## IMMEDIATE TODO LIST

```
[1] Add "Site Perspective" push/trap to all 155 [H] questions    ...P0
[2] Add "Cost-Consciousness" lens to [H] in files 01,03,05,06    ...P1
[3] Add "Safety Culture" connection to [H] in files 01,03,05,06,07,08 ...P2
[4] Rewrite calculation-heavy [H] questions (Q7,Q14,Q15 in 01; Q10 in 04) ...P3
[5] Create "L&T EPC" version of bank - parallel, not modifying ...P4
[6] Audit file 00 (Spine) - decide if CO1 technical fundamentals should interleave ...P5
[7] Add CO1/CO2/CO3 tagging to every question for future ref ...P6
```

## CO1 TOPICS THINLY COVERED (Add as new [H] questions)

| Topic | Missing From |
|-------|-------------|
| Physical meaning of principal stress/strain | 02, 03, 07 |
| Entropy - physical meaning | All except 02 |
| Exergy/availability & plant efficiency | All except 02 |
| NPSH/cavitation mechanism | 01, 05 |
| Design process: how you actually work | 01, 06 |
| Standard selection logic (bearings/seals/couplings) | 03, 04 |
| Tolerance stack-up: RSS vs worst case | 05, 07 |
| Motor selection logic (pump/fan/compressor/crane) | 05 |
| VFD: affinity laws, harmonics, bearing currents | 05, 06 |
| Fit selection: clearance/transition/interference, IT grades | 05, 06 |
| GD&T: why it exists beyond +/- tolerancing | All technical |
| Surface finish: Ra value meaning, not just symbol | 04, 05 |

## VALIDATION CHECKLIST (Per Question)

- [ ] Answer leads with physical explanation BEFORE any formula
- [ ] Push has natural follow-up testing understanding
- [ ] Trap identifies most common misconception
- [ ] "What they're really testing" line present (one sentence)
- [ ] Answer includes site execution, cost, OR safety framing
- [ ] No derivation longer than 3 lines
- [ ] Numerical examples work but aren't the focus
- [ ] Units stated correctly and consistently
- [ ] Standard values from template used (E=200 GPa, g=9.81, etc.)
- [ ] ASCII only - no LaTeX, no unicode math, no emoji