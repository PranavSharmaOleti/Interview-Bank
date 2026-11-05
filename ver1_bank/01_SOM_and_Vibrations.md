# Strength of Materials and Vibrations - L&T GET technical interview bank

**Part 1 of 8 | 32 questions | Core SOM fundamentals and vibration basics for mechanical GET panel**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly, [L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing recall, they are testing whether you can reason out loud.*

## 1. Strength of Materials - 22 questions

### Q1. What is the difference between stress and strain? Give their units and the basic formula connecting them. [H]

**A:** Stress (sigma) is internal resistance per unit area, units N/m2 or Pa. Strain (epsilon) is deformation per unit length, dimensionless. Hooke's law: sigma = E * epsilon in the linear elastic region, where E is Young's modulus.

**Push:** If you double the load on a steel rod in the elastic range, what happens to strain?
**Answer:** Strain doubles - linear proportionality holds until the proportional limit.

**Trap:** Stating stress has units of "N" instead of "N/m2" or confusing engineering strain with true strain.

### Q2. Sketch the stress-strain curve for mild steel and label every key point. [H]

**A:** Linear elastic (OA) -> proportional limit (P) -> elastic limit (E) -> upper yield point (Y_u) -> lower yield point (Y_l) -> plastic region with strain hardening -> ultimate tensile strength (U) -> necking -> fracture (F). Ductility = strain at fracture; toughness = area under curve; resilience = area up to elastic limit; stiffness = slope in elastic region (E).

**Push:** Where does the 0.2% proof stress sit on this curve?
**Answer:** It's the stress at 0.2% plastic strain offset from origin - used for materials without a clear yield point like aluminium.

**Trap:** Calling the proportional limit and elastic limit the same point, or saying necking starts at yield.

### Q3. What is Hooke's law and where does it stop being valid? [H]

**A:** Hooke's law states stress is proportional to strain (sigma = E*epsilon). It is valid only up to the proportional limit - the highest stress where the stress-strain curve remains a straight line. Beyond this, the material still behaves elastically (returns to original shape) up to the elastic limit, but not linearly.

**Push:** Can a material be elastic but not follow Hooke's law?
**Answer:** Yes - rubber is elastic (returns to shape) but non-linear. Hooke's law requires linear elasticity.

**Trap:** Saying Hooke's law holds up to the yield point or elastic limit.

### Q4. Name the main types of stress and give a practical example of each. [H]

**A:** Normal stress (tensile/compressive) - rod in tension; Shear stress - rivet in single shear, shaft in torsion; Bearing stress - bolt bearing on plate hole; Punching shear - hole punching operation; Bending stress - beam fibers; Thermal stress - constrained expansion.

**Push:** What is the shear stress distribution in a circular shaft under torsion?
**Answer:** Linear from zero at centre to maximum at surface, tau = T*r/J.

**Trap:** Confusing bearing stress with compressive stress (bearing is localised contact pressure).

### Q5. Define allowable stress and factor of safety. How do you choose a factor of safety in practice? [H]

**A:** Allowable stress = yield stress (or UTS) / factor of safety (FoS). FoS choice depends on: loading type (static vs dynamic/impact), material reliability (homogeneous steel vs casting), consequence of failure (safety critical vs redundant), service temperature (creep), code requirements (IS 800, ASME), manufacturing uncertainty (weld quality, residual stress), inspection access.

**Push:** What typical FoS would you use for a static steel structure per IS 800?
**Answer:** Around 1.5 to 1.67 on yield strength for limit state design; older working stress codes used ~1.5-2.0.

**Trap:** Giving a single number like "FoS = 2" without context, or using UTS instead of yield for ductile materials.

### Q6. Explain von Mises and Tresca failure theories. Which is more conservative and why? [H]

**A:** Von Mises (distortion energy): yielding occurs when distortional strain energy reaches yield value; equivalent stress sigma_vm = sqrt(0.5*[(sigma1-sigma2)^2 + (sigma2-sigma3)^2 + (sigma3-sigma1)^2]). Tresca (max shear): yielding when max shear stress reaches shear yield = 0.5*sigma_y; equivalent stress = sigma1 - sigma3. Tresca is more conservative (predicts yielding earlier) - its yield locus is inscribed inside von Mises ellipse. Von Mises matches ductile metal test data better.

**Push:** For pure shear, what does each theory predict as yield stress in shear?
**Answer:** Tresca: tau_y = 0.5*sigma_y. Von Mises: tau_y = 0.577*sigma_y.

**Trap:** Saying von Mises is always more conservative, or mixing up which is the inner/outer locus.

### Q7. A 20 mm diameter steel rod carries a 50 kN tensile load. Calculate the tensile stress. [H]

**A:** Area = pi/4 * 20^2 = 314.16 mm2. Stress = 50000 N / 314.16 mm2 = 159.2 MPa. This is well below mild steel yield (~250 MPa) so elastic.

**Push:** If the rod is 2 m long and E = 200 GPa, what is the elongation?
**Answer:** Strain = 159.2/200000 = 7.96e-4; delta = strain * L = 1.59 mm.

**Trap:** Forgetting to convert mm2 to m2 or using diameter instead of radius in area formula.

### Q8. Compare solid and hollow shafts of same material and weight for torsional strength. [H]

**A:** For same weight and length, hollow shaft has larger polar moment J (material concentrated at larger radius). Torsional strength proportional to J/r_o. Hollow shaft is stronger and stiffer in torsion. Typical: hollow shaft with d_i/d_o = 0.5 to 0.7 gives 30-50% more torque capacity than solid of same weight.

**Push:** Why not make the wall infinitely thin?
**Answer:** Buckling risk, manufacturing limits, local denting, critical speed concerns.

**Trap:** Saying solid shaft is stronger because "more material" or confusing polar moment J with second moment I.

### Q9. State the bending stress formula and define each term. [H]

**A:** sigma = M*y/I. M = bending moment at section, y = distance from neutral axis to fiber, I = second moment of area about neutral axis. Valid for: pure bending (constant M), plane sections remain plane, material linear elastic, symmetric cross-section or principal axes.

**Push:** Where is the maximum bending stress in a simply supported beam with UDL?
**Answer:** At midspan, top and bottom fibers (M_max = wL^2/8, y = c).

**Trap:** Using I about wrong axis, or forgetting y is measured from neutral axis (not top/bottom arbitrarily).

### Q10. Draw the SFD and BMD for a simply supported beam with uniformly distributed load. Where is maximum BM? [H]

**A:** SFD: linear from +wL/2 at left support to -wL/2 at right support (zero at midspan). BMD: parabolic, maximum at midspan = wL^2/8. Maximum BM occurs where SF = 0 (midspan for symmetric UDL). Slope of BMD = SF at that point.

**Push:** How does the BMD change if the UDL only covers half the span?
**Answer:** Parabolic segment under load, linear segments elsewhere; peak shifts toward loaded region.

**Trap:** Drawing BMD as triangle (that's point load), or putting max BM at supports.

### Q11. Draw the SFD and BMD for a cantilever beam with point load at free end. [H]

**A:** SFD: constant = -P along full length. BMD: linear from 0 at free end to -PL at fixed support (hogging). Max BM = PL at fixed end.

**Push:** Where is the point of contraflexure?
**Answer:** None for this loading - BM doesn't change sign.

**Trap:** Drawing SFD as zero at fixed end, or BMD positive (sagging convention confusion).

### Q12. State the Euler-Bernoulli beam assumptions and the deflection formula for a simply supported beam with UDL. [H]

**A:** Assumptions: plane sections remain plane and normal to neutral axis, small deflections, linear elastic material, beam initially straight, cross-section symmetric about bending plane. Deflection at midspan: delta_max = 5*w*L^4 / (384*E*I).

**Push:** What about a cantilever with point load at tip?
**Answer:** delta_tip = P*L^3 / (3*E*I).

**Trap:** Using 384 instead of 384*E*I in denominator, or confusing 5/384 with 1/384 (point load at centre).

### Q13. List five ways to reduce deflection of a cantilever beam. [H]

**A:** 1) Increase Young's modulus E (change material), 2) Increase second moment I (deeper section, I-beam vs rectangle), 3) Reduce span L (most effective - L^3 or L^4 dependence), 4) Add intermediate support (convert to propped cantilever), 5) Change section profile (tapered, haunched, or pre-camber). Also: reduce load, use composite action.

**Push:** Which is most effective per unit cost?
**Answer:** Reducing span or increasing depth (I ~ depth^3) usually best. Pre-camber only offsets, doesn't change stiffness.

**Trap:** Listing "increase thickness" without specifying where (flange vs web matters), or saying "increase FoS".

### Q14. Derive the torsional shear stress formula tau = T*r/J. [H]

**A:** Key steps: 1) Assume plane sections remain plane and rotate rigidly (no warping for circular section). 2) Shear strain gamma = r*theta/L (theta = angle of twist). 3) Hooke's law in shear: tau = G*gamma. 4) Elemental torque dT = tau * r * dA. 5) Integrate: T = G*theta/L * integral(r^2 dA) = G*theta*J/L. 6) Substitute back: tau = T*r/J.

**Push:** Why doesn't this work for non-circular sections?
**Answer:** Warping occurs - cross-sections don't remain plane. Need St. Venant's torsion theory.

**Trap:** Using J = pi*d^4/32 for hollow shaft (correct is pi*(d_o^4 - d_i^4)/32) or confusing J with I.

### Q15. A solid shaft transmits 50 kW at 1200 rpm. If allowable shear stress is 60 MPa, find the minimum diameter. [H]

**A:** P = 2*pi*N*T/60 -> T = 50000*60/(2*pi*1200) = 397.9 N-m. tau = 16*T/(pi*d^3) for solid shaft. d^3 = 16*397.9/(pi*60e6) = 3.38e-5 -> d = 32.3 mm. Use 35 mm standard.

**Push:** If a hollow shaft with d_i/d_o = 0.5 carries same torque, what is outer diameter?
**Answer:** J = pi/32*(d_o^4 - d_i^4) = pi/32*d_o^4*(1-0.5^4) = 0.9375*J_solid. d_o increases by ~2% only.

**Trap:** Using power in kW without converting to watts, or forgetting the 16 in tau = 16T/(pi*d^3).

### Q16. What is equivalent bending moment and equivalent torque for combined bending and torsion? [H]

**A:** Equivalent bending moment M_e = 0.5*(M + sqrt(M^2 + T^2)) - gives same max normal stress as combined loading. Equivalent torque T_e = sqrt(M^2 + T^2) - gives same max shear stress. Used in shaft design per ASME/IS codes.

**Push:** Which theory (von Mises or Tresca) does the ASME code equivalent moment correspond to?
**Answer:** It's based on maximum shear stress theory (Tresca) with empirical factors.

**Trap:** Using M_e = M + T or T_e = M + T, or confusing which equivalent gives which stress.

### Q17. Derive Euler's critical buckling load for a pinned-pinned column. [H]

**A:** Start with beam equation: EI*d^2y/dx^2 = -M = -P*y. Solution: y = A*sin(kx) + B*cos(kx) where k^2 = P/(EI). Pinned ends: y=0 at x=0 and x=L -> B=0, sin(kL)=0 -> kL = n*pi. Lowest mode (n=1): P_cr = pi^2*EI/L^2. Assumptions: perfectly straight, homogeneous, elastic, axial load, no imperfections.

**Push:** What is the effective length L_eff for fixed-fixed column?
**Answer:** L_eff = 0.5*L (K=0.5). P_cr = 4*pi^2*EI/L^2 (four times pinned-pinned).

**Trap:** Using L instead of L_eff, or forgetting K factors for other end conditions.

### Q18. List the effective length factors K for standard column end conditions. [H]

**A:** Pinned-pinned: K=1.0; Fixed-fixed: K=0.5; Fixed-pinned: K=0.7; Fixed-free: K=2.0. Effective length L_eff = K*L. Buckling load P_cr = pi^2*EI/(K*L)^2.

**Push:** Real fixed supports are never perfectly rigid. What K do codes typically use for "fixed" ends?
**Answer:** IS 800 uses K=0.65 for fixed-fixed, 0.8 for fixed-pinned to account for partial fixity.

**Trap:** Using K=1 for fixed-pinned, or K=0.5 for fixed-free.

### Q19. What is slenderness ratio? When do you use Euler vs Rankine vs Johnson formula? [H]

**A:** Slenderness ratio lambda = L_eff / r (r = radius of gyration = sqrt(I/A)). Euler valid for long columns (lambda > lambda_c, elastic buckling). Rankine: empirical for all lengths, 1/P_R = 1/P_c + 1/P_e. Johnson parabolic: for intermediate columns (inelastic buckling). Euler for lambda > 120 (steel), Rankine for general, Johnson for lambda < ~80.

**Push:** What is the transition slenderness for Euler to be valid for mild steel (E=200 GPa, sigma_y=250 MPa)?
**Answer:** lambda_c = pi*sqrt(E/sigma_y) = pi*sqrt(200000/250) = 88.8. Above this, Euler applies.

**Trap:** Using slenderness ratio based on length L instead of L_eff, or applying Euler to short columns.

### Q20. Give the hoop and longitudinal stress formulas for a thin cylindrical pressure vessel. Why is hoop stress double? [H]

**A:** Hoop stress sigma_h = P*r/t (or P*d/2t). Longitudinal stress sigma_l = P*r/(2t) (or P*d/4t). Hoop is double because: cut longitudinally -> force = P*d*L resisted by 2*t*L; cut transversely -> force = P*pi*d^2/4 resisted by pi*d*t. Ratio = 2:1.

**Push:** What is the thin-wall criterion?
**Answer:** d/t > 10 (or r/t > 10). Some codes use 20 for higher accuracy.

**Trap:** Using d instead of r in formulas inconsistently, or saying hoop stress = P*d/t (missing factor of 2).

### Q21. What is the endurance limit in fatigue? How does stress concentration affect fatigue life? [H]

**A:** Endurance limit (sigma_e) = stress amplitude below which infinite life is expected (for steels ~0.4-0.5*UTS). Stress concentration factor K_t (theoretical) increases local stress. Fatigue stress concentration factor K_f = 1 + q*(K_t - 1) where q = notch sensitivity (0 to 1). Fatigue life drops sharply with K_f. Shot peening introduces compressive surface residual stress to improve fatigue life.

**Push:** Does aluminium have a clear endurance limit?
**Answer:** No - aluminium S-N curve continues sloping down; design uses fatigue strength at 10^7 or 10^8 cycles.

**Trap:** Using K_t directly instead of K_f, or saying shot peening increases material strength (it adds compressive residual stress).

### Q22. State Saint-Venant's principle and give a practical example. [H]

**A:** Saint-Venant's principle: localised stress distribution from statically equivalent load systems becomes uniform at distances approximately equal to the largest dimension of the loaded region. Example: stress concentration at a hole in a plate decays to nominal stress within ~1-2 hole diameters from the edge.

**Push:** How does this apply to a bolted joint?
**Answer:** Stress distribution under bolt head is complex locally, but at a distance (e.g., in the shank) it's uniform axial stress = P/A.

**Trap:** Saying it applies to all loads regardless of distance, or confusing it with superposition.

**What they're really testing:** Whether you can distinguish textbook formulas from practical design judgment - knowing when a formula applies, what assumptions limit it, and how to choose factors based on real-world consequences.

## 2. Vibrations - 10 questions

### Q23. Derive the equation of motion and natural frequency for an undamped SDOF spring-mass system. [H]

**A:** Free body: m*x_ddot + k*x = 0 -> x_ddot + (k/m)*x = 0. Natural frequency omega_n = sqrt(k/m) rad/s. f_n = omega_n/(2*pi) Hz. Period T = 1/f_n = 2*pi*sqrt(m/k).

**Push:** If mass doubles and stiffness halves, what happens to f_n?
**Answer:** f_n new = (1/2*pi)*sqrt((k/2)/(2m)) = (1/2*pi)*sqrt(k/(4m)) = 0.5*f_n original.

**Trap:** Confusing rad/s with Hz, or giving omega_n = k/m (missing square root).

### Q24. Explain viscous damping, damping ratio, and the difference between damped and undamped natural frequency. [H]

**A:** Viscous damping force = c*x_dot (proportional to velocity). Damping ratio zeta = c/c_critical where c_critical = 2*sqrt(k*m) = 2*m*omega_n. Damped natural frequency omega_d = omega_n*sqrt(1-zeta^2). For zeta < 1 (underdamped): decaying oscillation. zeta = 1 (critically damped): fastest return without oscillation. zeta > 1 (overdamped): slow non-oscillatory return.

**Push:** What is omega_d when zeta = 0.1?
**Answer:** omega_d = 0.995*omega_n (less than 1% difference). Damping barely changes frequency for light damping.

**Trap:** Saying omega_d = omega_n*sqrt(1-zeta) (missing square on zeta), or claiming damping increases natural frequency.

### Q25. What is resonance? Why is it dangerous? Define magnification factor. [H]

**A:** Resonance: forcing frequency equals natural frequency (omega = omega_n). Amplitude theoretically infinite for undamped system; limited by damping in real systems. Dangerous because large dynamic stresses cause rapid fatigue failure. Magnification factor MF = 1/sqrt((1-r^2)^2 + (2*zeta*r)^2) where r = omega/omega_n. At resonance (r=1), MF = 1/(2*zeta).

**Push:** If zeta = 0.02, what is MF at resonance?
**Answer:** MF = 1/(2*0.02) = 25. Response 25x static deflection.

**Trap:** Saying resonance only occurs at exact omega_n (it's a peak around omega_d for damped systems), or confusing magnification factor with transmissibility.

### Q26. Define critical speed of a shaft. How does it relate to natural frequency and whirling? [H]

**A:** Critical speed = rotational speed at which shaft rotation frequency coincides with lateral natural frequency of the rotor-bearing system. At critical speed, synchronous whirling occurs - shaft centre rotates in orbit at running speed. Causes large vibration amplitudes. Practical fix: operate well away from critical speeds, improve balancing, increase stiffness, add damping (squeeze film dampers).

**Push:** Can a shaft have multiple critical speeds?
**Answer:** Yes - one for each bending mode (first, second, third...). First critical speed is usually most important.

**Trap:** Confusing critical speed (rotational speed) with natural frequency (Hz), or saying critical speed only occurs in vertical shafts.

### Q27. Differentiate between whirling and vibration. What is static vs dynamic balancing? [H]

**A:** Whirling: synchronous orbital motion of rotor centreline at running speed (or sub/super-synchronous). Vibration: broader term for any oscillatory motion. Static balancing: corrects single-plane unbalance (centrifugal force couple = 0). Dynamic balancing: corrects two-plane unbalance (both force and couple = 0). Static balancing sufficient for thin discs; dynamic needed for long rotors.

**Push:** A rotor is statically balanced but vibrates at running speed. Why?
**Answer:** It has couple unbalance - two equal unbalances 180 deg apart in different planes. Creates moment but no net force. Requires dynamic balancing.

**Trap:** Saying static balancing fixes all unbalance, or that dynamic balancing is "better" rather than "necessary for multi-plane unbalance".

### Q28. Explain transmissibility and vibration isolation. When does damping help vs hurt isolation? [H]

**A:** Transmissibility T = force transmitted to foundation / applied force = sqrt(1 + (2*zeta*r)^2) / sqrt((1-r^2)^2 + (2*zeta*r)^2). For force excitation: isolation (T < 1) requires r > sqrt(2) i.e., omega > 1.414*omega_n. Damping helps at resonance (reduces peak T) but hurts isolation at high r (increases T above the undamped curve). For base excitation, same formula applies to displacement transmissibility.

**Push:** If you want 90% isolation (T=0.1), what frequency ratio r do you need assuming light damping?
**Answer:** For large r, T approx = 1/r^2. So r = sqrt(10) = 3.16. Need omega > 3.16*omega_n.

**Trap:** Saying "more damping always improves isolation" - it reduces peak but worsens high-frequency isolation.

### Q29. What is logarithmic decrement? How do you measure damping from free vibration decay? [H]

**A:** Logarithmic decrement delta = ln(x_n / x_{n+1}) = 2*pi*zeta / sqrt(1-zeta^2) approx = 2*pi*zeta for small zeta. Measure successive peak amplitudes in free decay, compute delta, then zeta = delta / sqrt(4*pi^2 + delta^2). For viscous damping, delta is constant per cycle.

**Push:** If amplitude decays to 50% in 5 cycles, what is zeta?
**Answer:** x_{n+5}/x_n = 0.5. 5*delta = ln(2) = 0.693 -> delta = 0.1386. zeta = delta/(2*pi) = 0.022.

**Trap:** Using delta = ln(x_1/x_n) / n but forgetting it's per cycle, or applying to non-viscous damping.

### Q30. List common machine fault signatures in vibration spectrum (frequency and pattern). [H]

**A:** Unbalance: 1x RPM, radial, single peak. Misalignment: 1x and 2x RPM, axial + radial, phase shift across coupling. Looseness: 0.5x, 1.5x, 2.5x RPM (sub-harmonics), erratic phase. Bearing defect: non-integer multiples (BPFO, BPFI, BSF, FTF) - calculated from geometry. Rub: 1x + 2x + 3x... harmonics, high radial, partial contact. Oil whirl: 0.4-0.48x RPM sub-synchronous. Resonance: high 1x with phase shift, amplification at critical speed.

**Push:** How do you distinguish unbalance from misalignment when both show 1x RPM?
**Answer:** Unbalance: predominantly radial, phase difference ~0 or 180 deg across bearing. Misalignment: high axial at 1x and 2x, phase shift ~180 deg across coupling.

**Trap:** Assigning bearing frequencies to 1x/2x RPM, or saying looseness shows only at 1x.

### Q31. What are the conditions for static, couple, and dynamic balancing of rotating masses? [H]

**A:** Static balance: sum of centrifugal forces = 0 (single plane). Couple balance: sum of centrifugal force couples = 0 (forces balanced but moment exists). Dynamic balance: both force and couple sums = 0 (two planes). Static unbalance corrected in one plane. Couple unbalance needs two equal masses 180 deg apart in two planes. Dynamic unbalance needs correction in two planes.

**Push:** A rotor has two unbalance masses of equal magnitude, 180 deg apart in two different planes. What type of unbalance?
**Answer:** Pure couple unbalance. Statically balanced (no net force) but dynamically unbalanced (couple moment).

**Trap:** Saying couple balance is a subset of static balance, or that dynamic balancing only requires two planes regardless of unbalance distribution.

### Q32. Explain the difference between force excitation and base excitation. How does the transmissibility formula differ? [M]

**A:** Force excitation: external force F(t) applied to mass. Base excitation: foundation moves y(t), mass experiences relative motion z = x - y. Equation: m*z_ddot + c*z_dot + k*z = -m*y_ddot. Displacement transmissibility T_d = X/Y = sqrt(1 + (2*zeta*r)^2) / sqrt((1-r^2)^2 + (2*zeta*r)^2) - same formula as force transmissibility. Force transmissibility T_f = F_T/F_0 uses same expression.

**Push:** For base excitation at very high frequency (r >> 1), what happens to mass displacement relative to base?
**Answer:** Mass stays nearly stationary (X -> 0) while base moves - mass isolates from base motion.

**Trap:** Saying the formulas are completely different, or confusing relative displacement with absolute displacement transmissibility.

**What they're really testing:** Whether you understand vibration as a system response problem - can identify excitation type, compute critical speeds, diagnose faults from spectrum, and design isolation knowing when damping helps or hurts.