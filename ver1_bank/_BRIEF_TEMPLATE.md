# SHARED BRIEF - read this before writing your bank file

You are writing one section of a study bank for a **mechanical engineering undergraduate** who has an
**L&T (Larsen & Toubro) Graduate Engineer Trainee interview TOMORROW**.

- He is a **2027 pass-out, mechanical engineering, on-campus core GET** hire (L&T Ltd, not LTTS).
- The panel is **30-45 minutes**, technical, at **"GATE-lite" depth**: fundamentals from the standard
  mechanical syllabus, occasionally one numerical, plus questions on his project and internship.
- L&T is an EPC/engineering conglomerate: heavy manufacturing, power, project sites, safety culture.
  A mech GET panel asks **core fundamentals**, not coding, not software.
- Only about 8-10 questions are actually traceable to real L&T mechanical interviews. **Do not claim
  any question is "L&T-specific" or "asked at L&T"** unless you are certain. Write these as general
  mechanical-fresher panel questions - which is what they are.
- The candidate's internship (a guided plant visit to BHEL Hyderabad, observation only) is handled
  elsewhere. You do not need to cover it.

## Your deliverable

Write **EXACTLY ONE** file, at the path given in your task prompt. Do not create, edit, or modify any
other file. Do not touch the other bank files. Do not create an index or README.

## Question tags (prefix every question with one)

| Tag | Meaning |
|---|---|
| `[H]` | **Asked very commonly** - shows up in 4+ independent fresher interview accounts. These are must-win. |
| `[M]` | **Asked regularly** - 2-3 accounts. |
| `[L]` | **Occasional** - a single anecdote, but a sensible question an interviewer would ask. |

**Order questions inside every section: all `[H]` first, then `[M]`, then `[L]`.** This order is
deliberate - the candidate reads top-down and stops when he runs out of time, so the top of each
section must be the highest-yield content.

## Exact format for every question

```
### Q1. <the question, phrased the way an interviewer would actually say it> [H]

**A:** <exam-ready answer, 2-5 sentences, plain text. Formulas written inline like sigma = F/A,
tau = T*r/J. State the key result or value first, then why it matters in practice.>

**Push:** <the single most likely follow-up the interviewer would ask, plus its answer - 1-2 sentences.>
Omit the "Push:" line only when there is genuinely no natural follow-up.

**Trap:** <the most common wrong answer, or the misconception the interviewer is testing - 1 line.>
Omit the "Trap:" line when it is not applicable.
```

## Section format

```
## 1. <Section title> - <n> questions

### Q1. ...

...

**What they're really testing:** <one line>
```

End each major section with the "What they're really testing:" line. It tells the candidate the
*intent* of the section, which is what makes the answer stick.

## File header (use this exact structure)

```
# <Subject area> - L&T GET technical interview bank

**Part <N> of 8 | <n> questions | <one-line topic summary>**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly,
[L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you
cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing
recall, they are testing whether you can reason out loud.*
```

## Quality rules (non-negotiable)

1. **Technical correctness first.** If you are not certain of a formula or value, write the general
   principle and the method, and say so in the answer ("the standard value is around...", "you'd
   confirm it in the code"). **NEVER invent a precise number you are unsure of.** A vague correct
   answer beats a confident wrong one.
2. **Use these standard values consistently** across all files:
   E steel 200 GPa | E aluminium 70 GPa | E cast iron 100-120 GPa | G steel 80 GPa | Poisson 0.3
   density steel 7850 kg/m3 | cast iron 7200 | aluminium 2700 | water 1000 | oil 900-950
   1 atm = 1.013 bar | g = 9.81 m/s2 | 1 kW = 1.34 HP | 1 HP = 0.746 kW | pi = 3.1416
   Re: laminar below 2300, transition 2300-4000, turbulent above 4000
   stress-strain mild steel: proportional ~200 MPa, yield ~250 MPa, ultimate ~400-550 MPa
3. **ASCII only.** No LaTeX, no unicode math symbols, no emoji, no arrows. Write `sigma`, `tau`,
   `omega`, `theta`, `->`, `x`, `approx`, `deg C`, `kPa`, `MPa`, `N-m`, `m3/s`, `kg/m3`.
4. **Standards:** you may name `IS 800` (steel structures by limit state), `IS 456` (concrete),
   `IS 2062` (structural steel), `IS 808` (rivets), `IS 1556` (welding electrodes), `IS 3006`
   (mild steel tubes), `ASTM A106` (seamless pipe), `API 5L` (line pipe). **Do not invent clause
   numbers** and do not attribute specific values to a code you are not sure about.
5. **Length:** the "A:" line must be speakable in 30-60 seconds. Hard cap about 90 words. This is a
   spoken interview, not an essay.
6. **Derivations** - when a question classically asks for one ("derive Bernoulli from Euler", "derive
   Euler buckling load", "explain the Rankine cycle", "derive the Lewis equation", "derive bearing L10
   life", "derive the critical insulation radius", "derive natural frequency of an SDOF system"),
   give the **key steps in 3-5 lines**, not a full derivation. Name the starting assumption and the
   final result.
7. **Numericals** - when a question classically expects a number, work it in the answer and show the
   final result, e.g. "a 20 mm dia steel rod under 50 kN -> A = pi/4 x 20^2 = 314 mm2 ->
   sigma = 50000 N / 314 mm2 = 159 MPa".
8. **Self-contained.** Do not tell the reader to look anything up in another file.
9. **Technical only.** No motivational, HR, behavioural, or company-questions content in your file.
   That is handled in a separate part.
10. **Number questions `Q1..Qn` within your own file.** Numbering does not need to be continuous
    across files.

## What makes this bank actually work

The panel is not testing recall. It is testing whether you can **reason out loud** on a subject you
learned two years ago. So every answer should read like something a person would actually say:
first the direct answer, then the mechanism, then why it matters in a plant. Avoid textbook
paragraphs. If a good candidate would say "I remember the number being about 250 MPa for mild
steel, and I would double check it in the handbook - but the key point for us is where that number
sits relative to the ultimate strength", write that kind of answer.

## Report back (under 200 words, nothing else)

- The file path and the exact number of questions written
- The list of your section titles with question counts
- Any syllabus item in your scope you deliberately did **not** cover, and why
- Any place where you stated a number you were not 100% sure of, and what you wrote instead
- Do **not** paste the file contents back.
