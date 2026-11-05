# Your final-year project - what it is, and how to answer it
**Cantilever Bracket | SolidWorks Simulation | 2027 pass-out | 21 Oct 2026**

Everything in this document comes out of your own six SolidWorks Simulation reports (the `.docx`
files in `Project fem/`) and your two repository images. Nothing here is a generic answer. If it
says a number, the number is yours.

---

## 1. What the project actually is, in one paragraph

You took a cantilever bracket and ran it through **three design iterations**, each one a different
SolidWorks **configuration** of the same part, each one a separate Simulation study. You started
with an over-built solid box-section arm (`Parent Model`), hollowed it out with lightening slots
(`Supposedly child`), found that the slots created a stress raiser and that the mesh had gone bad,
and then re-architected the arm as a **triangulated truss** (`Child Reborn`). On the final geometry
you also ran a **Frequency (Modal)**, a **Modal Time History** and a **Linear Dynamic (Harmonic)**
study. Net result: **33.6% of the mass removed**, the reaction force down 24%, the peak stress
still 57 times below yield, and the first natural frequency at 31.9 Hz.

That is a real, respectable engineering loop: **geometry change -> meshing -> analysis -> compare ->
change the geometry again.** It is exactly what a mechanical GET does on a plant job.

---

## 2. The numbers (memorise the bold ones)

| | **Static 1** | **Static 2** | **Static 3** |
|---|---|---|---|
| Configuration | Parent Model | Supposedly child | Child Reborn |
| Geometry | solid box arm | box arm, 2 oval slots | **triangulated truss arm** |
| Mass | 406.23 kg | 321.07 kg | **269.82 kg** |
| Volume | 0.05276 m3 | 0.04170 m3 | **0.03504 m3** |
| Reaction force | 5,534.24 N | 4,699.04 N | **4,196.02 N** |
| Mesh nodes | 1,457,934 | 10,445,156 | **458,961** |
| Mesh elements | 942,318 | 6,889,296 | **241,739** |
| Max aspect ratio | 4.34 | **40,657** | 9.29 |
| % elements AR<3 | 99.8 | 99.3 | 95.2 |
| % distorted elements | 0 | 4.35e-05 | 0 |
| Time to mesh | 1 min 02 s | **44 min 51 s** | 35 s |
| **Max von Mises** | 6.354 MPa | 26.77 MPa | **10.85 MPa** |
| **Max displacement** | 0.122 mm | 0.301 mm | **0.216 mm** |
| Factor of safety on yield | 98 | 23 | **57** |

**Material (identical in all six studies):** Alloy Steel, linear elastic isotropic, von Mises
criterion. E = 210 GPa, nu = 0.28, G = 79 GPa, rho = 7,700 kg/m3, yield 620.4 MPa, tensile
723.8 MPa.

**Loads (identical in all six studies):** `Fixed-1` on 1 face (the mounting face); `Force-1` =
**500 N normal** on 3 faces; `Gravity-1` = 9.81 m/s2 on the whole body; `Distributed Mass-1` =
**5 kg remote mass** on 2 faces.

**Modal (on Child Reborn):** f1 = **31.883 Hz**, f2 = 59.586 Hz, f3 = 81.906 Hz. Mode 1 is
predominantly Z-direction with **41.6% mass participation**, mode 3 is Y-direction with 41.8%.

**Modal Time History:** base excitation of 0.5 in (Y) and -10 in (Z), 1 second -> max von Mises
**53.22 MPa**, max displacement **0.788 mm**.

---

## 3. The engineering story, in plain words - this is what you are actually selling

**Iteration 1 - the parent model was not light, it was over-designed.** A solid box-section arm
406 kg and 3,981 N of self-weight, carrying only 6.35 MPa of von Mises stress against a 620 MPa
yield. A factor of safety of 98 means the part was carrying nowhere near its capacity. The mass was
not doing any work.

**Iteration 2 - cut the weight, and the cut-outs fought back.** Lightening slots in the web took
21% of the mass out. But the peak stress went up **4.2x** (6.35 -> 26.77 MPa) and the tip
deflection up **2.5x** (0.122 -> 0.301 mm). Look at where the hot spot moved: it is not at the
mount any more, it is at the **end of the lightening slot** near the free end. That is a stress
concentration, and it is the classic failure of a slotted design - a slot end is a hole with a
sharp end. On top of that the mesh had fallen apart: max aspect ratio **40,657**, 6.9 million
elements, 45 minutes to mesh. Those numbers I do not trust, and I said so.

**Iteration 3 - stop subtracting, start rearranging.** I re-architected the arm as a **triangulated
truss**: material moved out of the web and into the top and bottom chords, with a zig-zag of
diagonal members between them. Now the load path is a truss, the bending is carried by the chords
where the section modulus is highest, and there are no long slot terminations to act as stress
raisers. Result: peak stress **down 2.4x** from iteration 2 (26.77 -> 10.85 MPa), deflection **down
28%** (0.301 -> 0.216 mm), and another 16% of the mass gone (321 -> 270 kg). The hot spot moved to
where it *should* be - the mount and the top chord right next to it, which is where the bending
moment is maximum on a cantilever.

**The honest conclusion.** The final part is **33.6% lighter** and its own load is **24% lower**,
but per unit of load it is **about 2.3x more flexible and 2.3x more highly stressed** than the
parent. That is not a failure - that is the trade curve of lightening. I paid 2.3x in stiffness to
buy 34% in mass, and at 620 MPa yield the final part still has a factor of safety of 57, so the
parent's extra 136 kg was carrying nothing. **The right question is not "did the numbers go down",
it is "did I remove material that was not working, without moving the load path into a worse
place".** By that measure iteration 3 wins and iteration 2 lost.

---

## 4. Answers to the questions I asked you (`00_START_HERE_TONIGHT.md` section 3)

### Q1. Topic / title
**The idea:** a cantilever bracket - a mounting plate with a bolted hole, and an arm cantilevered off
it - taken through three design iterations with FEA at each step.
**How to say it:** "My final-year project was a cantilever bracket, done as a design-iteration study.
I built the geometry in SolidWorks, ran static structural analysis on it, changed the geometry based
on what the analysis told me, and ran it again. Three iterations, and I kept the numbers from every
one so I could compare them properly."
**If they push:** "Why a bracket?" - "Because a cantilever is the simplest structure that still has
all the interesting failure modes: bending, shear, stress concentration at the fixed end, and
dynamic behaviour. It was a good teaching vehicle."
**Do not say:** "I designed a bracket for industry" - it was an assignment-driven study.

### Q2. Problem it solves
**The idea:** the parent model was massively over-designed; the goal was to remove dead mass without
losing structural margin.
**How to say it:** "The starting point was a solid-section cantilever arm that was far stronger than
it needed to be - 6.35 MPa of stress against a 620 MPa yield. So the question I set myself was:
how much of that material is actually working, and can I take it out without the load path
getting worse? I ended up removing about a third of the mass."
**If they push:** "Where did you use the saved mass?" - "I did not design to a mass budget, so
honestly nowhere - the point was the method, not a product."

### Q3. Your specific role
**The idea:** it was his own project, solo - geometry, meshing, setup, solving, reading results.
**How to say it:** "It was a solo project. I did the whole loop myself - the CAD modelling and the
SolidWorks configurations, the study setup, the meshing and the mesh controls, running the
solver, and reading the results back and deciding what to change. The SolidWorks reports in my
folder are the raw output from those runs."
**If they push:** "Any help?" - "The SolidWorks Simulation guidance for setting up the modal and
time-history studies I worked through myself."

### Q4. Tools / software used
**The idea:** SolidWorks CAD + SolidWorks Simulation. Four study types.
**How to say it:** "SolidWorks for the CAD, and SolidWorks Simulation for the analysis, because
keeping them in the same environment meant the geometry changes and the study setup stayed in sync
as I iterated. I used four study types: Static Structural on all three configurations, then
Frequency (Modal), Modal Time History and Linear Dynamic (Harmonic) on the final geometry."
**If they push:** "Why not ANSYS?" - "Because the design started in SolidWorks and for this problem
- linear static and modal on a part of this size - SolidWorks Simulation was sufficient. If I were
doing contact, nonlinearity or a large fatigue life I would have taken the geometry into ANSYS."

### Q5. The one calculation or decision you personally owned
**The idea:** the decision that iteration 2 failed and iteration 3 was the answer - and the
load-case reconciliation.
**How to say it:** "Two things I owned. The first was the decision to throw out iteration 2: its
peak stress had gone up 4.2x and it was sitting at the end of the lightening slot, which told me
the slots themselves were the problem, not just the material I had removed. So I stopped subtracting
material and changed the architecture to a truss. The second was noticing that the reaction force the
solver reported - 5,534 N on the parent, 4,196 N on the final - was not the 500 N load I had
applied. I reconciled it: it is the part's own weight, plus 500 N on each of the three loaded
faces, plus the 5 kg remote mass. That told me the bracket was carrying mostly itself, and that
was the single most useful thing I learned in the whole project - lightening the part cuts the
load directly, and I would not have seen that from the stress plots alone."
**If they push:** "How did you check it?" - "I checked it across all three studies - 406 kg gives
3,981 N, 321 kg gives 3,146 N, 270 kg gives 2,644 N, and adding the same 1,549 N of external load
reproduces the three reported reactions to within a newton."

### Q6. Key numbers you can defend
**The idea:** the six numbers below. Everything else is in the reports.
**How to say it:** "Mass went from 406 kg to 270 kg - that is 33.6% off. Reaction force fell from
5,534 N to 4,196 N. Peak von Mises went 6.35, 26.77, 10.85 MPa across the three iterations.
Tip deflection went 0.122, 0.301, 0.216 mm. First natural frequency 31.9 Hz with 41.6% mass
participation in the vertical. And the mesh on the final model is 459 thousand nodes with a max
aspect ratio of 9.3 and zero distorted elements."
**If they push:** any of them - you have the report behind every one.
**Do not say:** any number from the two GitHub images (see section 6, item 2).

### Q7. Assumptions you made
**The idea:** linear elastic, no contact, fixed base, gravity as a body load, remote mass as a lumped
mass, and the biggest one - that the load case is representative.
**How to say it:** "The material was linear elastic isotropic alloy steel, the base was fully fixed,
and I did not model contact anywhere, so I assumed the clearances in the truss are enough that the
members do not touch. The load case is a 500 N normal load on the end faces plus gravity plus a 5 kg
remote mass. The assumption I am least comfortable with is that this load case is representative of
how the part is actually used - that is the one I would want to test first."
**If they push:** "What would you change?" - "A real duty cycle, and a bolt preload at the mount
rather than a fully fixed face."

### Q8. The hardest part / what went wrong
**The idea:** iteration 2 - the mesh and the stress concentration.
**How to say it:** "Iteration 2 was the hard one. The lightening slots took 21% of the mass out, but
the peak stress went up more than four times, and when I looked at where, it was not at the mount
- it was at the end of the slot near the free end. And the mesh on that model had a max aspect ratio
of 40,657 with 6.9 million elements and 45 minutes of meshing. So I had two problems at once: the
design was creating a stress raiser, and I could not trust the numbers. I rebuilt the geometry as a
truss and re-meshed it properly - 459 thousand nodes, aspect ratio 9.3, 35 seconds."
**If they push:** "How did you know it was the slot?" - "Because the hot spot moved to the slot
termination and stayed there, and because the geometry change that removed the slots entirely -
replacing them with triangulated web members - moved the hot spot back to the mount, which is
where the bending moment actually peaks."

### Q9. How you validated the result
**The idea:** three checks - load reconciliation, eigenfrequency consistency across studies, and
geometry/mesh quality.
**How to say it:** "Three ways. First I reconciled the loads - I can reproduce the three reported
reaction forces from the mass, the 500 N per face and the 5 kg remote mass to within a newton, which
tells me the model is loading what I think it is loading. Second, the eigenfrequencies came out
31.883, 32.045 and 31.903 Hz in three different studies with different load definitions - and
eigenfrequency does not depend on load in a linear analysis, so that consistency is a real check
that the stiffness and mass are right. Third, I looked at where the stress was, not just how big it
was: the hot spot has to be where the physics says it should be. In the final truss it is at the
mount, on a cantilever, which is correct."
**If they push:** "Would you do a physical test?" - "Yes - that is the honest limitation, this is
simulation only. The first physical check I would run is a static load test at the free end with a
deflection gauge, compared against the FEA prediction of 0.216 mm."

### Q10. What you'd redesign and why
**The idea:** chords thicker, diagonals thinner; add fillets at the mount; then a proper comparison
load case and a mesh convergence study.
**How to say it:** "Three things. First, rebalance the truss - move a bit more material into the two
chords and take it out of the diagonals, because the bending is carried by the chords and the
diagonals are mostly carrying shear. Second, put a fillet at the transition where the arm meets the
mounting plate, because that is where my peak stress is and a sharp corner is a stress raiser.
Third, and this is the one I would do first if I had another week: rerun all three geometries with
gravity switched off and the same 500 N on each, because with gravity on, the load is dominated by
self-weight and I am partly measuring the mass again instead of comparing the structures."
**If they push:** "Why is that last one the first one?" - "Because everything else is tuning on top
of a comparison that is not quite clean. Fix the measurement before you optimise against it."

### Q11. One thing you'd do differently
**The idea:** mesh convergence, and not trusting a single mesh.
**How to say it:** "I would have done a proper mesh convergence study on the final model - run the
same load case at coarse, medium and fine element sizes and show that the peak stress converges.
Right now I have one mesh with good quality numbers, but good quality is not the same as converged.
I also would have exported the key plots properly - the two images in my GitHub repo are from an
earlier iteration and do not match my final reports."

---

## 5. The follow-ups a mechanical GET panel will actually ask

**1. Why a truss? Why not just a thinner solid plate?**
"Because the load is bending, and bending is carried by the section modulus - roughly the distance
from the neutral axis to the outer fibre times the thickness. In a solid box I was paying for
material right through the middle of the section, which does almost nothing for bending. A truss puts
the material where the lever arm is, and the diagonals deal with the shear. For the same mass you
get a much bigger section modulus, and the section modulus is what sets the bending stress."

**2. Why did the stress go UP if the part is better?**
"It did go up in absolute terms - 6.35 to 10.85 MPa. But the load went down 24% at the same time,
because I removed a third of the mass and this part was carrying mostly itself. Per newton of load
the stress is about 2.3x worse, and I am not going to pretend that is free. The justification is that
the parent was at a factor of safety of 98 against yield - it was carrying nothing - and the final
version is still at 57. I removed 136 kg of material that was not doing any work. If the duty cycle
were severe enough that stiffness mattered more than mass, the parent would be the right answer, and
I would want to know the duty cycle before I claimed this is a win."

**3. What is a von Mises stress and why use it?**
"It is a scalar that combines the three normal stresses and the three shear stresses into one
equivalent value, so you can compare a general 3D stress state against a simple uniaxial yield
criterion. For a ductile material like steel, yielding is governed by shear distortion, not by
extension, and von Mises captures that. Tresca is the older, more conservative alternative - it says
the maximum shear stress must not reach the shear yield strength. Von Mises is the standard default
in SolidWorks and it is what the yield-strength line in my legend is checking against."

**4. Your peak stress is 10.85 MPa against a 620 MPa yield. Is that even interesting?**
"Honestly, no - and that is the point I took from the project. In absolute terms all three designs
are enormously over-strength, so the stress plot is not where the design decision lives. The decision
lives in the trade between mass and stiffness, and in whether the stress is where the physics says it
should be. The number that matters more is the deflection, because 0.216 mm on a part this size is
a tolerance question, not a strength question."

**5. Why does your first mode have 41.6% participation in one direction?**
"Because that is the global bending mode of the arm. The bracket is a cantilever - mass is
concentrated at the mounting end and the far end moves. Mode 1 at 31.9 Hz is the first vertical
bending mode, and 41.6% participation in Z means about 42% of the effective mass moves with it. The
remaining participation is spread across the higher modes, which is normal for a structure this
complex - you do not get one clean mode that captures all the mass."

**6. What is modal time history for, and why did you excite it 10 inches?**
"Modal time history superimposes the mode shapes to give you a time-domain response to a known
excitation - so you can see what actually happens over time, not just the worst shape. The 10 inch
base excitation is deliberately severe; it is not a service condition, it is there to show the solver
working and to make the response visible. That is why it gives 53 MPa and 0.788 mm, which are far
higher than the static case. If I redid it I would use a realistic input spectrum."

**7. Your harmonic sweep goes to 100 kHz on a part whose first mode is 31.9 Hz. Why?**
"That was a default sweep range and it is not a meaningful one for this part - the response above
about 200 Hz is essentially zero because there is no energy up there and no excitation. The
interesting band is around 30 to 100 Hz, where the first three modes live. If I were doing it
properly I would sweep only across the modes and look at the amplification at resonance."

**8. What is mesh aspect ratio and why did yours matter?**
"Aspect ratio is the ratio of an element's longest dimension to its shortest. A very high aspect
ratio means the element is a long thin sliver, and slivers are numerically bad - they behave like
one-dimensional beams, so they stiffen artificially and they carry stress that is really a mesh
artefact rather than the real stress. Iteration 2 had a max aspect ratio of 40,657, which means
some elements were effectively zero-thickness. On the final model it is 9.3 with 95% of elements
under 3, which is a sane mesh."

**9. How do you know the mesh is fine enough?**
"Quality numbers tell you the mesh is well-shaped; they do not tell you it is converged. Convergence
needs the same load case at three element sizes and a comparison of the answer, which I did not do.
That is a gap I know about."

**10. What is the difference between static, modal and dynamic analysis?**
"Static assumes the load is applied slowly enough that inertia does not matter - the structure is in
equilibrium at every instant. Modal tells you the natural frequencies and mode shapes, the
properties of the structure itself with no load needed. Dynamic superimposes those modes against a
time-varying excitation to get the actual response over time. Static asks 'where does it deflect',
modal asks 'how does it want to move', dynamic asks 'what does it actually do when you shake it'."

**11. Why did you use configurations instead of three separate parts?**
"Configuration is the right tool for exactly this. One part file, one set of study definitions, and
I swap the geometry by changing configuration. The load case, the material and the mesh controls
stay identical across all three, so the comparison is clean and there is no risk of me forgetting to
change something between runs."

**12. Your mirror feature - what were you mirroring?**
"The arm is symmetric about its vertical centre plane, so I modelled half and mirrored it. It is a
standard way to cut model size, and it doubles as a check: if the mesh was poor at the mirror seam,
you see it immediately."

**13. What did you actually learn from this project?**
"To read an FEA result instead of just reporting it. Before this project I would have taken the
maximum stress number and moved on. After it, I look at where the hot spot is and ask whether that
is where the physics puts it - and when the answer is no, I know the design is wrong, not just the
number. The second thing is the load case: I went in thinking a 500 N load was the story, and the
output taught me the part was carrying itself. You do not get that from a textbook."

**14. If you had one more week, what would you do?**
"Three things, in order. A clean comparison run - gravity off, identical 500 N on all three
geometries - so I could compare the structures rather than the masses. A mesh convergence study on
the final truss. And a physical load test on one of them, because I have not actually validated any
of this against reality, and a simulation I have not checked against a test is an argument, not a
result."

---

## 6. The five things that are weak in this project. Own them.

**1. Your GitHub README overclaims.** It says "significantly less stressed, less deformed". The
reports say the opposite: peak stress went 6.35 -> 26.77 -> 10.85 MPa and deflection 0.122 ->
0.301 -> 0.216 mm. What IS true: **mass -33.6%, reaction -24%, peak stress down 2.4x from
iteration 2 to iteration 3, and the mesh went from genuinely broken to sane.** Fix the README to say
that, or you will get caught. You cannot let a written claim contradict your own data.

**2. Your two GitHub images are from a different run than your reports.** In those images the yield
strength reads 620,422,000,000 - that is 620 GPa, a thousand times the 620.4 MPa in your reports -
and the stresses are a thousand times larger too. So they are not the same analysis. I have pulled
the correct plots out of your reports into `Project fem/README_images/` (10 files, renamed
01-10 in iteration order). **Replace the two images in your repo with those.** Use 01/04/07 for the
three geometries and 02/05/08 for the three stress plots.

**3. Gravity dominates your load case, so your three results are not a clean comparison.** The
bracket carries 4,196 N of which about 3,981 N is its own weight in iteration 1. With gravity on,
"solving" the part is partly measuring its mass. The fix is one extra study per geometry with
gravity off and the same 500 N applied - three extra solves.

**4. One mesh per design, no convergence study.** You have good quality numbers, which is not the
same as a converged answer. Say so.

**5. No physical validation.** It is a simulation study. Say that first, before they point it out.

---

## 7. The eight numbers to memorise

1. **406 kg -> 270 kg** (mass, -33.6%)
2. **5,534 N -> 4,196 N** (reaction force, -24%)
3. **6.35 / 26.77 / 10.85 MPa** (peak von Mises, iterations 1 / 2 / 3)
4. **0.122 / 0.301 / 0.216 mm** (max tip deflection)
5. **31.9 Hz** (first natural frequency, 41.6% Z participation)
6. **459,000 nodes, aspect ratio 9.3** (final mesh) versus **10.4 million nodes, aspect ratio 40,657**
   (iteration 2 - the broken one)
7. **620.4 MPa yield, 210 GPa, nu 0.28** (the material)
8. **19 operations** - no wait, that is the BHEL rotor. **500 N on 3 faces + gravity + 5 kg remote
   mass** (the load case)

---

## 8. The 30-second and 90-second versions

**30 seconds:** "My project was a cantilever bracket taken through three design iterations in
SolidWorks Simulation. I started with an over-designed solid arm, hollowed it out with lightening
slots, found that the slots acted as a stress raiser and the mesh had gone bad, and then
re-architected the arm as a triangulated truss. End result: a third of the mass removed, the
reaction force down 24%, peak stress 10.85 MPa against a 620 MPa yield, and a first natural
frequency of 31.9 Hz."

**90 seconds:** "It was a cantilever bracket - a mounting plate with a bolt hole and an arm
cantilevered off it - and I ran it as a design-iteration study. The workflow was SolidWorks
configurations holding three geometry variants, a Simulation study on each, and then I compared the
numbers and changed the geometry again. The parent model was a solid box section, 406 kg, and it
was carrying only 6.35 MPa of stress against a 620 MPa yield - a factor of safety of 98, so most
of that mass was doing nothing. My second iteration cut 21% of the mass with lightening slots, and
it backfired: the peak stress went up more than four times, and the hot spot had moved to the end
of the slot, which is a stress concentration. The mesh had also gone bad - aspect ratio 40,657 and
45 minutes to mesh - so I did not trust those numbers either. So the third iteration was a
re-architecture: I turned the arm into a triangulated truss, moving the material out of the web
and into the chords. That dropped the peak stress by 2.4x from the slotted version, cut the
deflection 28%, and took another 16% of the mass out. Final numbers: 270 kg, reaction 4,196 N,
peak von Mises 10.85 MPa, tip deflection 0.216 mm, first natural frequency 31.9 Hz, and a clean
mesh at 459 thousand nodes. The thing I took from it is that I learned to read *where* the stress
is, not just how big it is - the hot spot has to be where the physics puts it, and when it is not,
the design is wrong."

---

## 9. Fix these three things before the interview

1. **Rewrite the GitHub README** to match your data (section 6, item 1) and swap in the ten images
   from `Project fem/README_images/`.
2. **Fill in this document's section 4 in your own words**, then say it out loud. If you cannot say
   section 5's answers out loud without reading, they are not learned.
3. **Know section 6 cold.** Those are the five weak spots. An interviewer who finds one of them
   himself will respect you more for naming it first than for being caught.
