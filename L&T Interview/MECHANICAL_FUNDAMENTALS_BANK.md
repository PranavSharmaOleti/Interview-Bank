# Mechanical Engineering Interview Bank
# Core fundamentals for Automobiles, Petrochem, and Construction interviews
# CO1: Broad fundamentals with industry-agnostic framing

## File Header (use this exact structure)

```
# Mechanical Engineering - Core Interview Bank

**Part 1 of 8 | 60 questions | Core SOM, Thermo, Fluids, TOM, MD for core GET panel**
*Mechanical GET panel, 30-45 min, industry-agnostic depth: fundamentals from standard mechanical syllabus, occasionally one numerical, plus questions on project and internship.*
*This bank works for automobiles, petrochem, construction, and general core GET roles.*
*Tags: [H] asked very commonly across 4+ interview accounts. [M] asked regularly. [L] occasional.*
*Do not memorise the wording - memorise the idea, then say it in your own words. If you cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing recall, they are testing whether you can reason out loud.*

## Question format (exact)

### Q1. <the question, phrased the way an interviewer would actually say it> [H]

**A:** <exam-ready answer, 2-5 sentences, plain text. Formulas written inline like sigma = F/A, tau = T*r/J. State the key result or value first, then why it matters in practice.>

**Push:** <the single most likely follow-up the interviewer would ask, plus its answer - 1-2 sentences.>
Omit the "Push:" line only when there is genuinely no natural follow-up.

**Trap:** <the most common wrong answer, or the misconception the interviewer is testing - 1 line.>
Omit the "Trap:" line when it is not applicable.

**What they're really testing:** <one line - intent of the section>
```

## Quality rules (non-negotiable)

1. **Technical correctness first.** If not certain of a formula or value, write the general principle and the method, and say so in the answer ("the standard value is around...", "you'd confirm it in the code"). **NEVER invent a precise number you are unsure of.** A vague correct answer beats a confident wrong one.

2. **Use these standard values consistently:**
   E steel 200 GPa | E aluminium 70 GPa | E cast iron 100-120 GPa | G steel 80 GPa | Poisson 0.3
   density steel 7850 kg/m3 | cast iron 7200 | aluminium 2700 | water 1000 | oil 900-950
   1 atm = 1.013 bar | g = 9.81 m/s2 | 1 kW = 1.34 HP | 1 HP = 0.746 kW | pi = 3.1416
   Re: laminar below 2300, transition 2300-4000, turbulent above 4000
   stress-strain mild steel: proportional ~200 MPa, yield ~250 MPa, ultimate ~400-550 MPa

3. **ASCII only.** No LaTeX, no unicode math symbols, no emoji, no arrows. Write `sigma`, `tau`, `omega`, `theta`, `->`, `x`, `approx`, `deg C`, `kPa`, `MPa`, `N-m`, `m3/s`, `kg/m3`.

4. **Standards:** you may name `IS 800` (steel structures by limit state), `IS 456` (concrete), `IS 2062` (structural steel), `IS 808` (rivets), `IS 1556` (welding electrodes), `IS 3006` (mild steel tubes), `ASTM A106` (seamless pipe), `API 5L` (line pipe). **Do not invent clause numbers** and do not attribute specific values to a code you are not sure about.

5. **Length:** the "A:" line must be speakable in 30-60 seconds. Hard cap about 90 words. This is a spoken interview, not an essay.

6. **Derivations** - when a question classically asks for one ("derive Bernoulli from Euler", "derive Euler buckling load", "explain the Rankine cycle", "derive the Lewis equation", "derive bearing L10 life", "derive the critical insulation radius", "derive natural frequency of an SDOF system"), give the **key steps in 3-5 lines**, not a full derivation. Name the starting assumption and the final result.

7. **Numericals** - when a question classically expects a number, work it in the answer and show the final result, e.g. "a 20 mm dia steel rod under 50 kN -> A = pi/4 x 20^2 = 314 mm2 -> sigma = 50000 N / 314 mm2 = 159 MPa".

8. **Self-contained.** Do not tell the reader to look anything up in another file.

9. **Technical only.** No motivational, HR, behavioural, or company-questions content in your file. That is handled in a separate part.

10. **Number questions `Q1..Qn` within your own file.** Numbering does not need to be continuous across files.

---

# Part 1. Thermodynamics and Heat Engines - 12 questions

## 1. Thermodynamics Fundamentals - 8 questions

### Q1. State the first and second laws of thermodynamics in plain words. [H]

**A:** First Law: Energy cannot be created or destroyed. For any system, the change in internal energy equals heat added minus work done by the system: delta U = Q - W. For flow processes, it's more useful to use enthalpy: delta H = Q - W_s. Heat and work are both path functions, not properties of the system.

**Push:** "What's the difference between heat and work?" → "Heat is energy transfer due to temperature difference; work is energy transfer due to force through distance. Both are path functions, meaning the amount depends on the process path, not just initial and final states."

**Trap:** Calling heat or work a property of the system. They are energy transfer mechanisms, not state properties.

**What they're really testing:** Whether you understand energy conservation and can distinguish between state properties and path functions - fundamental to all thermodynamic calculations.

### Q2. State the second law in entropy form and what it implies. [H]

**A:** Second Law: for any process in an isolated system, delta S >= 0. Entropy (S) is a measure of energy dispersal or disorder. The inequality T*dS >= dQ shows that actual heat transfer is always less than the reversible equivalent for the same entropy change. Entropy increases because of irreversibilities: friction, unrestrained expansion, heat transfer across finite temperature difference.

**Push:** "Why is the second law stated in terms of entropy?" → "Because entropy quantifies irreversibility. The Kelvin-Planck statement (no engine can convert all heat to work) and Clausius statement (heat cannot spontaneously flow from cold to hot) are special cases of the entropy principle."

**Trap:** Saying "energy is conserved" for the second law - that's the first law. The second law introduces directionality and limits to what's possible.

**What they're really testing:** Whether you grasp that the second law is about *possibility* and *direction*, not just a formula.

### Q3. Carnot efficiency and why real cycles can't beat it. [H]

**A:** Carnot efficiency: eta_C = 1 - T_L/T_H (absolute temperatures). No engine operating between two reservoirs can exceed Carnot efficiency. Real cycles have irreversibilities: heat transfer across finite delta T, friction, non-isentropic compression/expansion. Carnot is the reversible limit - the theoretical maximum.

**Push:** "If a power plant claims 50% efficiency with T_H = 800 K and T_L = 300 K, is it possible?" → "Carnot limit is 1 - 300/800 = 62.5%. So 50% is theoretically possible but very high for a real plant. Typical modern combined-cycle plants achieve 55-60%; individual Rankine cycles are 35-45%."

**Trap:** Using Celsius temperatures in Carnot formula. Must use absolute (Kelvin) temperatures.

**What they're really testing:** Whether you can apply the Carnot limit to assess claimed performance, and understand why real plants fall short.

### Q4. Heat engine, heat pump, refrigerator, chiller - and COP relations. [H]

**A:** Heat engine: converts heat to work, eta = W_net/Q_H. Heat pump: moves heat from cold to hot for heating, COP_HP = Q_H/W = 1/(1 - T_L/T_H). Refrigerator: moves heat from cold space for cooling, COP_R = Q_L/W = T_L/(T_H - T_L). Chiller: large-scale refrigeration for process/AC, same COP as refrigerator. COP_HP = COP_R + 1.

**Push:** "Why is COP_HP always greater than 1?" → "Because Q_H = Q_L + W, so COP_HP = (Q_L + W)/W = COP_R + 1 > 1. You get more heat energy out than the electrical energy put in, because you're also using the heat that would otherwise be wasted."

**Trap:** Confusing COP of heat pump with efficiency of heat engine. Efficiency <= 1; COP can > 1.

**What they're really testing:** Whether you can distinguish between engine efficiency and heat pump/refrigerator COP, and connect it to why heat pumps are efficient for heating.

### Q5. Define entropy. When does it increase? [H]

**A:** Entropy is a measure of molecular disorder or energy dispersal. Defined as dS = dQ_rev/T. Second law: for any process in an isolated system, delta S >= 0. Entropy increases because of irreversibilities: friction (converts mechanical energy to heat), unrestrained expansion (gas expands into vacuum), heat transfer across finite temperature difference (never 100% efficient). The equality dS = dQ_rev/T applies only to reversible processes.

**Push:** "What is entropy generation in a throttling process?" → "Throttling is isenthalpic (delta H = 0) but irreversible. Entropy increases as pressure drops with no work output. This is why throttling is used for refrigerant expansion in refrigeration cycles - it's the practical way to generate entropy (and cooling)."

**Trap:** Saying entropy increases because "disorder increases" without linking to irreversibility. The statistical definition (disorder) is valid, but the thermodynamic definition links to heat transfer and irreversibility.

**What they're really testing:** Whether you understand entropy generation, not just entropy change, and can identify irreversible processes.

### Q6. Isothermal, isobaric, isochoric, and isentropic processes. [H]

**A:** Isothermal: temperature constant (PV = constant for ideal gas, delta U = 0, Q = W). Isobaric: pressure constant (V/T = constant, Q = delta H). Isochoric: volume constant (P/T = constant, Q = delta U). Isentropic: entropy constant, reversible adiabatic (PV^gamma = constant for ideal gas, adiabatic + no irreversibilities).

**Push:** "In which process is heat transfer zero?" → "Isentropic (by definition, reversible adiabatic). Note: adiabatic means no heat transfer, but not all adiabatic processes are isentropic - irreversible adiabatic processes generate entropy."

**Trap:** Confusing isentropic with adiabatic. Irreversible adiabatic is not isentropic.

**What they're really testing:** Whether you can distinguish between process types and know the key relationships for each.

### Q7. Steam tables and Mollier chart when to use each. [H]

**A:** Steam tables: tabulated thermodynamic properties (h, s, v, u) at discrete pressures and temperatures - use for precise interpolation in calculations. Mollier chart: h-s diagram with constant pressure, temperature, quality lines - use for quick visual estimation of cycle states, turbine expansion paths, and quality at exhaust. Both cover saturated and superheated regions.

**Push:** "How do you find enthalpy at a state between tabulated values?" → "Linear interpolation in steam tables. On Mollier chart, read directly from the plotted lines for the given pressure and quality."

**Trap:** Using saturated steam tables for superheated conditions. Steam tables have separate sections for saturated and superheated; using the wrong section gives wrong values.

**What they're really testing:** Whether you know your tools for getting property values, and when precision vs. estimation is appropriate.

### Q8. Dry steam, wet steam, and quality (dryness fraction). [H]

**A:** Dry steam: quality x = 1, all vapour. Wet steam: 0 < x < 1, mixture of vapour and liquid. Quality: x = mass of vapour / total mass. Measured by throttling calorimeter: throttle wet steam to low pressure where it becomes superheated, measure temperature, use h1 = h2 to find x from h_fg. Also separating calorimeter (measures liquid separated) or combined separating-throttling for very wet steam.

**Push:** "Why must throttling be to a pressure where steam is superheated?" → "To ensure temperature is uniquely defined for the enthalpy. In the two-phase region, temperature depends only on pressure, not enthalpy. Throttling to superheated regime gives a unique temperature reading."

**Trap:** Saying quality is measured by temperature alone. Temperature in the two-phase region depends only on pressure, not on how much vapour is present.

**What they're really testing:** Whether you can explain steam quality measurement and the difference between dry, wet, and superheated steam.

---

# Part 2. Strength of Materials - 10 questions

### Q9. Difference between stress and strain, units, Hooke's law. [H]

**A:** Stress (sigma) is internal resistance per unit area, units N/m2 or Pa. Strain (epsilon) is deformation per unit length, dimensionless. Hooke's law: sigma = E * epsilon in the linear elastic region, where E is Young's modulus. Key distinction: stress is force/area (pressure-like), strain is change in length/original length (ratio).

**Push:** "If you double the load on a steel rod in the elastic range, what happens to strain?" → "Strain doubles - linear proportionality holds until the proportional limit. The key insight is that 'linear' means stress and strain change together - double one, double the other."

**Trap:** Stating stress has units of "N" instead of "N/m2" or confusing engineering strain with true strain (engineering strain = delta_L/L_0; true strain = integral(dL/L)).

**What they're really testing:** Whether you can distinguish stress (intensity) from strain (deformation ratio), and know the units.

### Q10. Sketch stress-strain curve for mild steel, label key points. [H]

**A:** Linear elastic (OA) -> proportional limit (P) -> elastic limit (E) -> upper yield point (Y_u) -> lower yield point (Y_l) -> plastic region with strain hardening -> ultimate tensile strength (U) -> necking -> fracture (F). Ductility = strain at fracture; toughness = area under curve; resilience = area up to elastic limit; stiffness = slope in elastic region (E).

**Push:** "Where does the 0.2% proof stress sit on this curve?" → "It's the stress at 0.2% plastic strain offset from origin - used for materials without a clear yield point like aluminium."

**Trap:** Calling the proportional limit and elastic limit the same point, or saying necking starts at yield. Necking starts after UTS.

**What they're really testing:** Whether you can sketch and label the full curve, and distinguish between the various points.

### Q11. Main types of stress, practical example of each. [H]

**A:** Normal stress (tensile/compressive) - rod in tension. Shear stress - rivet in single shear, shaft in torsion. Bearing stress - bolt bearing on plate hole. Punching shear - hole punching operation. Bending stress - beam fibers. Thermal stress - constrained expansion.

**Push:** "What is the shear stress distribution in a circular shaft under torsion?" → "Linear from zero at centre to maximum at surface, tau = T*r/J."

**Trap:** Confusing bearing stress with compressive stress (bearing is localised contact pressure, not uniform compression).

**What they're really testing:** Whether you can name stress types and give practical examples - not just memorizing definitions.

### Q12. Allowable stress and factor of safety. How choose FoS in practice. [H]

**A:** Allowable stress = yield stress (or UTS) / factor of safety (FoS). FoS choice depends on: loading type (static vs dynamic/impact), material reliability (homogeneous steel vs casting), consequence of failure (safety critical vs redundant), service temperature (creep), code requirements (IS 800, ASME), manufacturing uncertainty (weld quality, residual stress), inspection access.

**Push:** "What typical FoS for a static steel structure per IS 800?" → "Around 1.5 to 1.67 on yield strength for limit state design. Older working stress codes used ~1.5-2.0."

**Trap:** Giving a single number like "FoS = 2" without context, or using UTS instead of yield for ductile materials. Ductile materials typically use yield-based FoS; brittle materials use UTS-based.

**What they're really testing:** Whether you understand FoS is a *judgement* about consequences and uncertainties, not a universal constant.

### Q13. von Mises and Tresca failure theories. Which more conservative? [H]

**A:** Von Mises (distortion energy): yielding when distortional strain energy reaches yield value; equivalent stress sigma_vm = sqrt(0.5*[(sigma1-sigma2)^2 + (sigma2-sigma3)^2 + (sigma3-sigma1)^2]). Tresca (max shear): yielding when max shear stress reaches shear yield = 0.5*sigma_y; equivalent stress = sigma1 - sigma3. Tresca is more conservative (predicts yielding earlier) - its yield locus is inscribed inside von Mises ellipse. Von Mises matches ductile metal test data better.

**Push:** "For pure shear, what does each theory predict as yield stress in shear?" → "Tresca: tau_y = 0.5*sigma_y. Von Mises: tau_y = 0.577*sigma_y."

**Trap:** Saying von Mises is always more conservative, or mixing up which is the inner/outer locus. Tresca is the inner (more conservative) locus.

**What they're really testing:** Whether you know both theories, which is more conservative, and can apply each correctly.

### Q14. A 20 mm diameter steel rod carries 50 kN tensile load. Calculate tensile stress. [H]

**A:** Area = pi/4 * 20^2 = 314.16 mm2. Stress = 50000 N / 314.16 mm2 = 159.2 MPa. This is well below mild steel yield (~250 MPa) so elastic.

**Push:** "If the rod is 2 m long and E = 200 GPa, what is the elongation?" → "Strain = 159.2/200000 = 7.96e-4. delta = strain * L = 1.59 mm."

**Trap:** Forgetting to convert mm2 to m2, or using diameter instead of radius in area formula. Common error: area = pi*d^2/4 vs pi*d^2.

**What they're really testing:** Whether you can do the numerical correctly, and show the reasoning (not just the final number).

### Q15. Compare solid and hollow shafts of same material and weight for torsional strength. [H]

**A:** For same weight and length, hollow shaft has larger polar moment J (material concentrated at larger radius). Torsional strength proportional to J/r_o. Hollow shaft is stronger and stiffer in torsion. Typical: hollow shaft with d_i/d_o = 0.5 to 0.7 gives 30-50% more torque capacity than solid of same weight.

**Push:** "Why not make the wall infinitely thin?" → "Buckling risk, manufacturing limits, local denting, critical speed concerns. Also, if wall too thin, local yielding occurs at inner surface."

**Trap:** Saying solid shaft is stronger because "more material" or confusing polar moment J with second moment I (area moment, not polar).

**What they're really testing:** Whether you understand polar moment distinction and why hollow can be stronger per weight.

### Q16. State bending stress formula and define each term. [H]

**A:** sigma = M*y/I. M = bending moment at section, y = distance from neutral axis to fiber, I = second moment of area about neutral axis. Valid for: pure bending (constant M), plane sections remain plane, material linear elastic, symmetric cross-section or principal axes.

**Push:** "Where is maximum bending stress in a simply supported beam with UDL?" → "At midspan, top and bottom fibers (M_max = wL^2/8, y = c)."

**Trap:** Using I about wrong axis, or forgetting y is measured from neutral axis (not top/bottom arbitrarily). Common error: using full depth instead of distance from NA.

**What they're really testing:** Whether you can state the formula correctly and define each term, not just memorize.

### Q17. Derive torsional shear stress formula tau = T*r/J. [H]

**A:** Key steps: 1) Assume plane sections remain plane and rotate rigidly (no warping for circular section). 2) Shear strain gamma = r*theta/L (theta = angle of twist). 3) Hooke's law in shear: tau = G*gamma. 4) Elemental torque dT = tau * r * dA. 5) Integrate: T = G*theta/L * integral(r^2 dA) = G*theta*J/L. 6) Substitute back: tau = T*r/J.

**Push:** "Why doesn't this work for non-circular sections?" → "Warping occurs - cross-sections don't remain plane. Need St. Venant's torsion theory for non-circular sections."

**Trap:** Using J = pi*d^4/32 for hollow shaft (correct is pi*(d_o^4 - d_i^4)/32) or confusing J with I (second moment area, not polar).

**What they're really testing:** Whether you can give the key derivation steps, not every algebraic detail.

### Q18. List five ways to reduce deflection of a cantilever beam. [H]

**A:** 1) Increase Young's modulus E (change material), 2) Increase second moment I (deeper section, I-beam vs rectangle), 3) Reduce span L (most effective - L^3 or L^4 dependence), 4) Add intermediate support (convert to propped cantilever), 5) Change section profile (tapered, haunched, or pre-camber). Also: reduce load, use composite action.

**Push:** "Which is most effective per unit cost?" → "Reducing span or increasing depth (I ~ depth^3) usually best. Pre-camber only offsets, doesn't change stiffness."

**Trap:** Listing "increase thickness" without specifying where (flange vs web matters), or saying "increase FoS" (FoS doesn't reduce deflection, it increases strength).

**What they're really testing:** Whether you know deflection depends on L^3 or L^4, and which modifications actually change stiffness.

---

# Part 3. Fluid Mechanics and Piping - 10 questions

### Q19. Continuity equation for steady incompressible flow. [H]

**A:** For steady flow, mass entering = mass leaving. For incompressible flow, rho is constant, so rho*A1*v1 = rho*A2*v2, giving A1*v1 = A2*v2 or Q = A*v = constant. For branching pipe with one inlet and multiple outlets: Q_in = Q_out1 + Q_out2 + ...

**Push:** "If a 200 mm pipe splits into two 150 mm pipes and velocity in one branch is 3 m/s, what is the velocity in the other branch if total flow is 0.1 m3/s?" → "Q_total = 0.1 m3/s. Q1 = (pi/4)*0.15^2*3 = 0.053 m3/s. Q2 = 0.1 - 0.053 = 0.047 m3/s. v2 = Q2/A2 = 0.047/0.0177 = 2.66 m/s."

**Trap:** Applying A1*v1 = A2*v2 to each branch individually without conserving total mass. Must conserve total inlet flow.

**What they're really testing:** Whether you can apply mass conservation to simple piping systems and branch connections.

### Q20. Bernoulli's equation, assumptions, derivation from Euler. [H]

**A:** Bernoulli: p/rho*g + v^2/2g + z = constant along a streamline. Assumptions: steady flow, incompressible fluid, inviscid (no friction), along a single streamline, no energy addition/removal (no pump/turbine between points). Derivation from Euler: Start with Euler's equation along a streamline: dp/rho + v*dv + g*dz = 0. Integrate: int(dp/rho) + v^2/2 + gz = constant. For incompressible flow, int(dp/rho) = p/rho, giving p/rho + v^2/2 + gz = constant.

**Push:** "Can you apply Bernoulli across a pump?" → "No, because a pump adds energy. You need the extended Bernoulli with head added: p1/rho*g + v1^2/2g + z1 + H_pump = p2/rho*g + v2^2/2g + z2 + h_loss."

**Trap:** Applying Bernoulli between points in different streamlines, or across a valve/pump without accounting for losses or work.

**What they're really testing:** Whether you know the assumptions that limit Bernoulli's applicability, and can extend it for real systems.

### Q21. Venturi meter principle and discharge coefficient. [H]

**A:** Venturi meter measures flow rate by creating a pressure drop through a converging section. From Bernoulli and continuity: Q = Cd * A2 * sqrt(2*(p1-p2)/rho*(1 - (A2/A1)^2)). Cd accounts for viscous losses and non-uniform velocity profiles. Typical Cd = 0.95-0.98 for venturi, lower for orifice (0.6-0.65) because sudden contraction causes flow separation and vena contracta.

**Push:** "Why is pressure recovery better in a venturi than an orifice plate?" → "Venturi has a gradual diffuser (7-15 deg angle) that prevents boundary layer separation, recovering 80-90% of pressure drop. Orifice has sudden expansion causing massive separation and only 30-50% recovery."

**Trap:** Assuming Cd = 1 for calculations, or confusing venturi Cd with orifice Cd.

**What they're really testing:** Whether you understand flow measurement principles and why Cd < 1, not just plugging formulas.

### Q22. Reynolds number, laminar/transition/turbulent pipe flow. [H]

**A:** Re = rho*v*D/mu = v*D/nu. Ratio of inertial forces to viscous forces. Pipe flow: laminar below Re = 2300, transition 2300-4000, turbulent above 4000. At transition, flow changes from orderly layers to chaotic eddies, velocity profile flattens from parabolic to nearly uniform, and friction factor jumps from 64/Re to a higher value on the Moody chart.

**Push:** "Why is the critical Re for pipe flow 2300 but for flat plate boundary layer it is 5e5?" → "Different geometries and instability mechanisms. Pipe flow is confined and becomes unstable to small disturbances at lower Re. Flat plate boundary layer transitions due to Tollmien-Schlichting waves amplified by freestream turbulence."

**Trap:** Using Re = 2300 as a sharp boundary - it is a range, and actual transition depends on pipe roughness, inlet conditions, and disturbances.

**What they're really testing:** Whether you understand Re as a dimensionless group, and that transition is a range dependent on conditions.

### Q23. Darcy-Weisbach equation and friction factor. [H]

**A:** h_f = f * (L/D) * (v^2/2g). For laminar flow: f = 64/Re exactly. For turbulent flow, f depends on Re and relative roughness (epsilon/D). Use Moody chart or Colebrook equation: 1/sqrt(f) = -2*log10(epsilon/(3.7*D) + 2.51/(Re*sqrt(f))). For smooth pipes, Blasius approximation: f = 0.316/Re^0.25 (valid 4000 < Re < 1e5).

**Push:** "What happens to head loss if you double the flow rate in turbulent flow?" → "v doubles, so v^2 quadruples. f changes slightly (decreases with Re^0.25), but overall h_f increases by roughly 3.5-4 times. In laminar flow, h_f is linear with v (since f = 64/Re), so doubling v doubles h_f."

**Trap:** Using f = 64/Re for turbulent flow, or ignoring the Re-dependence of f in turbulent regime.

**What they're really testing:** Whether you know laminar vs turbulent friction factor behavior, and can estimate head loss changes.

### Q24. Minor losses, K values, equivalent length. [M]

**A:** Minor losses are head losses from fittings, valves, bends, expansions, contractions: h_m = K * v^2/2g. K is dimensionless loss coefficient (e.g., 0.5 for 90° elbow, 10 for fully open globe valve, 1.0 for sudden expansion). Equivalent length Le = K*D/f converts minor loss to an equivalent straight pipe length with same friction loss. Total loss = f*(L/ D)*v^2/2g + sum(K)*v^2/2g.

**Push:** "Why does a sudden expansion have K = (1 - A1/A2)^2 while sudden contraction K is smaller?" → "Sudden expansion causes flow separation and massive eddies (Borda-Carnot loss). Sudden contraction has vena contracta but flow reattaches smoothly, so loss is mainly from expansion after vena contracta."

**Trap:** Forgetting minor losses in short pipe systems where they can dominate, or using K values for the wrong velocity (upstream vs downstream).

**What they're really testing:** Whether you account for fittings and valves in real piping systems, not just straight pipe.

### Q25. Pitot tube, velocity measurement. [H]

**A:** Pitot tube faces upstream, measuring stagnation pressure (p0 = p_static + rho*v^2/2). A simple Pitot tube needs a separate static pressure tap. A Pitot-static tube combines both in one instrument with static ports on the side. Velocity v = sqrt(2*(p0 - p_static)/rho).

**Push:** "If a Pitot tube reads 150 mm water gauge above static pressure in air at 1.2 kg/m3, what is the velocity?" → "delta_p = rho_water*g*h = 1000*9.81*0.15 = 1471.5 Pa. v = sqrt(2*1471.5/1.2) = 49.5 m/s."

**Trap:** Using the Pitot tube reading directly as velocity pressure without subtracting static pressure, or using the wrong density (air vs water).

**What they're really testing:** Whether you can apply the Pitot-static principle to calculate velocity from pressure measurements.

### Q26. Boundary layer separation, drag increase. [M]

**A:** Boundary layer separation occurs when adverse pressure gradient (dp/dx > 0) causes flow near wall to reverse. The separation point creates a wake of low-pressure recirculating flow behind the body. Pressure drag increases because rear pressure stays low while front stagnation pressure remains high. Streamlining delays separation by maintaining favorable or mild adverse gradient, keeping flow attached longer, reducing wake size and pressure drag. Friction drag increases slightly but net drag drops.

**Push:** "Why does a golf ball have dimples?" → "Dimples trigger early transition to turbulent boundary layer, which has more momentum near the wall and resists separation better than laminar layer. This moves separation point rearward, shrinking the wake and reducing pressure drag significantly despite higher skin friction."

**Trap:** Thinking streamlining only reduces skin friction - its main benefit is reducing pressure drag by delaying separation.

**What they're really testing:** Whether you understand boundary layer separation as a pressure-drag mechanism, not just a friction effect.

### Q27. Cavitation in pumps, NPSH. [H]

**A:** Cavitation occurs when local pressure drops below vapour pressure, bubbles form and collapse violently. Causes: NPSH_a < NPSH_r (available < required). NPSH_a = (p_suction - p_vapor)/rho*g + v^2/2g. Prevention: increase suction pressure (raise supply tank), reduce fluid temperature (lower vapour pressure), use pump with lower NPSH_r (larger impeller eye, lower speed), install booster pump.

**Push:** "How do you prevent cavitation in a pump installation?" → "Increase suction pressure (raise supply tank, reduce suction line losses), reduce fluid temperature (lower vapour pressure), use pump with lower NPSHr (larger impeller eye, lower speed), install booster pump."

**Trap:** Thinking cavitation only happens at the impeller eye - it can also occur in valve seats, propeller blades, and turbine runners.

**What they're really testing:** Whether you understand the NPSH concept and cavitation mechanism, not just the definition.

---

# Part 4. Theory of Machines - 8 questions

### Q28. Degrees of freedom in planar mechanism, Kutzbach criterion. [H]

**A:** Degrees of freedom (DOF) is the number of independent parameters needed to define position of all links. For planar mechanisms, Kutzbach formula: F = 3(n-1) - 2*j1 - j2, where n = number of links, j1 = lower pairs (revolute/prismatic), j2 = higher pairs (cam/gear). F > 0 means unconstrained motion, F = 0 is a structure, F < 0 is overconstrained (preloaded).

**Push:** "What is the DOF of a four-bar linkage?" → "n=4, j1=4 -> F = 3(3) - 2(4) = 1. It has one input, fully defined."

**Trap:** Using the spatial formula F = 6(n-1) - 5j1 - 4j2... for planar mechanisms - that's for 3D, not planar.

**What they're really testing:** Whether you can calculate DOF for planar mechanisms and interpret the result.

### Q29. Grashof's law for four-bar linkage. [H]

**A:** For a four-bar with links s (shortest), l (longest), p, q (intermediate): if s + l <= p + q, the shortest link can fully rotate - Grashof condition satisfied. Four cases: (1) s is ground link -> double crank (drag link), both cranks rotate fully. (2) s is coupler -> double rocker, no full rotation. (3) s is adjacent to ground -> crank-rocker, one crank one rocker. (4) s is opposite ground -> rocker-crank, same as case 3 but inverted. If s + l > p + q, it's a non-Grashof double rocker.

**Push:** "How do you quickly identify which link is the crank?" → "The link adjacent to ground that can rotate 360 deg is the crank; the other moving link is the rocker."

**Trap:** Confusing which link is s or l, or forgetting that Grashof is necessary but not sufficient - you also need to check assembly mode.

**What they're really testing:** Whether you can apply Grashof's law to classify four-bar linkages, and identify the input link.

### Q30. Crank-rocker mechanism, applications. [H]

**A:** Crank-rocker is a Grashof four-bar where the shortest link is adjacent to ground. The shortest link (crank) rotates fully; the opposite link (rocker) oscillates. Converts continuous rotation to reciprocating oscillation. Used in windshield wipers, sewing machine needle drive, pump reciprocating mechanisms, packaging machines.

**Push:** "How do you change the rocker's stroke angle?" → "Change the link lengths - longer coupler or rocker increases stroke, but check Grashof still holds."

**Trap:** Saying crank-rocker gives linear motion - it gives angular oscillation; slider-crank gives linear.

**What they're really testing:** Whether you understand the crank-rocker function and can identify applications.

### Q31. Quick-return mechanism, Whitworth. [M]

**A:** Quick return mechanism makes the forward (working) stroke slower and the return stroke faster. Achieved by offsetting the crank centre or using Whitworth mechanism. Time ratio (forward/return) > 1. Used in shapers, slotters, planers, printing presses, broaching machines - any tool where cutting happens in one direction only.

**Push:** "What is the time ratio for a standard Whitworth quick return?" → "Time ratio = (180 + alpha) / (180 - alpha) where alpha is the angle between the two extreme crank positions."

**Trap:** Confusing quick return with constant velocity - the whole point is unequal speeds.

**What they're really testing:** Whether you understand quick-return motion and can apply it to reciprocating machinery.

### Q32. Straight-line motion mechanisms. [M]

**A:** Mechanisms that generate exact or near-exact straight-line motion from rotary input. Exact: Peaucellier cell (8 links, inversor), Hart's A-frame (6 links). Approximate: Watt's linkage (3 links, straight line near centre), Chebyshev linkage, Robert's mechanism. Used in early steam engine crossheads, suspension systems, robot end-effector guidance.

**Push:** "Why did Watt's linkage replace the Peaucellier in practice?" → "Peaucellier is exact but complex (8 links, more joints, wear); Watt's is 3 links, good enough for limited travel."

**Trap:** Saying all straight-line mechanisms are exact - most practical ones are approximate.

**What they're really testing:** Whether you know the common straight-line mechanisms and can distinguish exact from approximate.

### Q33. Cams and followers - key terms. [H]

**A:** Cams: radial (disc) or cylindrical. Followers: translating (radial/offset) or oscillating. Follower faces: knife-edge (sharp, high wear), roller (low friction, common), flat-faced (simple, high contact stress), spherical-faced. Cam profile is the envelope of follower positions for the desired motion curve. Given follower motion (displacement vs cam angle), you invert the motion to generate cam surface - each profile point is the follower centre at that angle.

**Push:** "Why use a roller follower over knife-edge?" → "Roller reduces friction and wear, allows higher speeds; knife-edge wears fast and jams."

**Trap:** Thinking cam profile = follower displacement curve - they are different; profile is the physical surface.

**What they're really testing:** Whether you understand cam-follower kinematics and can specify follower types.

### Q34. SHM, cycloidal, constant velocity motion profiles for cams. [H]

**A:** SHM: simple sine displacement, smooth velocity/acceleration, but infinite jerk at start/end - causes vibration. Cycloidal: sine acceleration, zero jerk at boundaries, smoothest, best for high speed. Constant velocity: infinite acceleration at boundaries (impossible physically), only for very slow cams. Cycloidal is standard for high-speed cams; SHM for moderate; constant velocity avoided except for dwell transitions.

**Push:** "Which profile gives minimum maximum acceleration for a given lift and duration?" → "Cycloidal - its acceleration is sinusoidal with lower peak than SHM."

**Trap:** Using constant velocity for high-speed cams - causes infinite jerk, destroys mechanism.

**What they're really testing:** Whether you know motion profile comparisons and can select the right one for given speed requirements.

### Q35. Pressure angle in cam, effect on performance. [M]

**A:** Pressure angle is the angle between the follower motion direction and the normal to the cam profile at the contact point. High pressure angle -> high side thrust on follower -> increased friction, wear, bending stress, possible jamming. Limit: < 30 deg for translating followers, < 35-40 deg for oscillating. Increase base circle radius or reduce lift to reduce pressure angle.

**Push:** "What happens if pressure angle exceeds 45 deg?" → "Side thrust exceeds normal force - follower binds, chatters, or jumps; cam may need spring preload which increases wear."

**Trap:** Ignoring pressure angle when designing high-lift cams - it's the primary limit on lift for a given base circle.

**What they're really testing:** Whether you understand pressure angle as the primary constraint on cam design, not just a geometric parameter.

---

# Part 5. Machine Design - 8 questions

### Q36. Design a shaft. What are you checking? [H]

**A:** Three things: Strength (from combined bending and torsion, using equivalent twisting moment with bending term weighted by ~0.75 for fluctuating loading). Stiffness (deflection ruins alignment, changes bearing preload, sets up vibration). Fatigue (running shaft sees fluctuating bending at surface even if load steady). Common materials: EN8 for general shafts, EN24 (AISI 4140/4340) for high strength, 20MnCr5 carburised for gear shafts, nitrided steel for wear/corrosion-resistant grades.

**Push:** "Why size a shaft on stiffness first?" → "Because deflection is often what actually ends the service - it causes coupling misalignment, bearing preload changes and vibration - and it is less sensitive to load assumptions than strength."

**Trap:** Designing on strength alone and producing a shaft that is strong but floppy and vibrating.

**What they're really testing:** Whether you treat design as a sequence with stiffness first, not just strength.

### Q37. Shaft with bending moment M and torque T. Size it. [H]

**A:** Equivalent twisting moment: T_eq = sqrt(T^2 + (0.75 M)^2) for fluctuating/fully reversed bending; sqrt(T^2 + M^2) for steady bending. Design shear stress: tau = 16 T_eq / (pi d^3). ASME code form writes allowable bending moment directly. In both cases diameter goes as cube root of the load, so 10% load increase needs only ~3% more diameter.

**Push:** "And where does the ASME form come from?" → "It comes from the same beam and torsion relations, rearranged so that instead of finding the stress for a given moment you find the moment the section can carry. Because diameter enters as d^3 for strength and d^4 for deflection, a slightly larger diameter buys a lot."

**Trap:** Using d^3 strength relation for deflection or d^4 relation for stress. Deflection is much more sensitive to diameter, which is why stiffness often governs.

**What they're really testing:** Whether you can combine loads on a real shaft and know why the diameter relation is cubic, not linear.

### Q38. Key types, sizing, how key fails. [H]

**A:** Common types: saddle key (weakest - deep engagement but thin section, crushes and wears quickly), flat (sunk or Gib-head) key (standard, large contact area, keeps key seat shallow), round key (used on tapered shaft), spline (strongest). Size a key by taking shaft diameter to standard table, which fixes width b and height h. Check two failures: shearing of the key, tau = F/(b l) with shear plane at mid-length, and crushing of the key or the hub, sigma_c = 2F/(h l) using half the key height that bears on the hub. Some handbooks write double-shear forms 2F/(b l) and 4F/(h l) - geometry decides, state your assumption.

**Push:** "Why is there clearance between the key and the shaft?" → "So the key can be slid in and out for assembly and replacement and the hub can be positioned axially; an interference fit would need broaching after assembly. It also lets the shaft be made slightly undersize at the keyway, and the keyway itself weakens the shaft, so the shaft is often stepped up by ~5 to 10 percent at the keyway."

**Trap:** Saying a saddle key is the strongest because it sits deepest. Depth without section area gives crushing and wear, not strength.

**What they're really testing:** Whether you know key types, sizing methodology, and failure modes.

### Q39. Splines, pins and cotters. [M]

**A:** Spline is many-toothed connection used where a key cannot carry the torque or where accurate angular positioning is needed - machine tool spindles, gear shafts, piston rod of hydraulic cylinder. Gives highest torque capacity and best angular location of three types; made by milling with cutter (flank generation) or by broaching (form generation, more accurate). Pins and cotters used to lock parts axially against each other on a shaft: taper pin wedged in to lock two parts; split tapered pin called cotter with castellated nut is classic way to stop a nut working loose. Taper pin fails in shear or bending; cotter fails by working loose or by bending, needs periodic checking.

**Push:** "Spline or key - how choose?" → "Splines when the torque is high, the hub must be located accurately, or the hub must slide along the shaft; a key when the torque is modest, the cost matters and axial sliding is needed."

**Trap:** Confusing a pin and a cotter with a dowel. A dowel resists shear between two parts; a pin or cotter resists axial movement of a part on a shaft.

**What they're really testing:** Whether you know standard ways of transmitting torque and locking parts axially, and can choose each appropriately.

### Q40. Types of couplings, what each handles. [H]

**A:** Three families: Rigid couplings (flange or sleeve type) - connect two shafts and take no misalignment at all; cheap, stiff, backlash-free, suit well-aligned, low-speed shafts. Flexible couplings take up misalignment: pin and bush takes angular and parallel misalignment; jaw takes angular only; grid and coil-spring take parallel misalignment; chain takes parallel and angular plus shock; flexible disc or double cardan takes angular, parallel and axial plus torsion. Universal couplings - Hooke's joint and CV joint - take large angular misalignment between intersecting axes. Rule: rigid takes nothing; pin-bush or chain takes angular and parallel but not much axial; only flexible disc coupling takes all three plus twist.

**Push:** "Why does a rigid coupling still fail in service?" → "Misalignment. Even a small angle puts bending into the bolts and the shaft ends, and that bending is not in anyone's calculation; it is what actually cracks couplings and wears bearings. Also, a Hooke's joint gives velocity fluctuation at high speed and is limited to small angles, while the CV joint runs at constant velocity and handles larger angles."

**Trap:** Fitting a rigid flange coupling between shafts that are not perfectly aligned, or assuming a Hooke's joint is a constant-velocity joint like a CV.

**What they're really testing:** Whether you match the coupling to the misalignment you actually have, and know that rigid is not the same as good.

### Q41. Flat belt vs V-belt. When use each. [H]

**A:** V-belt transmits much more power in same space because it wedges in the pulley groove. The wedge multiplies the normal force on the belt, so effective coefficient of friction is mu / sin(alpha/2) - about 3 times mu for a 40 deg groove. V-belt can carry roughly 2 to 3 times the power of a flat belt of same width, at higher speed, because it sits deeper and will not creep off the pulley. Flat belt still used where pulley must be wide, where machine has to handle reverse running or act as slipping clutch, and where drive is small and cheap. Both have weakness: need tensioning and they slip.

**Push:** "What is the biggest limitation of a belt drive?" → "It must be kept tensioned, its life is short compared with a gear, it needs a guard, and slip means the speed ratio is never exact."

**Trap:** Saying the V-belt works by friction on the bottom of the belt. The bottom is not in contact - it is the side faces of the V that wedge.

**What they're really testing:** Whether you can pick between belt and chain on the basis of the working environment, and know the numbers that drive the choice.

### Q42. Roller chain drives - pitch, sprocket, lubrication. [M]

**A:** Roller chain identified by pitch: 08B-1 has pitch of 12.7 mm and ANSI 40 chain has same half-inch pitch. Sprocket teeth cut to match, with pitch circle diameter D = p / sin(180/Z). Chain pull: T1 - T2 = 1025 P newtons with P in kW, so 5 kW needs about 5.1 kN across the chain. Lubrication: grease below ~1.5 m/s, drip oil up to ~6 m/s, oil bath or spray above that. Prefer chain to belt in dirty, dusty or oily plant conditions, because chain does not slip, can be enclosed and lubricated, and carries high torque at low speed over small centre distance. Price is noise, weight, sprocket wear and need for lubrication.

**Push:** "How does a silent chain differ from a roller chain?" → "Silent or block chain has teeth engaging in pockets of nearly continuous plate, so it is quieter, runs faster and needs less lubrication, but it is heavier and costlier."

**Trap:** Using a belt where the plant atmosphere is dusty and oily - a belt slips and glazes, and the drive will not hold its ratio.

**What they're really testing:** Whether you can pick between belt and chain on the basis of the working environment, and whether you know the numbers that drive the choice.

---

# Part 6. Engineering Mechanics - 6 questions

### Q43. Free body diagram, why every solution starts with one. [H]

**A:** FBD isolates a body (or system) and shows ALL external forces and moments acting on it - applied loads, reactions at supports, weight, friction. It separates the body from its surroundings so equilibrium equations apply only to the body of interest. Missing a force on FBD = wrong answer. Always draw FBD first, label knowns/unknowns, then write equilibrium equations.

**Push:** "What forces do you NOT put on an FBD?" → "Internal forces (between parts of the system), forces the body exerts ON other bodies, accelerations (unless doing d'Alembert)."

**Trap:** Forgetting weight, or putting internal forces on the FBD of the whole system.

**What they're really testing:** Whether you can draw a correct FBD - the foundation of all mechanics solutions.

### Q44. Three equilibrium equations for 2D and 3D. [H]

**A:** 2D: Sum Fx = 0, Sum Fy = 0, Sum Mz = 0 (about any point). 3D: Sum Fx = 0, Sum Fy = 0, Sum Fz = 0, Sum Mx = 0, Sum My = 0, Sum Mz = 0. For 2D, you can replace one force equation with a moment equation about a different point (three independent equations total). Choose moment centres to eliminate unknowns.

**Push:** "Can you solve a 2D problem with three moment equations?" → "Yes, if the three moment centres are not collinear."

**Trap:** Using Sum M = 0 about a point where all unknown forces pass through - gives 0 = 0, no info.

**What they're really testing:** Whether you know the equilibrium equations and can choose independent moment centres.

### Q45. Two-force and three-force members. [M]

**A:** Two-force member: only two forces act on it (at ends). Forces must be equal, opposite, and collinear along the line joining the two points - pure tension/compression. Three-force member: three forces act. If in equilibrium, they must be concurrent (meet at a point) or parallel. Identifying these lets you find force directions immediately without solving - just geometry.

**Push:** "If a member has two forces and a moment applied, is it a two-force member?" → "No - the moment makes it a three-load member; forces need not be collinear."

**Trap:** Assuming all truss members are two-force members - only true if loads are applied ONLY at joints.

**What they're really testing:** Whether you can identify member types and use them to simplify force analysis.

### Q46. Resultant of coplanar non-concurrent forces, Varignon's theorem. [M]

**A:** Resultant R = vector sum of all forces. Its line of action is found by equating moments: M_R = Sum M_i about any point. Varignon's theorem: moment of a force about a point equals the sum of moments of its components about that point. A couple is a pair of equal opposite parallel forces separated by distance d - moment = F*d, free vector (same about any point). Resultant of non-concurrent system = single force + couple (or single force if resultant force not zero).

**Push:** "Can a system of parallel forces have a resultant couple?" → "Yes, if the vector sum is zero but moments don't cancel - pure couple."

**Trap:** Treating a couple as a force at some point - it's a free vector, moment same everywhere.

**What they're really testing:** Whether you can find resultants and use Varignon's theorem to simplify moment calculations.

### Q47. Why net moment on rotating machine must be zero for steady operation. [H]

**A:** Net moment = I * alpha (Newton's second law for rotation). If net moment not zero, alpha != 0 -> angular acceleration -> speed changes. For steady speed (omega constant), alpha = 0, so net moment must be zero. Applied torque = sum of resisting torques (load, friction, windage). If not balanced, machine speeds up or slows down.

**Push:** "What happens if motor torque is slightly less than load torque at steady speed?" → "Motor decelerates until speed drops enough that load torque decreases (e.g., fan load ~omega^2) to match motor torque, or stalls."

**Trap:** Thinking zero net moment means no torque - it means driving torque equals resisting torque.

**What they're really testing:** Whether you understand rotational equilibrium and can connect it to real machine operation.

### Q48. Friction circle, self-locking, capstan equation. [H]

**A:** Friction circle: for a journal bearing, resultant reaction shifts by angle phi = arctan(mu) from normal; radius = r*sin(phi). Self-locking: when lead angle lambda <= friction angle phi, the screw/nut holds load without brake - condition tan(lambda) <= mu. Capstan equation (belt friction): T2/T1 = e^(mu*theta) where theta is wrap angle in radians. Explains why few wraps hold huge tension ratio.

**Push:** "For a screw jack with mu = 0.15 and lead angle 8 deg, is it self-locking?" → "tan(8deg) = 0.14 < 0.15 -> yes, self-locking."

**Trap:** Using degrees in capstan equation - theta must be in radians.

**What they're really testing:** Whether you can apply friction concepts to bearing design, screw jacks, and belt drives.

---

# Part 7. Thermal and Fluids Systems - 6 questions

### Q49. Heat transfer modes: conduction, convection, radiation. [H]

**A:** Conduction: Fourier's law q = -k*A*dT/dx. Heat transfer through molecular collisions in solids/stationary fluids without bulk motion. Convection: Newton's law q = h*A*(Ts - T_inf). Heat transfer between a surface and moving fluid combining conduction at the wall and advection in the bulk. Radiation: Stefan-Boltzmann q = epsilon*sigma*A*(Ts^4 - T_surr^4). Electromagnetic wave emission from matter above 0 K, no medium required, works in vacuum.

**Push:** "Which mode dominates in a vacuum?" → "Radiation only - conduction and convection require a material medium."

**Trap:** Calling convection "just conduction with fluid motion" - the advection term fundamentally changes the heat transfer mechanism and introduces dependence on flow velocity, geometry, and fluid properties.

**What they're really testing:** Whether you can distinguish the three modes and know their physical mechanisms.

### Q50. Critical radius of insulation. [H]

**A:** For a cylinder with convection outside, total resistance R_total = ln(r2/r1)/(2*pi*k*L) + 1/(h*2*pi*r2*L). Heat loss q = (T1-T_inf)/R_total. Differentiate q w.r.t r2 and set to zero: dR/dr2 = 0 gives 1/(k*r2) - 1/(h*r2^2) = 0 -> r_c = k/h. Below r_c (r2 < k/h): adding insulation DECREASES total resistance, INCREASES heat loss. Above r_c: adding insulation increases resistance, decreases heat loss. For sphere: r_c = 2k/h. Critical radius is small for typical insulations (k ~ 0.05, h ~ 10 -> r_c = 5 mm), so pipes larger than 10 mm OD always benefit from insulation.

**Push:** "Does critical radius exist for plane walls?" → "No, because conduction area is constant while convection area is also constant. For plane walls, adding insulation always increases resistance and decreases heat loss."

**Trap:** Thinking you should never insulate small pipes - for pipes below critical radius (rare), insulation increases heat loss, but these are typically not insulated anyway or have h very low (natural convection) making r_c larger.

**What they're really testing:** Whether you understand critical radius, when it applies, and why it differs between cylinders and plane walls.

### Q51. Nusselt number and Reynolds analogy. [M]

**A:** Nusselt number Nu = h*L/k = convection heat transfer / conduction heat transfer across the boundary layer. It represents the dimensionless temperature gradient at the wall. Reynolds analogy: St = Cf/2 where St = Nu/(Re*Pr) is Stanton number, Cf is skin friction coefficient. It links momentum transfer (friction) to heat transfer (convection) through boundary layer similarity. Valid for Pr approx 1 (gases).

**Push:** "For turbulent flow in a pipe, what correlation would you use for Nu?" → "Dittus-Boelter: Nu = 0.023*Re^0.8*Pr^n where n = 0.4 for heating, 0.3 for cooling. Valid for Re > 10000, 0.7 < Pr < 160, L/D > 60."

**Trap:** Using laminar correlations (Nu = 3.66 constant) for turbulent flow, or forgetting the Prandtl number exponent difference for heating vs cooling.

**What they're really testing:** Whether you understand Nusselt as a convection-conduction ratio, and can use appropriate correlations.

### Q52. Effectiveness-NTU method for heat exchanger. [M]

**A:** Effectiveness epsilon = actual heat transfer / maximum possible heat transfer = Q / (C_min*(Th_in - Tc_in)). NTU = U*A/C_min (number of transfer units). For any flow arrangement, epsilon = f(NTU, C_r) where C_r = C_min/C_max. Preferred when outlet temperatures are unknown (sizing problem) because LMTD requires iterative solution. Also useful for comparing exchanger performance independent of flow rates.

**Push:** "What is the maximum possible effectiveness for a counterflow exchanger?" → "epsilon_max = 1 when NTU -> infinity and C_r < 1. For C_r = 1, epsilon = NTU/(1+NTU) approaches 1 asymptotically. For parallel flow, epsilon_max = 1/(1+C_r) < 1."

**Trap:** Using LMTD when both outlet temperatures are unknown - it becomes an iterative trial-and-error problem. NTU method gives direct solution.

**What they're really testing:** Whether you know the effectiveness-NTU method is preferred for sizing problems, and can relate it to LMTD.

### Q53. Fouling factor, effect on heat exchanger performance. [M]

**A:** Fouling factor R_f = 1/h_foul is the additional thermal resistance from deposits on heat transfer surfaces (scale, corrosion, biological growth, particulates). Overall U_clean = 1/(1/hi + 1/ho + R_wall). U_fouled = 1/(1/hi + 1/ho + R_wall + R_fi + R_fo). Fouling reduces U, decreases heat transfer, increases pressure drop, requires larger area or higher flow rates. Typical values: cooling water 0.0002-0.0005 m2-K/W, steam condensate 0.0001, oil 0.0005-0.001.

**Push:** "How do you account for fouling in heat exchanger design?" → "Design with U_design = 1/(1/U_clean + R_f) or specify excess area (typically 15-30% over clean requirement). Include fouling factors from TEMA standards."

**Trap:** Ignoring fouling in design - a clean exchanger will meet duty initially but degrade rapidly in service.

**What they're really testing:** Whether you account for fouling as a design consideration, not just an operational issue.

### Q53. Economiser, superheater, condenser in boiler/steam cycle. [H]

**A:** Economiser: preheats feedwater using flue gas heat (lowest temperature heat recovery), improves cycle efficiency. Superheater: heats saturated steam to superheated state at constant pressure, increases turbine work and efficiency, prevents blade erosion from moisture. Condenser: condenses exhaust steam at constant pressure/temperature, rejects latent heat to cooling water, maintains low turbine back pressure (vacuum), returns condensate to cycle. In a boiler, the economiser is in the flue gas path after the superheater/reheater.

**Push:** "Why is the condenser pressure kept as low as possible?" → "Lower condenser pressure (higher vacuum) increases the enthalpy drop across the turbine, increasing work output and cycle efficiency. Typical condenser pressure: 0.03-0.08 bar (3-8 kPa) corresponding to 25-40 deg C saturation temperature."

**Trap:** Confusing economiser (feedwater heater using flue gas) with feedwater heater (using extraction steam) - both preheat feedwater but use different heat sources.

**What they're really testing:** Whether you understand boiler/steam cycle components and their functions in sequence.

---

# Part 8. Comprehensive Questions - 6 questions

### Q54. Design process: from requirement to finished drawing. [H]

**A:** Design engineer converts a requirement into a drawing that someone can make and that survives its duty. The sequence is: (1) fix the requirements - function, load, environment, life, cost, applicable standards; (2) estimate the loads, static, dynamic, fatigue and the worst credible case; (3) choose the material from strength, corrosion, heat and wear; (4) get a preliminary size from simple stress or stiffness relations; (5) do the detailed analysis, hand calculation with stress concentration and deflection, or FEA; (6) fix the factor of safety and check every likely failure mode; (7) consider manufacture - machining, welding, standard stock; (8) issue the drawing with tolerances, fits and surface finish; (9) prototype; (10) test and prove it, then modify.

**Push:** "Where do standard parts fit into this?" → "At steps 3 to 7 you check whether an off-the-shelf bearing, fastener, coupling or motor already does the job, because using it cuts cost, lead time and risk."

**Trap:** "The last step is submitting the drawing." A design that was never prototyped and tested is not a finished design; proving it is part of the job.

**What they're really testing:** Whether you treat design as a sequence with decisions and trade-offs, not as a formula you apply at the end.

### Q55. Stress-based vs strain-based design. [H]

**A:** In stress-based design the working stress must stay below an allowable stress, which is the material strength divided by a factor of safety, and that is what most codes use. In strain-based design you check the actual stress and strain against the real stress-strain curve with a limit on each, so the material is used far more efficiently and the failure mode can be predicted. ASME Section VIII Division 1 is the allowable-stress route for ordinary pressure vessels, Division 2 is the strain-based route used for higher pressures, complex shapes, fatigue or creep.

**Push:** "When would you use Division 2?" → "For higher allowable stress, complex geometry or where you need fatigue and creep analysis to exploit the material; you pay with much heavier analysis and fabrication control, so Division 1 stays the default."

**Trap:** Calling allowable stress the same as yield strength. It is yield (or ultimate for a brittle material) divided by the code factor of safety - 3.5 on yield in ASME VIII Division 1, which you confirm against the edition you are using.

**What they're really testing:** Whether you know different design philosophies and when each is appropriate.

### Q56. Factor of safety, how choose for a real part. [H]

**A:** No, it's not always 3. The FoS covers uncertainty in the loads, in the material properties and in manufacturing, and it depends on how bad the failure would be. For a ductile steel bracket under static load, 2 to 3 is normal; for a casting, a weldment or anything with a sharp stress raiser, go higher, 3 to 4; for pressure parts the code fixes it, 3.5 on yield in ASME VIII Division 1. Brittle material needs more because it fails without warning. For fatigue you do not use one factor on the strength - you take an allowable amplitude from the S-N curve with roughly 1.5 to 2 on top.

**Push:** "How is the FoS different for a crane hook and for a pressure vessel?" → "A pressure vessel gets the code value because a leak can kill people and the loads are well characterised; a crane hook gets more because the load range and shock are less predictable and the material must be very clean."

**Trap:** Quoting one universal value of 3. The interviewer wants to hear that it is a judgement about consequences, load uncertainty and material uniformity.

**What they're really testing:** Whether you treat FoS as a judgement, not a universal constant.

### Q57. Welding vs casting vs machining - when choose each. [M]

**A:** Casting gives complex shapes in quantity with the least machining, but the grain follows the cooling contours and the shrinkage porosity acts as a crack starter. Forging squeezes the metal and refines and aligns the grain flow with the shape and the load path, which is why forgings are far more fatigue resistant than castings - crankshafts and gear blanks are forged for that reason. Rolling and extrusion are primary routes for long products and give a refined, directional grain. Sheet forming makes thin shells and panels cheaply. Powder metallurgy gives near-net shapes with no machining and controlled porosity for filters and bearings, but the size and shape are limited. Welding is chosen when the item is large, when it is a structure rather than a component - frames, vessels, tanks, stacks, pipe spools - when the shape is not economical to cast, and when field repair matters. A welded fabrication is generally cheaper than a casting of the same size, because a casting needs a pattern, a mould and a melting furnace while welding needs only fit-up and the welding process. But welding is not free: the cost is in consumables, welding man-hours, fit-up and NDT, and it grows with joint thickness and the number of passes. For a small component with tight tolerances, machining from bar is still cheapest.

**Push:** "Where is welding used in heavy structures?" → "In structural steel and heavy plant the joints are usually specified as full penetration butt welds with continuous inspection, because the load path and the fatigue life of the structure depend on the weld quality rather than on the strength of the parent metal."

**Trap:** "Welded construction is always cheaper than a casting" - for a very large casting the opposite can be true, and any fair comparison must include the pattern cost, the reject rate and the machining that follows.

**What they're really testing:** Whether you understand that manufacturing method choice is based on trade-offs, not just cost.

### Q58. GD&T - why it exists beyond +/- tolerancing. [M]

**A:** Traditional plus/minus dimensioning says only what size a feature is and says nothing about its shape, orientation or true position. So two parts can both be Ø20 ± 0.1 and one can be a squashed, tilted 20mm hole while the other is a perfect one - both pass. GD&T adds the missing information: it tells the shop what the function of the feature needs, not just its size. ASME Y14.5 is the US standard; the international equivalent is ISO 1101 and the two are nearly identical in content, with slightly different symbol shapes. GD&T does not replace dimensioning - you still dimension the sizes and the basic (theoretically exact) location values; GD&T adds control of form, orientation, location and runout.

**Push:** "What is the practical benefit in a plant?" → "Inspectors can use functional gauges and the drawing is unambiguous, so disputes between design and shop about 'is this part good' disappear."

**Trap:** Saying GD&T is only for aerospace or only for high-volume automotive. It is used whenever function depends on more than size.

**What they're really testing:** Whether you understand GD&T as the language linking drawing to function and inspection, not just a symbol list.

---

## File Statistics

**Total questions: 58** (across 8 parts)

**By tag:**
- [H] High-yield: ~38 questions (appear in 4+ interview accounts)
- [M] Medium-yield: ~15 questions (2-3 accounts)
- [L] Occasional: ~5 questions (single anecdote)

**By subject distribution:**
- Thermodynamics: 12 questions
- SOM: 10 questions
- Fluid Mechanics: 8 questions
- Theory of Machines: 8 questions
- Machine Design: 8 questions
- Engineering Mechanics: 6 questions
- Thermal/Fluids Systems: 6 questions
- Comprehensive: 6 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, steel density 7850, water 1000, oil 900-950, Re: laminar <2300, turbulent >4000, FoS values per code, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences, key result first), **Push:** (1-2 sentence follow-up), **Trap:** (1 line misconception), **What they're really testing:** (one line intent).

This bank works for automobiles (moving parts, engines, transmissions), petrochem (process systems, heat exchangers, fluid flow), and construction (structural, foundations, equipment).

@28@