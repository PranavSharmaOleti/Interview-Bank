# Block A + Block B - the questions, with the answers

**L&T GET (core, mechanical) - 2027 pass-out | 21 Oct 2026**

Everything on one page. Block A = the questions actually traceable to L&T mechanical interviews.
Block B = the classic fresher-panel core. Answers are copied verbatim from the bank files, so the
wording and the `Push:` / `Trap:` lines are exactly what you will drill in the mock.

**How to use it:** read the question, answer it out loud *from memory first*, then read the
answer and see what you missed. Answering out loud is the whole point - reading teaches nothing.
If you cannot say it in 60 seconds, it is not learned yet.

**Three rules:** answer the question asked, not the one you prepared. Numbers first, then the
mechanism, then why it matters in a plant. "I do not know, and here is how I would work it out"
beats a confident guess every single time.

---

## BLOCK A - the 10 that are actually traceable to L&T mechanical interviews

*Only about 8-10 questions in the entire public record are genuinely attributable to L&T.*

---

### A1. State the laws of thermodynamics and explain entropy.

**02 Q1**

*State the four laws of thermodynamics in one line each and what each is used for.*

**A:** Zeroth: if A equals B and B equals C, then A equals C - basis of temperature measurement. First: energy cannot be created or destroyed, delta U = Q - W - energy balance for any system. Second: entropy of an isolated system never decreases, heat flows from hot to cold - sets direction and limits efficiency. Third: entropy approaches a constant (zero for perfect crystal) as temperature approaches absolute zero - reference for absolute entropy values.

**Push:** Why is the second law stated in terms of entropy? **A:** Because entropy quantifies irreversibility; the Kelvin-Planck and Clausius statements are special cases of the entropy principle.

**Trap:** Saying "energy is conserved" for the second law - that is the first law.

**02 Q3**

*Define entropy. State the second law in entropy form and explain why entropy increases in real processes.*

**A:** Entropy is a measure of molecular disorder or energy dispersal, defined as dS = dQ_rev/T. Second law: for any process in an isolated system, delta S >= 0. Entropy increases because irreversibilities (friction, unrestrained expansion, heat transfer across finite temperature difference) generate entropy - the inequality T*dS >= dQ shows actual heat transfer is always less than reversible equivalent for same entropy change.

**Push:** What is entropy generation in a throttling process? **A:** Throttling is isenthalpic but irreversible; entropy increases as pressure drops with no work output.

**Trap:** Saying entropy increases because "disorder increases" without linking to irreversibility.

---

### A2. What does a stress-strain curve show, and how do stress and strain differ?

**01 Q1**

*What is the difference between stress and strain? Give their units and the basic formula connecting them.*

**A:** Stress (sigma) is internal resistance per unit area, units N/m2 or Pa. Strain (epsilon) is deformation per unit length, dimensionless. Hooke's law: sigma = E * epsilon in the linear elastic region, where E is Young's modulus.

**Push:** If you double the load on a steel rod in the elastic range, what happens to strain?
**Answer:** Strain doubles - linear proportionality holds until the proportional limit.

**Trap:** Stating stress has units of "N" instead of "N/m2" or confusing engineering strain with true strain.

**01 Q2**

*Sketch the stress-strain curve for mild steel and label every key point.*

**A:** Linear elastic (OA) -> proportional limit (P) -> elastic limit (E) -> upper yield point (Y_u) -> lower yield point (Y_l) -> plastic region with strain hardening -> ultimate tensile strength (U) -> necking -> fracture (F). Ductility = strain at fracture; toughness = area under curve; resilience = area up to elastic limit; stiffness = slope in elastic region (E).

**Push:** Where does the 0.2% proof stress sit on this curve?
**Answer:** It's the stress at 0.2% plastic strain offset from origin - used for materials without a clear yield point like aluminium.

**Trap:** Calling the proportional limit and elastic limit the same point, or saying necking starts at yield.

**01 Q3**

*What is Hooke's law and where does it stop being valid?*

**A:** Hooke's law states stress is proportional to strain (sigma = E*epsilon). It is valid only up to the proportional limit - the highest stress where the stress-strain curve remains a straight line. Beyond this, the material still behaves elastically (returns to original shape) up to the elastic limit, but not linearly.

**Push:** Can a material be elastic but not follow Hooke's law?
**Answer:** Yes - rubber is elastic (returns to shape) but non-linear. Hooke's law requires linear elasticity.

**Trap:** Saying Hooke's law holds up to the yield point or elastic limit.

---

### A3. Manufacturing processes and production technology - types of welding and where each is used, and lathe operations.

**04 Q26**

*Compare the main welding processes.*

**A:** SMAW uses a flux-coated consumable electrode, needs no gas, works in any position and outdoors, but it is slow - the standard for site erection. GMAW/MIG feeds a continuous wire under a shielding gas: fast, clean, good for thin sheet, but it needs wind protection. GTAW/TIG uses a non-consumable tungsten with argon and a hand-added filler; the highest quality and control, but slow, so it suits root passes, thin tube and stainless. SAW feeds a bare wire under a flux blanket, giving a very high deposition rate on long seams in thick plate. FCAW uses a flux-cored wire and needs little or no shielding gas - easy like MIG, but with a slag. Plasma and laser are mainly cutting processes rather than joining, though plasma welding does exist.

**Push:** Which process for a 2 mm stainless sheet, and why? - TIG, because it gives a clean, oxide-free, low-heat-input weld with no flux contamination and the heat input can be controlled to avoid distortion; laser if the volume is high and the joint is simple.

**Trap:** "SMAW gives the best quality weld because it is the toughest process" - the shielded processes give cleaner and more consistent deposits; SMAW's advantage is that it is robust and works everywhere.

**04 Q1**

*Walk me through the main operations you can do on a lathe.*

**A:** Turning, facing, parting off, grooving, threading, chamfering, boring, tapping and knurling are the standard lathe operations. Turning reduces the diameter (external), facing produces a flat end, parting off severs the finished part, grooving cuts a groove, threading cuts the screw thread, boring enlarges and finishes an existing hole, tapping cuts an internal thread and knurling puts a grip pattern on the surface. On a CNC turning centre exactly the same things happen, driven by G-codes instead of handwheels.

**Push:** Why do you not bore a hole from solid on the lathe? - Because you would remove a huge amount of metal as swarf with a long slender bar that would chatter and break; you drill the hole first and then bore it to size.

**Trap:** "Facing and turning are the same operation" - facing makes a flat surface perpendicular to the axis, turning makes a cylindrical surface.

**04 Q2**

*What is the difference between a roughing cut and a finishing cut?*

**A:** Roughing is the heavy cut that removes most of the material: deep depth of cut, high feed, relatively lower cutting speed, a tougher tool with a large nose radius and good coolant supply. Finishing is the light final cut: small depth of cut, fine feed, higher speed, a sharp rigid tool with a small nose radius, and it is judged on accuracy and surface finish rather than metal removal rate. Roughing sets the shape, finishing sets the size and the finish.

**Push:** How do you choose the cutting speed for a given operation? - From the tool material and the workpiece: carbide runs several times faster than HSS on the same workpiece, and the diameter sets the rpm you need for that speed.

**Trap:** "Roughing uses high speed and light feed" - that is finishing; roughing runs at a lower speed with heavy feed and a deep cut.

**04 Q3**

*How do you know a cutting tool has worn out? What is a "tool signature"?*

**A:** On a single point turning tool, flank wear shows up as a bright secondary bevel or band just behind the cutting edge - that band is the tool signature, and its width tells you how much wear has built up. On the workpiece the same wear shows as a taper on the turned diameter (it grows away from the chuck), a drifting dimension, or a rough finish. So you inspect the tool visually, watch the dimension trend across the job, and compare the wear land against the limit for that tool grade.

**Push:** Which wears faster, flank wear or crater wear? - Crater wear on the rake face, caused by heat and chemical reaction with the hot chips, usually develops faster on ductile materials at high speeds; flank wear dominates on hard or abrasive workpieces.

**Trap:** "The tool signature is the bright band you see on the workpiece" - the signature is on the tool; the workpiece shows a taper, a loss of size, chatter marks or a poor finish.

---

### A4. What is a gearbox? Name the types (spur, helical, bevel, worm, planetary).

**05 Q16**

*What types of gears do you know, and where is each one used?*

**A:** Spur gear - straight teeth on a cylindrical shaft with parallel axes; the simplest and cheapest, used for low speed and general duty. Helical gear - teeth inclined to the axis, parallel axes; smoother, quieter and higher capacity because more teeth share the load, but it generates axial thrust that needs a thrust bearing, so it is used in high-speed gearboxes and in vehicle gearboxes. Bevel gear - conical, for shafts that intersect, typically at 90 deg. Worm - a screw driving a wheel, for very high ratios in a compact package, self-locking, but low efficiency and it generates heat. Planetary - sun, planets and ring, all coaxial, a very high ratio in one stage, used in automatic transmissions and in coaxial reduction boxes. Rack and pinion - converts rotation to linear motion, used in machine tools and actuators.

**Push:** "Why do helical gears generate axial thrust?" - Because the tooth force has a component along the axis, proportional to the helix angle; you must support that with a thrust bearing or a properly preloaded pair.

**Trap:** Believing helical gears are always more efficient than spur. They are smoother and quieter, but the axial thrust and the extra sliding loss mean they are not automatically more efficient.

---

### A5. What is a factor of safety and how do you choose it?

**01 Q5**

*Define allowable stress and factor of safety. How do you choose a factor of safety in practice?*

**A:** Allowable stress = yield stress (or UTS) / factor of safety (FoS). FoS choice depends on: loading type (static vs dynamic/impact), material reliability (homogeneous steel vs casting), consequence of failure (safety critical vs redundant), service temperature (creep), code requirements (IS 800, ASME), manufacturing uncertainty (weld quality, residual stress), inspection access.

**Push:** What typical FoS would you use for a static steel structure per IS 800?
**Answer:** Around 1.5 to 1.67 on yield strength for limit state design; older working stress codes used ~1.5-2.0.

**Trap:** Giving a single number like "FoS = 2" without context, or using UTS instead of yield for ductile materials.

**05 Q3**

*How do you choose the factor of safety for a real part? Is it always 3?*

**A:** No. The factor of safety covers uncertainty in the loads, in the material properties and in manufacturing, and it depends on how bad the failure would be. For a ductile steel bracket under static load, 2 to 3 is normal; for a casting, a weldment or anything with a sharp stress raiser, go higher, 3 to 4; for pressure parts the code fixes it, 3.5 on yield in ASME VIII Division 1. Brittle material needs more because it fails without warning. For fatigue you do not use one factor on the strength - you take an allowable amplitude from the S-N curve with roughly 1.5 to 2 on top.

**Push:** "How is the factor of safety different for a crane hook and for a pressure vessel?" - A pressure vessel gets the code value because a leak can kill people and the loads are well characterised; a crane hook gets more because the load range and shock are less predictable and the material must be very clean.

**Trap:** Quoting one universal value of 3. The interviewer wants to hear that it is a judgement about consequences, load uncertainty and material uniformity.

**What they're really testing:** Whether you treat design as a sequence with decisions and trade-offs, or as a formula you apply at the end.

---

---

### A6. What is a hazard and what is a near miss?

**00 Q18**

*What is a hazard? What is a near miss? Give an example.*

**A:** Hazard = a source or situation with the potential to cause harm (an unguarded rotating shaft, a
live conductor, a hot surface, an unsecured scaffold). Near miss = an unplanned event that did not
cause injury this time but had the potential to do so (a dropped tool near someone's foot, a pipe
fletching a worker, a load swinging outside the exclusion zone). The point of tracking near misses is
that they are free lessons - the outcome was luck, not a control.
**Push:** "What did you see at BHEL?" -> A real observation: unguarded machinery, hot work areas,
movement of heavy components, the shop floor discipline. If you do not remember a specific one, say
what you observed generally about the safety discipline in the shop.
**Trap:** confusing hazard and risk. If they push, add: "risk = likelihood x severity, hazard = the
thing that can cause the harm."

---

### A7. GD&T questions - what does true position mean and how is it different from a diameter dimension?

**07 Q17**

*Position tolerance versus a plus/minus diameter dimension — what's the difference?*

**A:** A plus/minus tolerance on a dimension gives only size control; the axis can wander anywhere within the cylinder formed by the size limits - a "worst case" is that a hole can be at its largest size AND at the limit at the same time. Worse, a plus/minus on a position gives a zone of two parallel planes in one direction only, and it does not fix the true centre. A position tolerance gives you a cylindrical zone of a stated diameter centred on the true position (derived from boxed basic dimensions) and oriented to the datums. Crucially, when position tolerance is applied to a feature of size and with MMC (or LMC) it also controls the size, so size and position are two sides of the same integrated requirement. That is why a position callout can replace both the size dimension and a separate location dimension.

**Push:** What is the virtual condition and why does it matter? It is the MMC size minus the position tolerance (for internal features) or plus (for external) — it is the functional gauge size. A part that passes the gauge will assemble; the virtual condition is what inspection uses to test interchangeability.

**Trap:** Calling a hole "position tolerant" when it has only a plus/minus dimension. A plus/minus dimension only controls size, not position.

**07 Q18**

*How do you read a feature control frame?*

**A:** Read it left to right: the geometric characteristic symbol, then the tolerance value (with a diameter symbol if the zone is cylindrical), then any modifier (M, L, S), then the datum references (primary A, secondary B, tertiary C). For example, a position symbol, 0.2 dia, then A, then B, then the MMC symbol after the tolerance value means: the axis of this feature must lie within a cylinder of diameter 0.2 mm, located at the true position from datums A and B, and 0.2 is the tolerance available at maximum material condition. The basic dimensions that fix true position are boxed on the drawing.

**Push:** Where does the material condition modifier go? It goes after the tolerance value for the controlled feature, not after the datum letters. After a datum letter it applies to that datum.

**Trap:** Misreading the frame as a recipe list. The frame is a compact description of what the feature must satisfy, with clear order: characteristic -> tolerance -> datums.

**07 Q19**

*What do MMC, LMC and RFS mean, and how do they change the tolerance?*

**A:** MMC is maximum material condition - for a hole the smallest allowed diameter, for a shaft the largest - the most material in the part, so the least tolerance is available and the zone is at its tightest. At MMC the tolerance in the frame is exactly the stated value. If the actual size departs from MMC (hole gets larger, shaft gets smaller), the part has gained material, so bonus tolerance is added equal to how much it departed from MMC. LMC is the opposite - a hole at its largest, a shaft at its smallest - the most tolerance, where the tolerance is greatest. RFS, regardless of feature size, means the tolerance stays exactly as stated no matter what the actual size is; no bonus, no loss. Some Indian textbooks write this as PMC (maybe "plus/minus condition") and use it the same way: the tolerance does not change with actual size.

**Push:** Why does bonus tolerance exist? It protects function - a hole slightly oversize is still acceptable if the position error is within the enlarged zone; the tolerance grows to match reality instead of rejecting good parts.

**Trap:** Thinking MMC gives the part more tolerance. It gives the least tolerance at MMC; the bonus appears as you move away from it.

**07 Q22**

*Fits and tolerances — ISO system, hole basis and shaft basis, clearance/transition/interference fits with an example of each, IT grades.*

**A:** ISO system separates the tolerance grade (IT) which fixes the size of the tolerance zone, and the fundamental deviation (a letter) which fixes its position relative to nominal. IT grades IT01 to IT18; IT1-IT3 fine, IT4-IT6 fine, IT7-IT8 medium, IT9-IT11 coarse, IT12-IT18 very coarse. In hole basis the hole always has H (lower deviation zero, hole above nominal), shaft gets the letter. In shaft basis it is reversed. Three fit types: clearance (hole always > shaft), transition (zones overlap, can be clearance or interference), interference (shaft always > hole). Example: for 20 mm nominal, H7 hole is 20.000-20.021 (IT7 = 21 µm for 18-30 mm step), g6 shaft is 19.981-19.994 (es = -6, IT6 = 13). H8/f7 clearance example: H8 = 20.000-20.033 (IT8 = 33 µm), f7 = 19.959-20.001 (es = -20). H7/p6 interference example: p = +28 µm deviation, p6 = 20.028-20.041 (es = +28, ei = +28-13 = +15).

**Push:** What is the fit for a bolt hole? H7/g6 is the standard loose running fit; H8/f7 is a clearance fit used when clearance is important.

**Trap:** Confusing the fundamental deviation letter with the fit — the letter sets where the zone sits, the IT grade sets its size.

---

### A8. Fluid mechanics - what does the panel actually want here?

**03 Q3**

*Derive the continuity equation for steady incompressible flow in a pipe. What changes for a branching pipe?*

**A:** For steady flow, mass entering = mass leaving. For incompressible flow, rho is constant, so rho * A1 * v1 = rho * A2 * v2, giving A1*v1 = A2*v2 or Q = A*v = constant. For a branching pipe with one inlet and multiple outlets, the sum of outlet flow rates equals the inlet flow rate: Q_in = Q_out1 + Q_out2 + ...

**Push:** If a 200 mm pipe splits into two 150 mm pipes and velocity in one branch is 3 m/s, what is the velocity in the other branch if total flow is 0.1 m3/s?
**A:** Q_total = 0.1 m3/s. Q1 = (pi/4)*0.15^2*3 = 0.053 m3/s. Q2 = 0.1 - 0.053 = 0.047 m3/s. v2 = Q2/A2 = 0.047/0.0177 = 2.66 m/s.

**Trap:** Applying A1*v1 = A2*v2 to each branch individually without conserving total mass.

**03 Q4**

*State Bernoulli's equation and list all its assumptions. How do you derive it from Euler's equation?*

**A:** Bernoulli: p/rho*g + v^2/2g + z = constant along a streamline. Assumptions: steady flow, incompressible fluid, inviscid (no friction), along a single streamline, no energy addition/removal (no pump/turbine between points). Derivation from Euler: Start with Euler's equation along a streamline: dp/rho + v*dv + g*dz = 0. Integrate: int(dp/rho) + v^2/2 + gz = constant. For incompressible flow, int(dp/rho) = p/rho, giving p/rho + v^2/2 + gz = constant.

**Push:** Can you apply Bernoulli across a pump?
**A:** No, because a pump adds energy. You need the extended Bernoulli with head added: p1/rho*g + v1^2/2g + z1 + H_pump = p2/rho*g + v2^2/2g + z2 + h_loss.

**Trap:** Applying Bernoulli between points in different streamlines, or across a valve/pump without accounting for losses or work.

**03 Q7**

*Define Reynolds number. What are the laminar, transition, and turbulent ranges for pipe flow? What physically changes at transition?*

**A:** Re = rho*v*D/mu = v*D/nu. It represents ratio of inertial forces to viscous forces. Pipe flow: laminar below Re = 2300, transition 2300-4000, turbulent above 4000. At transition, flow changes from orderly layers to chaotic eddies, velocity profile flattens from parabolic to nearly uniform, and friction factor jumps from 64/Re to a higher value on the Moody chart.

**Push:** Why is the critical Re for pipe flow 2300 but for flat plate boundary layer it is 5e5?
**A:** Different geometries and instability mechanisms. Pipe flow is confined and becomes unstable to small disturbances at lower Re. Flat plate boundary layer transitions due to Tollmien-Schlichting waves amplified by freestream turbulence.

**Trap:** Using Re = 2300 as a sharp boundary - it is a range, and actual transition depends on pipe roughness, inlet conditions, and disturbances.

**03 Q8**

*State the Darcy-Weisbach equation for head loss. What is the friction factor for laminar flow? How do you find it for turbulent flow?*

**A:** h_f = f * (L/D) * (v^2/2g). For laminar flow: f = 64/Re exactly. For turbulent flow, f depends on Re and relative roughness (epsilon/D). Use the Moody chart or Colebrook equation: 1/sqrt(f) = -2*log10(epsilon/(3.7*D) + 2.51/(Re*sqrt(f))). For smooth pipes, Blasius approximation: f = 0.316/Re^0.25 (valid 4000 < Re < 1e5).

**Push:** What happens to head loss if you double the flow rate in turbulent flow?
**A:** v doubles, so v^2 quadruples. f changes slightly (decreases with Re^0.25), but overall h_f increases by roughly 3.5-4 times. In laminar flow, h_f is linear with v (since f = 64/Re), so doubling v doubles h_f.

**Trap:** Using f = 64/Re for turbulent flow, or ignoring the Re-dependence of f in turbulent regime.

---

### A9. Strength of materials - the recurring numerical and the buckling derivation.

**01 Q7**

*A 20 mm diameter steel rod carries a 50 kN tensile load. Calculate the tensile stress.*

**A:** Area = pi/4 * 20^2 = 314.16 mm2. Stress = 50000 N / 314.16 mm2 = 159.2 MPa. This is well below mild steel yield (~250 MPa) so elastic.

**Push:** If the rod is 2 m long and E = 200 GPa, what is the elongation?
**Answer:** Strain = 159.2/200000 = 7.96e-4; delta = strain * L = 1.59 mm.

**Trap:** Forgetting to convert mm2 to m2 or using diameter instead of radius in area formula.

**01 Q13**

*List five ways to reduce deflection of a cantilever beam.*

**A:** 1) Increase Young's modulus E (change material), 2) Increase second moment I (deeper section, I-beam vs rectangle), 3) Reduce span L (most effective - L^3 or L^4 dependence), 4) Add intermediate support (convert to propped cantilever), 5) Change section profile (tapered, haunched, or pre-camber). Also: reduce load, use composite action.

**Push:** Which is most effective per unit cost?
**Answer:** Reducing span or increasing depth (I ~ depth^3) usually best. Pre-camber only offsets, doesn't change stiffness.

**Trap:** Listing "increase thickness" without specifying where (flange vs web matters), or saying "increase FoS".

**01 Q17**

*Derive Euler's critical buckling load for a pinned-pinned column.*

**A:** Start with beam equation: EI*d^2y/dx^2 = -M = -P*y. Solution: y = A*sin(kx) + B*cos(kx) where k^2 = P/(EI). Pinned ends: y=0 at x=0 and x=L -> B=0, sin(kL)=0 -> kL = n*pi. Lowest mode (n=1): P_cr = pi^2*EI/L^2. Assumptions: perfectly straight, homogeneous, elastic, axial load, no imperfections.

**Push:** What is the effective length L_eff for fixed-fixed column?
**Answer:** L_eff = 0.5*L (K=0.5). P_cr = 4*pi^2*EI/L^2 (four times pinned-pinned).

**Trap:** Using L instead of L_eff, or forgetting K factors for other end conditions.

---

### A10. Power factor and three-phase induction motor starting. (Officially tagged ELECTRICAL in the sources - a mech candidate may still get them, because L&T site loads are large.)

**08 Q3**

*What is power factor, what makes it low, and why does a low power factor cost money?*

**A:** Power factor is cos(phi), the ratio of real power to apparent power, so kW = kVA x PF. It falls when current and voltage are out of phase, which happens with inductive loads - induction motors, transformers, welding sets, ballasts - where current lags voltage. A low PF is expensive because for the same kW the current is higher, I = P/(sqrt(3) x V_L x cos phi), so you pay more I-squared-R loss in cables and transformers, you need bigger cables, transformers and generators, you get more voltage drop, and the utility penalises you below the power factor agreed in the supply contract.

**Push:** Which equipment is the worst offender? Large induction motors running lightly loaded - at full load a motor is close to unity PF, but at part load its PF drops badly; a transformer on no load is also very poor, around 0.2 to 0.3.

**Trap:** The classic wrong answer is that a low PF is only a nuisance. It directly inflates current, losses and equipment size. Note also that in the source question bank "power factor" is tagged ELECTRICAL, so treat it as insurance for a mech panel, not a guaranteed question.

**08 Q8**

*How does a three-phase induction motor work, and what is slip?*

**A:** A three-phase supply creates a rotating magnetic field in the stator; that field cuts the rotor conductors and induces current in them, and the interaction of that rotor current with the field produces torque, so the rotor follows the field at a speed slightly below it. Slip is that difference as a fraction, s = (Ns - N)/Ns, where Ns = 120 x f / P with P the number of poles. At full load a motor typically runs with a slip of roughly 2 to 6 percent depending on size, and it is this slip that is what converts into torque.

**Push:** Why can't it run at exactly synchronous speed? At synchronous speed there is no relative motion between the field and the rotor, so no current is induced and no torque is produced - a small slip is essential.

**Trap:** Saying the motor runs at synchronous speed, or quoting a running slip of 100 percent. Slip of 1 is the starting condition; running slip is a few percent.

**08 Q9**

*Why is a starter needed, and what happens on DOL starting?*

**A:** On direct-on-line starting the motor is connected straight across the supply, and the current at standstill is typically 5 to 7 times the full-load current, because at zero speed the rotor sees the full supply frequency and the motor impedance is at its lowest. That inrush pulls the supply voltage down, stresses the transformer and cables, and can trip the protection, so above a certain size you do not close the contactor straight to the line - you start through a reduced-voltage means. A starter does that, and also gives you a safe way to stop and reverse the machine plus overload and short-circuit protection for it.

**Push:** Does that starting current damage the motor? Usually not, because the inrush lasts only a second or two and the winding has a good short-time withstand; the real victims are the supply, the starter contacts and the mechanical train.

**Trap:** Saying a starter is there to limit speed or to save power. Note also that in the source question bank "three-phase induction motor starting" is tagged ELECTRICAL, so treat it as insurance for a mech panel, not the main event.

## BLOCK B - the 18 classic fresher-panel questions

*These recur across real candidate accounts year after year. Not L&T-specific - the panel's default material..*

---

### B1. Draw the Rankine cycle on a T-s diagram and name the four processes.

**02 Q6**

*Sketch the Rankine cycle on a T-s diagram. Name the four processes and list the five ways to improve cycle efficiency with effect and cost of each.*

**A:** T-s diagram: 1-2 constant pressure heat addition in boiler (horizontal right), 2-3 isentropic expansion in turbine (vertical down), 3-4 constant pressure condensation (horizontal left), 4-1 isentropic pumping (vertical up). Five improvements: (1) Superheat - raises average heat addition temperature, increases efficiency, needs better materials for higher temperature. (2) Reheat - reduces moisture at turbine exit, improves efficiency, adds reheater cost and pressure drop. (3) Regenerative feedwater heating - uses turbine bleed steam to preheat feedwater, raises average heat addition temperature, needs extra heaters and piping. (4) Lower condenser pressure - increases expansion ratio and work output, needs larger condenser and vacuum pumps. (5) Raise boiler pressure - raises saturation temperature, improves efficiency, needs thicker pressure parts and better materials.

**Push:** Which improvement gives the most gain per rupee in a typical plant? **A:** Regenerative feedwater heating usually gives best cost-benefit; superheat and reheat are standard in modern plants.

**Trap:** Forgetting that lowering condenser pressure increases turbine last-stage blade erosion risk from wetness.

---

### B2. Difference between a heat engine and a heat pump.

**02 Q5**

*Distinguish between heat engine, heat pump, refrigerator, and chiller. Give the COP relations.*

**A:** Heat engine: converts heat to work, eta = W_net/Q_H. Heat pump: moves heat from cold to hot for heating, COP_HP = Q_H/W = 1/(1 - T_L/T_H). Refrigerator: moves heat from cold space for cooling, COP_R = Q_L/W = T_L/(T_H - T_L). Chiller: large-scale refrigeration for process/AC, same COP as refrigerator. COP_HP = COP_R + 1.

**Push:** Why is COP_HP always greater than 1? **A:** Because Q_H = Q_L + W, so COP_HP = (Q_L + W)/W = COP_R + 1 > 1.

**Trap:** Confusing COP of heat pump with efficiency of heat engine.

---

### B3. What is the Carnot limit and why do real cycles fall short?

**02 Q4**

*What is Carnot efficiency? State Carnot theorem and explain why no real cycle beats it.*

**A:** Carnot efficiency eta_C = 1 - T_L/T_H (absolute temperatures). Carnot theorem: no engine operating between two reservoirs can exceed Carnot efficiency. Real cycles have irreversibilities - heat transfer across finite delta T, friction, non-isentropic compression/expansion - so their efficiency is always lower. Carnot is the reversible limit.

**Push:** If a power plant claims 50% efficiency with T_H = 800 K and T_L = 300 K, is it possible? **A:** Carnot limit is 1 - 300/800 = 62.5%, so 50% is theoretically possible but very high for a real plant.

**Trap:** Using Celsius temperatures in the Carnot formula.

---

### B4. Name five ways to limit the deflection of a cantilever beam.

---

### B5. A 20 mm dia steel rod carries 50 kN. Find the stress.

---

### B6. Derive Euler's buckling load / what is slenderness ratio?

**01 Q18**

*List the effective length factors K for standard column end conditions.*

**A:** Pinned-pinned: K=1.0; Fixed-fixed: K=0.5; Fixed-pinned: K=0.7; Fixed-free: K=2.0. Effective length L_eff = K*L. Buckling load P_cr = pi^2*EI/(K*L)^2.

**Push:** Real fixed supports are never perfectly rigid. What K do codes typically use for "fixed" ends?
**Answer:** IS 800 uses K=0.65 for fixed-fixed, 0.8 for fixed-pinned to account for partial fixity.

**Trap:** Using K=1 for fixed-pinned, or K=0.5 for fixed-free.

**01 Q19**

*What is slenderness ratio? When do you use Euler vs Rankine vs Johnson formula?*

**A:** Slenderness ratio lambda = L_eff / r (r = radius of gyration = sqrt(I/A)). Euler valid for long columns (lambda > lambda_c, elastic buckling). Rankine: empirical for all lengths, 1/P_R = 1/P_c + 1/P_e. Johnson parabolic: for intermediate columns (inelastic buckling). Euler for lambda > 120 (steel), Rankine for general, Johnson for lambda < ~80.

**Push:** What is the transition slenderness for Euler to be valid for mild steel (E=200 GPa, sigma_y=250 MPa)?
**Answer:** lambda_c = pi*sqrt(E/sigma_y) = pi*sqrt(200000/250) = 88.8. Above this, Euler applies.

**Trap:** Using slenderness ratio based on length L instead of L_eff, or applying Euler to short columns.

---

### B7. Laminar vs turbulent - define Reynolds number and give the ranges.

---

### B8. Cavitation in pumps - what causes it, how do you prevent it.

**03 Q11**

*Describe the working principle of a centrifugal pump. What is NPSH and why is cavitation a problem?*

**A:** Centrifugal pump: impeller rotates, imparting kinetic energy to fluid (v^2/2g), converted to pressure in the volute/diffuser. Requires priming (casing filled with liquid) because it cannot pump gas. Total head H = suction head + delivery head + velocity head difference + losses. NPSH available = (p_suction - p_vapour)/rho*g + v^2/2g. NPSH required is a pump characteristic. Cavitation occurs when NPSHa < NPSHr - local pressure drops below vapour pressure, bubbles form and collapse violently, causing noise, vibration, pitting damage, and performance drop.

**Push:** How do you prevent cavitation in a pump installation?
**A:** Increase suction pressure (raise supply tank, reduce suction line losses), reduce fluid temperature (lower vapour pressure), use pump with lower NPSHr (larger impeller eye, lower speed), install booster pump.

**Trap:** Thinking cavitation only happens at the impeller eye - it can also occur in valve seats, propeller blades, and turbine runners.

---

### B9. Types of welding and where each is used.

**04 Q27**

*What are the welding positions, and why is vertical-up the hardest?*

**A:** The positions are flat (F), horizontal (H), vertical (V) and overhead (OH), defined by the direction of travel of the weld relative to the plate and the position of the molten pool. Vertical-up is the hardest because the molten pool has to be held against gravity: the metal and the slag tend to run down, the puddle is hard to control, and as the bead grows the pool gets bigger and harder still, so the electrode must be held at an angle to direct the arc force upward. Vertical-down is easier because the arc force pushes the molten metal down into the joint, but the deposition rate is lower and the root profile is affected.

**Push:** How does a welder get qualified for vertical work? - The welder makes a test assembly in that position to the qualified procedure and passes the specified visual and NDT acceptance criteria, so the qualification record must cover the position and the process actually used on the job.

**Trap:** "Overhead welding is the hardest position" - vertical-up is generally regarded as the hardest to control because of the pool; overhead is difficult mainly for the welder's strength and for fatigue in the wrist and arm.

---

### B10. Lathe roughing vs finishing, and the tool signature.

---

### B11. GD&T - true position vs diameter dimensioning; MMC/LMC.

---

### B12. Belt drive vs chain drive.

**05 Q13**

*Flat belt versus V-belt - why has the V-belt replaced the flat belt, and when would you still use a flat belt?*

**A:** A V-belt transmits much more power in the same space because it wedges in the pulley groove. The wedge multiplies the normal force on the belt, so the effective coefficient of friction is mu / sin(alpha/2) - about 3 times mu for a 40 deg groove - and a V-belt can carry roughly 2 to 3 times the power of a flat belt of the same width, at higher speed, because it sits deeper and will not creep off the pulley. A flat belt is still used where the pulley must be wide, where the machine has to handle reverse running or act as a slipping clutch, and where the drive is small and cheap. Both have the same weakness: they need tensioning and they slip.

**Push:** "What is the biggest limitation of a belt drive?" - It must be kept tensioned, its life is short compared with a gear, it needs a guard, and slip means the speed ratio is never exact.

**Trap:** Saying the V-belt works by friction on the bottom of the belt. The bottom is not in contact - it is the side faces of the V that wedge.

**05 Q14**

*Explain open, crossed and quartered belt drives. What are velocity ratio, slip and creep, and how do you calculate the belt length?*

**A:** In an open drive both pulleys rotate the same way and the belt is a few percent shorter; in a crossed drive the belt crosses over so the pulleys rotate in opposite ways, but the crossed belt is longer, needs more tension and wears faster; in a quartered drive the pulleys rotate in opposite ways with the belt twisted through a quarter turn, used when the shafts must be moved apart, at the cost of rapid belt wear. Velocity ratio = N1/N2 = D2/D1. Slip is the ratio error from insufficient friction, around 2 to 5 percent, and creep is the elastic stretch of the belt around the pulley, which gives only about 0.1 to 0.2 percent error on the small pulley. Belt length is L = 2C + (pi/2)(D + d) + (D - d)^2/(4C), with C the centre distance and D and d the pulley diameters.

**Push:** "How do you set the belt tension?" - By the sag rule: a belt should sag about 1 to 2 percent of the span, or you use a tension gauge and check the force on the slack side after a run-in period. The correct tension is the minimum that will not slip, and too much tension is just as bad because it wears the belt and the bearings.

**Trap:** Believing creep is the same as slip. Slip is a friction loss that is avoidable, creep is elastic and unavoidable.

**05 Q15**

*Tell me about roller chain drives - pitch, sprocket, lubrication - and when do you prefer a chain to a belt?*

**A:** A roller chain is identified by its pitch: 08B-1 has a pitch of 12.7 mm and ANSI 40 chain has the same half-inch pitch, and the sprocket teeth are cut to match, with pitch circle diameter D = p / sin(180/Z). The chain pull comes from the power - the standard textbook relation is T1 - T2 = 1025 P newtons with P in kW, so 5 kW needs about 5.1 kN across the chain. Lubrication depends on chain speed: grease below about 1.5 m/s, drip oil up to about 6 m/s, and an oil bath or spray above that. You prefer a chain to a belt in dirty, dusty or oily plant conditions, because the chain does not slip, can be enclosed and lubricated, and carries high torque at low speed over a small centre distance. The price is noise, weight, sprocket wear and the need for lubrication.

**Push:** "How does a silent chain differ from a roller chain?" - A silent or block chain has the teeth engaging in the pockets of a nearly continuous plate, so it is quieter, runs faster and needs less lubrication, but it is heavier and costlier.

**Trap:** Using a belt where the plant atmosphere is dusty and oily - a belt slips and glazes, and the drive will not hold its ratio.

**What they're really testing:** Whether you can pick between belt and chain on the basis of the working environment, and whether you know the numbers that drive the choice.

---

---

### B13. Critical speed of a shaft and how it causes whirling.

**01 Q26**

*Define critical speed of a shaft. How does it relate to natural frequency and whirling?*

**A:** Critical speed = rotational speed at which shaft rotation frequency coincides with lateral natural frequency of the rotor-bearing system. At critical speed, synchronous whirling occurs - shaft centre rotates in orbit at running speed. Causes large vibration amplitudes. Practical fix: operate well away from critical speeds, improve balancing, increase stiffness, add damping (squeeze film dampers).

**Push:** Can a shaft have multiple critical speeds?
**Answer:** Yes - one for each bending mode (first, second, third...). First critical speed is usually most important.

**Trap:** Confusing critical speed (rotational speed) with natural frequency (Hz), or saying critical speed only occurs in vertical shafts.

**01 Q27**

*Differentiate between whirling and vibration. What is static vs dynamic balancing?*

**A:** Whirling: synchronous orbital motion of rotor centreline at running speed (or sub/super-synchronous). Vibration: broader term for any oscillatory motion. Static balancing: corrects single-plane unbalance (centrifugal force couple = 0). Dynamic balancing: corrects two-plane unbalance (both force and couple = 0). Static balancing sufficient for thin discs; dynamic needed for long rotors.

**Push:** A rotor is statically balanced but vibrates at running speed. Why?
**Answer:** It has couple unbalance - two equal unbalances 180 deg apart in different planes. Creates moment but no net force. Requires dynamic balancing.

**Trap:** Saying static balancing fixes all unbalance, or that dynamic balancing is "better" rather than "necessary for multi-plane unbalance".

---

### B14. Your favourite subject - why, and explain a concept from it.

**00 Q3**

*What is your favourite subject, and why?*

**A:** Pick the one you can actually defend for 10 minutes, not the one with the best marks. Give a
reason that shows understanding, not just liking: "I like X because it is where the abstract maths
finally turns into a physical outcome - you can see the machine behave the way the equation says it
will." Then be ready for the immediate follow-up: explain one concept from it.
**Push:** "Explain a concept from it." -> Have ONE ready, and be ready for a numerical.
**Trap:** naming Thermodynamics and then freezing when they ask for the Otto cycle. If thermo is your
favourite, the Otto and Diesel cycles are almost certain to be asked.

---

### B15. Why mechanical over civil or electrical?

**00 Q2**

*Why did you choose mechanical engineering?*

**A:** Because it is the broadest of the core engineering branches - it connects physics and maths to
something you can see built. Say the specific area that pulled you: machines, thermal, design, or
manufacturing. Then tie it to the role: you want to be in the part of engineering where a design
becomes a physical machine that has to work.
**Push:** "Why not electrical or civil?" -> Be honest and specific: "I am not saying those are
inferior. I chose mechanical because X, and I am aware that civil would have given me Y. What I want
to do is Z, and mechanical is where I can get to Z fastest."
**Trap:** "Because it is the core of every industry" - vague, and it invites the follow-up you cannot
answer.

---

### B16. Walk me through your final-year project.

**00 Q6**

*Walk me through your final-year project.*

**A:** This is the highest-value question of the interview. Prepare it as a 2-minute story with a
fixed structure: **problem -> what the machine/system is -> your specific part -> the one number or
decision you owned -> what you learned.** Use a diagram if they let you. Make sure the third beat is
yours alone - "we" for the team, "I" for your piece.
**Push:** "Why this project?" -> Why the topic is worth doing, not why the group chose it.
**Push:** "What was the hardest part?" -> Have one specific answer, not "team coordination".
**Trap:** narrating a report instead of a project. If your answer sounds like your project report
read aloud, it is too long and too passive.

**00 Q7**

*What exactly was YOUR contribution?*

**A:** The single most probed question in fresher panels, because it separates people who worked from
people who attended. Give one concrete, bounded thing: one calculation, one model, one analysis, one
section of the design, one test you set up. Then say what you did NOT do.
**Push:** "Did anyone check your work?" -> "Yes, X did, and we disagreed about Y, so I re-ran it" is a
strong answer. "No, I did it alone" is also honest and fine.
**Trap:** "We did everything together" - it reads as non-contribution.

**00 Q8**

*If you could redesign one part of the project, what would you change and why?*

**A:** This is not a trick and it is not a trap - it is a maturity probe. Pick a real limitation you
know about, say the constraint that caused it, and say what you would change. "I would change the
material spec because we had a weight constraint and I would have gone for a higher strength grade
and accepted the cost." Or: "I would have validated it with a test at half scale, which we could not
do, so we relied on simulation."
**Trap:** "Nothing, I would keep it as it is" - reads as no critical thinking.

**00 Q9**

*How did you validate your result?*

**A:** Say which of these you actually did: hand calculation check, comparison with a standard or a
textbook, simulation convergence check, comparison with a previous project, physical test, or
comparison with published data. If you did not validate, say that plainly and say how you would have.
**Trap:** claiming validation you did not do. This is exactly the kind of thing that collapses when
the panel asks a follow-up on the method.

---

### B17. What did you do in the internship? What surprised you?

**00 Q11**

*What did you do in your internship?*

**A:** State the frame in one sentence: "It was a plant training attachment at BHEL Hyderabad, in the
Turbines, Compressors and Gas Turbine division. I was given a technical run-down by the division and
taken through the shops, and I took notes on everything I saw. I was not given design ownership, and
I did not do any design work." Then move immediately into your three observations. The 90-second
version is memorised verbatim in `INTERVIEW_PREP_LT.md` section 3.1 - use that.
**Push:** "So you did not do anything?" -> "That is right - it was a training visit, not a project
assignment. What I did do was study. I wrote down the machine specifications, the tooling logic and
the rotor machining sequence, and I have since read up on why those choices are made."
**Trap:** "It was a great learning experience." (No content. This is the answer interviewers name as
the red flag.) Also: "I was part of the team that worked on..."

**00 Q12**

*What is one thing you observed there that surprised you?*

**A:** Have this ready separately from the script - they will ask it standalone. Your best observation
is the rotor: "A steam turbine rotor is not designed, it is machined. A large alloy-steel forging goes
through a fixed sequence of nineteen operations, blades are fitted into grooves, shrouding is welded
on, and the rotor is balanced stage-wise before the casing closes over it. The biggest machine in that
plant exists purely for first-job rotor balancing, because imbalance force goes as the square of
speed - so at operating speed, a small imbalance becomes a very large force."
**Push:** "What does that tell you about engineering?" -> "That the drawing is only a third of the
job. The process route and the inspection gate at each operation are the other two-thirds."

**00 Q14**

*What did you contribute during the internship?*

**A:** Be honest and reframe: "I did not contribute design work. What I contributed was attention.
I asked questions, I wrote down the machine specifications and the tooling logic so I could explain
them afterwards, and I understood the run-down well enough to explain it to my own group." Then give
one example of something you did that shows you were present and thinking: a question you asked and
the answer, or a process you did not understand until you saw it.
**Trap:** inflating. If they ask a detail you cannot produce, you are finished.

---

### B18. If you could redesign one part of your project, what would you change?

---

**Source files (if you want the surrounding questions):** `bank/00_The_Spine_Behavioural_and_LT.md`, `bank/01_SOM_and_Vibrations.md`, `bank/02_Thermodynamics_and_IC_Engines.md`, `bank/03_Fluids_and_Heat_Transfer.md`, `bank/04_Manufacturing_Welding_NDT.md`, `bank/05_Machine_Design.md`, `bank/07_CAD_GDNT_FEA.md`, `bank/08_Electrical_for_Mechanics.md`.

**Still missing: your final-year project.** Fill `00_START_HERE_TONIGHT.md` section 3. B16 is the most repeated question in the entire public record and your answer to it is the one thing in this file you cannot borrow.
