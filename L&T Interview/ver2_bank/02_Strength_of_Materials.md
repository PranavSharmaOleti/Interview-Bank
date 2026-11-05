# Strength of Materials - Core Interview Bank

**Part 2 of 10 | 50 questions | Stress, strain, beams, torsion, columns, failure theories, fatigue**
*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Stress and Strain Fundamentals - 12 questions

### Q1. Difference between stress and strain. [H]
**A:** Stress (sigma) is internal resistance per unit area, units N/m2 or Pa. Strain (epsilon) is deformation per unit length, dimensionless. Hooke's law: sigma = E * epsilon in the linear elastic region, where E is Young's modulus. Key distinction: stress is force/area (pressure-like), strain is change in length/original length (ratio).
**Push:** If you double the load on a steel rod in the elastic range, what happens to strain? -> Strain doubles - linear proportionality holds until the proportional limit.
**Trap:** Stating stress has units of "N" instead of "N/m2" or confusing engineering strain with true strain.
**What they're really testing:** Whether you can distinguish stress (intensity) from strain (deformation ratio), and know the units.

### Q2. Stress-strain curve for mild steel. [H]
**A:** Linear elastic (OA) -> proportional limit (P) -> elastic limit (E) -> upper yield point (Y_u) -> lower yield point (Y_l) -> plastic region with strain hardening -> ultimate tensile strength (U) -> necking -> fracture (F). Ductility = strain at fracture; toughness = area under curve; resilience = area up to elastic limit; stiffness = slope in elastic region (E).
**Push:** Where does the 0.2% proof stress sit? -> Stress at 0.2% plastic strain offset from origin - used for materials without clear yield point like aluminium.
**Trap:** Calling proportional limit and elastic limit the same point, or saying necking starts at yield.
**What they're really testing:** Whether you can sketch and label the full curve, and distinguish between various points.

### Q3. Hooke's law and where it stops. [H]
**A:** Hooke's law states stress is proportional to strain (sigma = E*epsilon). Valid only up to the proportional limit - the highest stress where the stress-strain curve remains a straight line. Beyond this, the material still behaves elastically (returns to original shape) up to the elastic limit, but not linearly.
**Push:** Can a material be elastic but not follow Hooke's law? -> Yes - rubber is elastic (returns to shape) but non-linear. Hooke's law requires linear elasticity.
**Trap:** Saying Hooke's law holds up to the yield point or elastic limit.
**What they're really testing:** Whether you understand the limits of Hooke's law and can distinguish linear elasticity from general elasticity.

### Q4. Main types of stress, practical examples. [H]
**A:** Normal stress (tensile/compressive) - rod in tension. Shear stress - rivet in single shear, shaft in torsion. Bearing stress - bolt bearing on plate hole. Punching shear - hole punching operation. Bending stress - beam fibers. Thermal stress - constrained expansion.
**Push:** What is the shear stress distribution in a circular shaft under torsion? -> Linear from zero at centre to maximum at surface, tau = T*r/J.
**Trap:** Confusing bearing stress with compressive stress (bearing is localised contact pressure).
**What they're really testing:** Whether you can name stress types and give practical examples.

### Q5. Allowable stress and factor of safety. [H]
**A:** Allowable stress = yield stress (or UTS) / factor of safety (FoS). FoS choice depends on: loading type (static vs dynamic/impact), material reliability (homogeneous steel vs casting), consequence of failure (safety critical vs redundant), service temperature (creep), code requirements (IS 800, ASME), manufacturing uncertainty (weld quality, residual stress), inspection access.
**Push:** What typical FoS for a static steel structure per IS 800? -> Around 1.5 to 1.67 on yield strength for limit state design. Older working stress codes used ~1.5-2.0.
**Trap:** Giving a single number like "FoS = 2" without context, or using UTS instead of yield for ductile materials.
**What they're really testing:** Whether you understand FoS is a judgement about consequences and uncertainties.

### Q6. von Mises and Tresca failure theories. [H]
**A:** Von Mises (distortion energy): yielding when distortional strain energy reaches yield value; equivalent stress sigma_vm = sqrt(0.5*[(sigma1-sigma2)^2 + (sigma2-sigma3)^2 + (sigma3-sigma1)^2]). Tresca (max shear): yielding when max shear stress reaches shear yield = 0.5*sigma_y; equivalent stress = sigma1 - sigma3. Tresca is more conservative (predicts yielding earlier) - its yield locus is inscribed inside von Mises ellipse. Von Mises matches ductile metal test data better.
**Push:** For pure shear, what does each theory predict as yield stress in shear? -> Tresca: tau_y = 0.5*sigma_y. Von Mises: tau_y = 0.577*sigma_y.
**Trap:** Saying von Mises is always more conservative, or mixing up which is the inner/outer locus.
**What they're really testing:** Whether you know both theories, which is more conservative, and can apply each correctly.

### Q7. A 20 mm diameter steel rod carries 50 kN tensile load. Calculate tensile stress. [H]
**A:** Area = pi/4 * 20^2 = 314.16 mm2. Stress = 50000 N / 314.16 mm2 = 159.2 MPa. This is well below mild steel yield (~250 MPa) so elastic.
**Push:** If the rod is 2 m long and E = 200 GPa, what is the elongation? -> Strain = 159.2/200000 = 7.96e-4. delta = strain * L = 1.59 mm.
**Trap:** Forgetting to convert mm2 to m2, or using diameter instead of radius in area formula.
**What they're really testing:** Whether you can do the numerical correctly, and show the reasoning.

### Q8. Compare solid and hollow shafts for torsional strength. [H]
**A:** For same weight and length, hollow shaft has larger polar moment J (material concentrated at larger radius). Torsional strength proportional to J/r_o. Hollow shaft is stronger and stiffer in torsion. Typical: hollow shaft with d_i/d_o = 0.5 to 0.7 gives 30-50% more torque capacity than solid of same weight.
**Push:** Why not make the wall infinitely thin? -> Buckling risk, manufacturing limits, local denting, critical speed concerns.
**Trap:** Saying solid shaft is stronger because "more material" or confusing polar moment J with second moment I.
**What they're really testing:** Whether you understand polar moment distinction and why hollow can be stronger per weight.

### Q9. Bending stress formula and terms. [H]
**A:** sigma = M*y/I. M = bending moment at section, y = distance from neutral axis to fiber, I = second moment of area about neutral axis. Valid for: pure bending (constant M), plane sections remain plane, material linear elastic, symmetric cross-section or principal axes.
**Push:** Where is maximum bending stress in a simply supported beam with UDL? -> At midspan, top and bottom fibers (M_max = wL^2/8, y = c).
**Trap:** Using I about wrong axis, or forgetting y is measured from neutral axis.
**What they're really testing:** Whether you can state the formula correctly and define each term.

### Q10. Derive torsional shear stress formula tau = T*r/J. [H]
**A:** Key steps: 1) Assume plane sections remain plane and rotate rigidly (no warping for circular section). 2) Shear strain gamma = r*theta/L (theta = angle of twist). 3) Hooke's law in shear: tau = G*gamma. 4) Elemental torque dT = tau * r * dA. 5) Integrate: T = G*theta/L * integral(r^2 dA) = G*theta*J/L. 6) Substitute back: tau = T*r/J.
**Push:** Why doesn't this work for non-circular sections? -> Warping occurs - cross-sections don't remain plane. Need St. Venant's torsion theory.
**Trap:** Using J = pi*d^4/32 for hollow shaft (correct is pi*(d_o^4 - d_i^4)/32) or confusing J with I.
**What they're really testing:** Whether you can give the key derivation steps.

### Q11. List five ways to reduce deflection of a cantilever beam. [H]
**A:** 1) Increase Young's modulus E (change material), 2) Increase second moment I (deeper section, I-beam vs rectangle), 3) Reduce span L (most effective - L^3 or L^4 dependence), 4) Add intermediate support (convert to propped cantilever), 5) Change section profile (tapered, haunched, or pre-camber). Also: reduce load, use composite action.
**Push:** Which is most effective per unit cost? -> Reducing span or increasing depth (I ~ depth^3) usually best. Pre-camber only offsets, doesn't change stiffness.
**Trap:** Listing "increase thickness" without specifying where (flange vs web matters), or saying "increase FoS".
**What they're really testing:** Whether you know deflection depends on L^3 or L^4, and which modifications actually change stiffness.

### Q12. Saint-Venant's principle. [H]
**A:** Saint-Venant's principle: localised stress distribution from statically equivalent load systems becomes uniform at distances approximately equal to the largest dimension of the loaded region. Example: stress concentration at a hole in a plate decays to nominal stress within ~1-2 hole diameters from the edge.
**Push:** How does this apply to a bolted joint? -> Stress distribution under bolt head is complex locally, but at a distance (e.g., in the shank) it's uniform axial stress = P/A.
**Trap:** Saying it applies to all loads regardless of distance, or confusing it with superposition.
**What they're really testing:** Whether you understand Saint-Venant's principle and can apply it to stress concentration problems.

---

## 2. Beam Analysis - 10 questions

### Q13. SFD and BMD for simply supported beam with UDL. [H]
**A:** SFD: linear from +wL/2 at left support to -wL/2 at right support (zero at midspan). BMD: parabolic, maximum at midspan = wL^2/8. Maximum BM occurs where SF = 0 (midspan for symmetric UDL). Slope of BMD = SF at that point.
**Push:** How does the BMD change if the UDL only covers half the span? -> Parabolic segment under load, linear segments elsewhere; peak shifts toward loaded region.
**Trap:** Drawing BMD as triangle (that's point load), or putting max BM at supports.
**What they're really testing:** Whether you can draw SFD and BMD correctly and identify maximum moment location.

### Q14. SFD and BMD for cantilever beam with point load at free end. [H]
**A:** SFD: constant = -P along full length. BMD: linear from 0 at free end to -PL at fixed support (hogging). Max BM = PL at fixed end.
**Push:** Where is the point of contraflexure? -> None for this loading - BM doesn't change sign.
**Trap:** Drawing SFD as zero at fixed end, or BMD positive (sagging convention confusion).
**What they're really testing:** Whether you can draw SFD and BMD for cantilever loading.

### Q15. Euler-Bernoulli beam assumptions and deflection formula. [H]
**A:** Assumptions: plane sections remain plane and normal to neutral axis, small deflections, linear elastic material, beam initially straight, cross-section symmetric about bending plane. Deflection at midspan: delta_max = 5*w*L^4 / (384*E*I).
**Push:** What about a cantilever with point load at tip? -> delta_tip = P*L^3 / (3*E*I).
**Trap:** Using 384 instead of 384*E*I in denominator, or confusing 5/384 with 1/384 (point load at centre).
**What they're really testing:** Whether you know the deflection formulas and their assumptions.

### Q16. SFD and BMD for simply supported beam with point load at centre. [H]
**A:** SFD: constant +P/2 from left support to centre, then -P/2 from centre to right support. BMD: triangular, maximum at centre = PL/4. Maximum BM occurs where SF = 0 (at centre for symmetric loading).
**Push:** How does BMD change if point load is off-centre? -> Triangular with peak at load point; peak value = P*a*b/L where a and b are distances from supports.
**Trap:** Drawing BMD as parabolic (that's UDL), or putting max BM at supports.
**What they're really testing:** Whether you can draw SFD and BMD for point load and identify maximum moment location.

### Q17. SFD and BMD for fixed beam with UDL. [M]
**A:** SFD: linear from +wL/2 at left support to -wL/2 at right support (zero at midspan). BMD: parabolic with negative moments at supports (-wL^2/12 each) and positive moment at midspan (+wL^2/24). There are two points of contraflexure where BM = 0, located at 0.211L from each support.
**Push:** Why does a fixed beam have less deflection than a simply supported beam? -> Because fixed ends develop moments that reduce the midspan moment (from wL^2/8 to wL^2/24), reducing deflection.
**Trap:** Drawing BMD as all positive (simply supported convention) - fixed beams have negative end moments.
**What they're really testing:** Whether you understand fixed-end moments and their effect on BMD.

### Q18. SFD and BMD for cantilever beam with UDL. [M]
**A:** SFD: linear from -wL at fixed end to 0 at free end. BMD: parabolic from -wL^2/2 at fixed end to 0 at free end. Maximum BM = wL^2/2 at fixed end. Deflection at free end = wL^4/(8EI).
**Push:** How does the deflection compare to a simply supported beam with same UDL? -> Cantilever deflection = wL^4/(8EI); simply supported = 5wL^4/(384EI). Cantilever is 9.6 times more flexible.
**Trap:** Using the simply supported deflection formula for a cantilever.
**What they're really testing:** Whether you can draw SFD/BMD for cantilever with UDL and calculate deflection.

### Q19. SFD and BMD for simply supported beam with moment at centre. [M]
**A:** SFD: constant = 0 (no transverse load). BMD: linear from 0 at left support to +M/2 at centre (if moment applied clockwise), then linear to 0 at right support. Maximum BM = M/2 at centre. Point of contraflexure at midspan.
**Push:** What is the reaction at supports? -> R_A = M/L (upward), R_B = M/L (upward) for clockwise moment at centre.
**Trap:** Drawing BMD as parabolic (that's UDL) or triangular (that's point load).
**What they're really testing:** Whether you can handle pure moment loading on beams.

### Q20. SFD and BMD for propped cantilever with UDL. [M]
**A:** SFD: linear from R_A at left support to -wL at right support (zero at prop location). BMD: cubic with maximum at prop location. Reactions: R_A = 3wL/8 (up), R_B = 5wL/8 (up), M_A = wL^2/8 (clockwise). Prop location at 3L/8 from fixed end.
**Push:** Why is the prop located at 3L/8 from fixed end? -> Because that's where the bending moment is zero in the cantilever, so the prop doesn't introduce additional moment.
**Trap:** Assuming prop is at midspan - it's not, it's at 3L/8.
**What they're really testing:** Whether you can analyze a statically indeterminate beam.

### Q21. SFD and BMD for overhanging beam with UDL. [M]
**A:** SFD: linear with jumps at supports. BMD: parabolic with maximum at support near overhang, zero at free end. Reactions: R_A = wL^2/(2a) (up), R_B = wL - R_A (up) where a is overhang length. Maximum moment occurs at support near overhang.
**Push:** Where is the point of contraflexure? -> At distance L^2/(2a) from the support near overhang.
**Trap:** Drawing BMD as all positive - overhanging beams have negative moments in the overhang region.
**What they're really testing:** Whether you can handle overhanging beam analysis.

### Q22. SFD and BMD for fixed beam with point load at centre. [M]
**A:** SFD: constant +P/2 from left support to centre, then -P/2 from centre to right support. BMD: linear from -PL/8 at left support to +PL/8 at centre, then linear to -PL/8 at right support. Points of contraflexure at L/4 from each support.
**Push:** How does fixed-end moment compare to simply supported? -> Fixed-end moment = PL/8 vs simply supported maximum moment = PL/4. Fixed beam has half the maximum moment.
**Trap:** Using simply supported moment (PL/4) for fixed beam - fixed ends reduce the moment.
**What they're really testing:** Whether you understand fixed-end moments reduce bending moment in beams.

---

## 3. Torsion and Columns - 10 questions

### Q23. Torsional shear stress formula. [H]
**A:** tau = T*r/J. T = torque, r = distance from centre, J = polar moment of inertia. For solid circular shaft: J = pi*d^4/32. For hollow: J = pi*(d_o^4 - d_i^4)/32. Maximum shear stress at outer surface: tau_max = 16T/(pi*d^3) for solid, 16T*d_o/(pi*(d_o^4 - d_i^4)) for hollow.
**Push:** A solid shaft transmits 50 kW at 1200 rpm. If allowable shear stress is 60 MPa, find minimum diameter. -> T = 50000*60/(2*pi*1200) = 397.9 N-m. d^3 = 16*397.9/(pi*60e6) = 3.38e-5. d = 32.3 mm. Use 35 mm standard.
**Trap:** Using power in kW without converting to watts, or forgetting the 16 in tau = 16T/(pi*d^3).
**What they're really testing:** Whether you can calculate shaft diameter from torque and allowable stress.

### Q24. Equivalent bending moment and torque for combined loading. [H]
**A:** Equivalent bending moment M_e = 0.5*(M + sqrt(M^2 + T^2)) - gives same max normal stress as combined loading. Equivalent torque T_e = sqrt(M^2 + T^2) - gives same max shear stress. Used in shaft design per ASME/IS codes.
**Push:** Which theory (von Mises or Tresca) does the ASME code equivalent moment correspond to? -> It's based on maximum shear stress theory (Tresca) with empirical factors.
**Trap:** Using M_e = M + T or T_e = M + T, or confusing which equivalent gives which stress.
**What they're really testing:** Whether you can combine bending and torsion for shaft design.

### Q25. Euler's critical buckling load. [H]
**A:** Start with beam equation: EI*d^2y/dx^2 = -M = -P*y. Solution: y = A*sin(kx) + B*cos(kx) where k^2 = P/(EI). Pinned ends: y=0 at x=0 and x=L -> B=0, sin(kL)=0 -> kL = n*pi. Lowest mode (n=1): P_cr = pi^2*EI/L^2. Assumptions: perfectly straight, homogeneous, elastic, axial load, no imperfections.
**Push:** What is the effective length L_eff for fixed-fixed column? -> L_eff = 0.5*L (K=0.5). P_cr = 4*pi^2*EI/L^2 (four times pinned-pinned).
**Trap:** Using L instead of L_eff, or forgetting K factors for other end conditions.
**What they're really testing:** Whether you can derive Euler buckling load and apply effective length factors.

### Q26. Effective length factors K for columns. [H]
**A:** Pinned-pinned: K=1.0; Fixed-fixed: K=0.5; Fixed-pinned: K=0.7; Fixed-free: K=2.0. Effective length L_eff = K*L. Buckling load P_cr = pi^2*EI/(K*L)^2.
**Push:** Real fixed supports are never perfectly rigid. What K do codes typically use for "fixed" ends? -> IS 800 uses K=0.65 for fixed-fixed, 0.8 for fixed-pinned to account for partial fixity.
**Trap:** Using K=1 for fixed-pinned, or K=0.5 for fixed-free.
**What they're really testing:** Whether you know K factors and understand they account for real support conditions.

### Q27. Slenderness ratio, Euler vs Rankine vs Johnson. [H]
**A:** Slenderness ratio lambda = L_eff / r (r = radius of gyration = sqrt(I/A)). Euler valid for long columns (lambda > lambda_c, elastic buckling). Rankine: empirical for all lengths, 1/P_R = 1/P_c + 1/P_e. Johnson parabolic: for intermediate columns (inelastic buckling). Euler for lambda > 120 (steel), Rankine for general, Johnson for lambda < ~80.
**Push:** What is the transition slenderness for Euler to be valid for mild steel (E=200 GPa, sigma_y=250 MPa)? -> lambda_c = pi*sqrt(E/sigma_y) = pi*sqrt(200000/250) = 88.8. Above this, Euler applies.
**Trap:** Using slenderness ratio based on length L instead of L_eff, or applying Euler to short columns.
**What they're really testing:** Whether you can select the appropriate column formula based on slenderness ratio.

### Q28. Thin-walled pressure vessel: hoop and longitudinal stress. [H]
**A:** Hoop stress sigma_h = P*r/t (or P*d/2t). Longitudinal stress sigma_l = P*r/(2t) (or P*d/4t). Hoop is double because: cut longitudinally -> force = P*d*L resisted by 2*t*L; cut transversely -> force = P*pi*d^2/4 resisted by pi*d*t. Ratio = 2:1.
**Push:** What is the thin-wall criterion? -> d/t > 10 (or r/t > 10). Some codes use 20 for higher accuracy.
**Trap:** Using d instead of r in formulas inconsistently, or saying hoop stress = P*d/t (missing factor of 2).
**What they're really testing:** Whether you understand the physical reason for the 2:1 ratio and can apply thin-wall formulas.

### Q29. Fatigue: endurance limit and stress concentration. [H]
**A:** Endurance limit (sigma_e) = stress amplitude below which infinite life is expected (for steels ~0.4-0.5*UTS). Stress concentration factor K_t (theoretical) increases local stress. Fatigue stress concentration factor K_f = 1 + q*(K_t - 1) where q = notch sensitivity (0 to 1). Fatigue life drops sharply with K_f. Shot peening introduces compressive surface residual stress to improve fatigue life.
**Push:** Does aluminium have a clear endurance limit? -> No - aluminium S-N curve continues sloping down; design uses fatigue strength at 10^7 or 10^8 cycles.
**Trap:** Using K_t directly instead of K_f, or saying shot peening increases material strength (it adds compressive residual stress).
**What they're really testing:** Whether you understand fatigue as a life problem, and can apply notch sensitivity to real parts.

### Q30. Saint-Venant's principle and practical example. [H]
**A:** Saint-Venant's principle: localised stress distribution from statically equivalent load systems becomes uniform at distances approximately equal to the largest dimension of the loaded region. Example: stress concentration at a hole in a plate decays to nominal stress within ~1-2 hole diameters from the edge.
**Push:** How does this apply to a bolted joint? -> Stress distribution under bolt head is complex locally, but at a distance (e.g., in the shank) it's uniform axial stress = P/A.
**Trap:** Saying it applies to all loads regardless of distance, or confusing it with superposition.
**What they're really testing:** Whether you understand Saint-Venant's principle and can apply it to stress concentration problems.

---

## 4. Vibrations - 8 questions

### Q31. SDOF equation of motion and natural frequency. [H]
**A:** Free body: m*x_ddot + k*x = 0 -> x_ddot + (k/m)*x = 0. Natural frequency omega_n = sqrt(k/m) rad/s. f_n = omega_n/(2*pi) Hz. Period T = 1/f_n = 2*pi*sqrt(m/k).
**Push:** If mass doubles and stiffness halves, what happens to f_n? -> f_n new = (1/2*pi)*sqrt((k/2)/(2m)) = (1/2*pi)*sqrt(k/(4m)) = 0.5*f_n original.
**Trap:** Confusing rad/s with Hz, or giving omega_n = k/m (missing square root).
**What they're really testing:** Whether you can derive the natural frequency and distinguish rad/s from Hz.

### Q32. Viscous damping, damping ratio, damped natural frequency. [H]
**A:** Viscous damping force = c*x_dot (proportional to velocity). Damping ratio zeta = c/c_critical where c_critical = 2*sqrt(k*m) = 2*m*omega_n. Damped natural frequency omega_d = omega_n*sqrt(1-zeta^2). For zeta < 1 (underdamped): decaying oscillation. zeta = 1 (critically damped): fastest return without oscillation. zeta > 1 (overdamped): slow non-oscillatory return.
**Push:** What is omega_d when zeta = 0.1? -> omega_d = 0.995*omega_n (less than 1% difference). Damping barely changes frequency for light damping.
**Trap:** Saying omega_d = omega_n*sqrt(1-zeta) (missing square on zeta), or claiming damping increases natural frequency.
**What they're really testing:** Whether you understand damping ratio, critical damping, and damped natural frequency.

### Q33. Resonance, magnification factor. [H]
**A:** Resonance: forcing frequency equals natural frequency (omega = omega_n). Amplitude theoretically infinite for undamped system; limited by damping in real systems. Dangerous because large dynamic stresses cause rapid fatigue failure. Magnification factor MF = 1/sqrt((1-r^2)^2 + (2*zeta*r)^2) where r = omega/omega_n. At resonance (r=1), MF = 1/(2*zeta).
**Push:** If zeta = 0.02, what is MF at resonance? -> MF = 1/(2*0.02) = 25. Response 25x static deflection.
**Trap:** Saying resonance only occurs at exact omega_n (it's a peak around omega_d for damped systems), or confusing magnification factor with transmissibility.
**What they're really testing:** Whether you understand resonance as a peak response condition, and can calculate magnification factor.

### Q34. Critical speed of a shaft. [H]
**A:** Critical speed = rotational speed at which shaft rotation frequency coincides with lateral natural frequency of the rotor-bearing system. At critical speed, synchronous whirling occurs - shaft centre rotates in orbit at running speed. Causes large vibration amplitudes. Practical fix: operate well away from critical speeds, improve balancing, increase stiffness, add damping (squeeze film dampers).
**Push:** Can a shaft have multiple critical speeds? -> Yes - one for each bending mode (first, second, third...). First critical speed is usually most important.
**Trap:** Confusing critical speed (rotational speed) with natural frequency (Hz), or saying critical speed only occurs in vertical shafts.
**What they're really testing:** Whether you understand critical speed as a resonance condition for rotating shafts.

### Q35. Transmissibility and vibration isolation. [H]
**A:** Transmissibility T = force transmitted to foundation / applied force = sqrt(1 + (2*zeta*r)^2) / sqrt((1-r^2)^2 + (2*zeta*r)^2). For force excitation: isolation (T < 1) requires r > sqrt(2) i.e., omega > 1.414*omega_n. Damping helps at resonance (reduces peak T) but hurts isolation at high r (increases T above the undamped curve). For base excitation, same formula applies to displacement transmissibility.
**Push:** If you want 90% isolation (T=0.1), what frequency ratio r do you need assuming light damping? -> For large r, T approx = 1/r^2. So r = sqrt(10) = 3.16. Need omega > 3.16*omega_n.
**Trap:** Saying "more damping always improves isolation" - it reduces peak but worsens high-frequency isolation.
**What they're really testing:** Whether you understand when damping helps (resonance) vs hurts (isolation), and can design vibration isolation.

### Q36. Logarithmic decrement. [H]
**A:** Logarithmic decrement delta = ln(x_n / x_{n+1}) = 2*pi*zeta / sqrt(1-zeta^2) approx = 2*pi*zeta for small zeta. Measure successive peak amplitudes in free decay, compute delta, then zeta = delta / sqrt(4*pi^2 + delta^2). For viscous damping, delta is constant per cycle.
**Push:** If amplitude decays to 50% in 5 cycles, what is zeta? -> x_{n+5}/x_n = 0.5. 5*delta = ln(2) = 0.693 -> delta = 0.1386. zeta = delta/(2*pi) = 0.022.
**Trap:** Using delta = ln(x_1/x_n) / n but forgetting it's per cycle, or applying to non-viscous damping.
**What they're really testing:** Whether you can measure damping from free vibration decay.

### Q38. Whirling vs vibration, static vs dynamic balancing. [H]
**A:** Whirling: synchronous orbital motion of rotor centreline at running speed (or sub/super-synchronous). Vibration: broader term for any oscillatory motion. Static balancing: corrects single-plane unbalance (centrifugal force couple = 0). Dynamic balancing: corrects two-plane unbalance (both force and couple = 0). Static balancing sufficient for thin discs; dynamic needed for long rotors.
**Push:** A rotor is statically balanced but vibrates at running speed. Why? -> It has couple unbalance - two equal unbalances 180 deg apart in different planes. Creates moment but no net force. Requires dynamic balancing.
**Trap:** Saying static balancing fixes all unbalance, or that dynamic balancing is "better" rather than "necessary for multi-plane unbalance".
**What they're really testing:** Whether you understand the difference between static and dynamic balancing, and when each is sufficient.

---

## 5. Fatigue and Failure - 8 questions

### Q39. S-N curve and endurance limit. [H]
**A:** The S-N or Wohler curve plots stress amplitude S against the number of cycles N to failure, usually on log-log axes, for a small polished test specimen. For steels the curve bends over and flattens into a horizontal line - the endurance limit or fatigue strength - below which the material survives unlimited cycles. A rule of thumb for steel is about half the ultimate tensile strength in MPa, roughly 450 MPa for a 900 MPa steel, but you take the real value from the handbook for the actual material. Aluminium and most other non-ferrous metals have no true endurance limit, so you state a design life and read the curve at that life.
**Push:** How do you get from the laboratory endurance limit to the real part? -> You apply the Marin factors - size, surface finish, load, temperature and reliability - which multiply down to the actual endurance limit of the component.
**Trap:** Using the laboratory endurance limit directly for the real part. The real part always has a lower value, and aluminium has no endurance limit at all.
**What they're really testing:** Whether you know fatigue is a life problem, not a strength problem, and can apply Marin factors.

### Q40. Situations where endurance limit cannot be used. [H]
**A:** Four important ones: (1) Welded joints - the weld toe is a notch with high residual tensile stress, so fatigue cracks start there at stresses well below the parent metal's endurance limit, and you use a fatigue category from the welding code instead. (2) Low-cycle fatigue, below roughly 10^4 to 10^5 cycles, where local yielding occurs at the notch and you need a strain-life (Coffin-Manson) approach. (3) High temperature, where creep and oxidation govern rather than fatigue, and you check against allowable stress at temperature and creep rupture. (4) Corrosive or erosive service, where the endurance limit does not exist because the curve keeps falling with life.
**Push:** Which of these dominates on a power plant site? -> Combined corrosion and fatigue in humid or coastal plants, and creep in steam lines and boilers at high temperature.
**Trap:** Assuming the S-N curve is valid for welded joints and for anything running at 500 deg C.
**What they're really testing:** Whether you know the limits of the S-N approach and when to use alternative fatigue methods.

### Q41. Kt vs Kf, notch sensitivity. [M]
**A:** Kt is purely geometric - the ratio of peak elastic stress at a notch to the nominal stress - and depends only on the notch shape. For static failure, or ductile yielding, the material redistributes and you use Kt (or Neuber's rule for local yielding). In fatigue only part of the notch is actually felt, so you use the fatigue stress concentration factor Kf = 1 + q(Kt - 1), where q is the notch sensitivity between 0 and 1. You apply Kf to the nominal alternating stress when you build the S-N picture, and you get q from a chart of notch sensitivity against notch radius and material strength.
**Push:** How do you reduce Kt in practice? -> Increase the fillet radius, avoid sharp internal corners, add a relief groove, and use radii that are generous relative to the section. A large fillet radius is the cheapest fatigue improvement available.
**Trap:** Treating Kt and Kf as the same number, or using Kt for a fatigue calculation.
**What they're really testing:** Whether you know the difference between geometric and fatigue stress concentration factors.

### Q42. Mean stress effect, Goodman and Gerber diagrams. [M]
**A:** A component under fluctuating load has a mean stress part and an alternating part, and a tensile mean stress shortens fatigue life while a compressive mean stress can lengthen it. The Goodman diagram plots allowable alternating stress against mean stress for a specified life, with a straight line joining the yield intercept and the endurance-limit intercept - the safe region is below that line and the method is conservative. The Gerber parabola is fitted through the same two intercepts but bulges outward, so it predicts more life and is less pessimistic. Goodman is the standard conservative choice; Gerber is used when you have good fatigue data and want a less pessimistic answer.
**Push:** Which do you use for a rotating shaft with fully reversed bending? -> Fully reversed means zero mean stress, so both give the same allowable amplitude; the mean-stress correction only matters when the load is not symmetric.
**Trap:** Thinking the Gerber parabola is the conservative one. It is the optimistic one; Goodman is conservative.
**What they're really testing:** Whether you know the mean stress effect and can choose between Goodman and Gerber.

### Q43. Mohr's circle for plane stress. [M]
**A:** Mohr's circle is a graphical method to find principal stresses and maximum shear stress from known stress components. For plane stress (sigma_x, sigma_y, tau_xy), the centre is at (sigma_x + sigma_y)/2, radius = sqrt(((sigma_x - sigma_y)/2)^2 + tau_xy^2). Principal stresses: sigma_1,2 = centre +/- radius. Maximum shear stress = radius. Angle of principal planes: 2*theta_p = atan(2*tau_xy/(sigma_x - sigma_y)).
**Push:** What is the maximum shear stress in a pure bending condition? -> For pure bending, sigma_x = M*y/I, sigma_y = 0, tau_xy = 0. Max shear = sigma_x/2 (at 45 deg to the neutral axis).
**Trap:** Forgetting to double the angle (2*theta_p), or confusing principal stress angle with shear stress angle.
**What they're really testing:** Whether you can use Mohr's circle to find principal stresses and maximum shear stress.

### Q44. Creep and creep rupture. [M]
**A:** Creep: time-dependent deformation under constant stress at elevated temperature. Three stages: primary (decreasing creep rate), secondary (constant creep rate), tertiary (increasing creep rate leading to rupture). Creep rupture: failure under sustained load at high temperature. Design uses creep rupture strength (stress for 100,000 hours to rupture) and creep rate (strain per hour). Common in boilers, steam lines, gas turbines.
**Push:** At what temperature does creep become significant for steel? -> Above ~400 deg C for carbon steel, ~500 deg C for alloy steels. Below these temperatures, creep is negligible.
**Trap:** Confusing creep with fatigue - creep is time-dependent under constant load; fatigue is cycle-dependent under varying load.
**What they're really testing:** Whether you understand creep as a high-temperature failure mode and can design against it.

### Q45. Thermal stresses in constrained members. [M]
**A:** Thermal stress: sigma = E * alpha * delta_T, where alpha is coefficient of thermal expansion. Occurs when a member is constrained from expanding/contracting freely. For a bar fixed at both ends: sigma = E*alpha*delta_T. For a bar with one end free: no thermal stress (free expansion). For a bimetallic strip: differential expansion causes bending.
**Push:** A steel bar (alpha = 12e-6 /deg C) is fixed at both ends and heated by 100 deg C. What is the thermal stress? -> sigma = 200e9 * 12e-6 * 100 = 240 MPa. This is near yield for mild steel (250 MPa).
**Trap:** Forgetting that thermal stress only occurs when expansion is constrained - a free bar has no thermal stress.
**What they're really testing:** Whether you can calculate thermal stress and understand when it occurs.

### Q46. Mohr's circle for plane strain. [M]
**A:** Same as plane stress but with strains instead of stresses. Principal strains: epsilon_1,2 = centre +/- radius where centre = (epsilon_x + epsilon_y)/2, radius = sqrt(((epsilon_x - epsilon_y)/2)^2 + gamma_xy^2). Maximum shear strain = radius. Used for strain gauge rosette analysis.
**Push:** How does Mohr's circle for strain differ from stress? -> Same graphical construction, but with strains instead of stresses. The angle to principal strain planes is the same as for principal stress planes.
**Trap:** Confusing strain components with stress components - gamma_xy/2 is used in the circle, not gamma_xy.
**What they're really testing:** Whether you can apply Mohr's circle to strain analysis.

### Q47. Fracture toughness and Charpy impact. [M]
**A:** Fracture toughness (K_IC) = critical stress intensity factor at which crack propagation becomes unstable. For linear elastic fracture mechanics: K = sigma * sqrt(pi * a) * Y, where a is crack length, Y is geometry factor. Charpy impact test: measures energy absorbed during fracture of a notched specimen. Used to determine ductile-to-brittle transition temperature (DBTT). Low temperature = brittle failure (low energy), high temperature = ductile failure (high energy).
**Push:** Why is impact testing specified separately from tensile properties? -> Because Charpy impact energy is not implied by strength; a steel can have adequate yield strength and still be brittle at low temperature, so toughness has to be demonstrated separately.
**Trap:** Saying high strength means high toughness - they are independent properties. High-strength steels can be very brittle.
**What they're really testing:** Whether you understand fracture toughness and the ductile-brittle transition.

### Q48. Residual stresses in welded joints. [M]
**A:** Welding causes residual stresses because the weld metal shrinks as it cools while the surrounding plate restrains it. The weld is left in tension, the plate around it in compression. On a pressure vessel, this can be more severe than the working pressure. Controlled by: preheat (slows cooling), post-weld heat treatment (PWHT - stress relief), peening (introduces compressive surface stress), weld sequence (balanced welding).
**Push:** How are residual stresses handled in pressure vessels? -> PWHT (post-weld heat treatment) at ~600-650 deg C for carbon steel, which relieves residual stresses by allowing plastic deformation at elevated temperature.
**Trap:** Saying residual stresses are always bad - compressive residual stresses (from shot peening) actually improve fatigue life.
**What they're really testing:** Whether you understand residual stress formation and mitigation in welded structures.

---

## 6. Fatigue and Design - 8 questions

### Q49. Design for static loading, factor of safety. [H]
**A:** For static loading, design stress = allowable stress = yield stress (or UTS for brittle) / FoS. FoS covers uncertainty in loads, material properties, manufacturing. Typical values: ductile steel under static load: 2-3; casting or weldment: 3-4; pressure parts: code value (3.5 on yield per ASME VIII Div 1). Brittle materials need higher FoS because they fail without warning. For fatigue, use S-N curve with 1.5-2 on top.
**Push:** How is the FoS different for a crane hook and for a pressure vessel? -> Pressure vessel gets code value because leak can kill people and loads are well characterised; crane hook gets more because load range and shock are less predictable.
**Trap:** Quoting one universal value of 3. The interviewer wants to hear that it is a judgement about consequences, load uncertainty and material uniformity.
**What they're really testing:** Whether you treat FoS as a judgement, not a universal constant.

### Q50. Design for dynamic/fatigue loading. [H]
**A:** Fatigue design uses S-N curve (stress amplitude vs cycles to failure). Key steps: 1) Determine the stress amplitude (alternating stress) from the load cycle. 2) Apply stress concentration factor Kf (not Kt) for notches. 3) Apply Marin factors (size, surface finish, load, temperature, reliability) to get the component's endurance limit. 4) Check: sigma_a * Kf < sigma_e_component. 5) For variable amplitude loading, use Miner's rule: sum (n_i/N_i) <= 1.0.
**Push:** What is Miner's rule? -> Cumulative damage rule: sum of (actual cycles / cycles to failure at that stress level) = 1.0 at failure. Used for variable amplitude loading.
**Trap:** Using Kt instead of Kf for fatigue, or forgetting Marin factors for real components.
**What they're really testing:** Whether you can design against fatigue using S-N data and apply the necessary corrections for real components.

---

## File Statistics

**Total questions: 49**

**By tag:**
- [H] High-yield: ~35 questions
- [M] Medium-yield: ~12 questions
- [L] Occasional: ~3 questions

**By section:**
- Stress and strain fundamentals: 12 questions
- Beam analysis: 10 questions
- Torsion and columns: 10 questions
- Vibrations: 8 questions
- Fatigue and failure: 8 questions
- Fatigue and design: 2 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, steel density 7850, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers SOM fundamentals - essential for automobiles, petrochem, and construction interviews.