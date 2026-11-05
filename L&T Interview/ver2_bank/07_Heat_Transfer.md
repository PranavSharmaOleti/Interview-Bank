# Heat Transfer - Core Interview Bank

**Part 7 of 10 | 50 questions | Conduction, convection, radiation, fins, heat exchangers, critical insulation radius, Nusselt/Reynolds analogy, effectiveness-NTU, fouling, Stefan-Boltzmann, view factors, LMTD**

*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Conduction Fundamentals - 10 questions

### Q1. Fourier's law of heat conduction. [H]
**A:** Fourier's law: Q = -k*A*(dT/dx), where k is thermal conductivity, A is area, dT/dx is temperature gradient. The negative sign indicates heat flows from high to low temperature. For a plane wall: Q = k*A*(T1-T2)/L. Units: W for Q, W/m-K for k, m2 for A, K/m for gradient.
**Push:** What is the thermal conductivity of steel vs copper? -> Steel ~40-50 W/m-K, copper ~400 W/m-K. Copper is ~10x more conductive, which is why copper heat exchangers are common.
**Trap:** Forgetting the negative sign in Fourier's law - it's essential for direction. Also confusing thermal conductivity k with thermal diffusivity alpha.
**What they're really testing:** Whether you know Fourier's law and can apply it to simple conduction problems.

### Q2. Thermal resistance concept and network. [H]
**A:** Thermal resistance R_th = L/(k*A) for conduction, 1/(h*A) for convection. Total resistance for series: R_total = R1 + R2 + ... For parallel: 1/R_total = 1/R1 + 1/R2 + ... Heat transfer Q = (T1-T2)/R_total. This is analogous to electrical resistance, making complex multi-layer problems tractable.
**Push:** How do you handle a wall with convection on both sides? -> Three resistances in series: R_conv1 + R_cond + R_conv2. Q = (T_inf1 - T_inf2)/(1/(h1*A) + L/(k*A) + 1/(h2*A)).
**Trap:** Using thermal conductivity instead of thermal resistance in series/parallel calculations, or confusing series and parallel arrangements.
**What they're really testing:** Whether you can build thermal resistance networks and solve multi-layer conduction problems.

### Q3. Composite wall heat transfer. [H]
**A:** For a composite wall with multiple layers, heat transfer Q = (T1-Tn)/R_total where R_total = sum of all resistances in series. For layers in parallel (like a wall with different materials side by side), use parallel resistance formula. Overall heat transfer coefficient U = 1/R_total (based on area). Q = U*A*delta_T.
**Push:** What is the overall heat transfer coefficient U? -> It's the reciprocal of total thermal resistance per unit area: U = 1/(1/h1 + L1/k1 + L2/k2 + ... + 1/h2). Units: W/m2-K.
**Trap:** Using the wrong area for different layers in series - in series, area is the same; in parallel, areas are different.
**What they're really testing:** Whether you can calculate heat transfer through composite walls using thermal resistance.

### Q4. Critical radius of insulation. [H]
**A:** Critical radius r_cr = k/h for cylindrical or spherical insulation. Adding insulation increases heat transfer if outer radius < r_cr (because convection area increase dominates), decreases heat transfer if outer radius > r_cr. For a wire with small radius, insulation can actually increase heat loss. Practical: for pipes below critical radius, don't insulate; for pipes above, insulate.
**Push:** A 10 mm diameter pipe (k_insulation = 0.05 W/m-K, h = 10 W/m2-K). Is r_cr larger or smaller than pipe radius? -> r_cr = 0.05/10 = 0.005 m = 5 mm. Pipe radius = 5 mm. r_cr = pipe radius, so insulation has no effect initially.
**Trap:** Saying insulation always reduces heat loss - below critical radius, insulation increases heat loss.
**What they're really testing:** Whether you understand the counter-intuitive critical radius concept.

### Q5. Transient heat conduction, lumped capacitance. [H]
**A:** Lumped capacitance: when Biot number Bi = h*L_c/k < 0.1, temperature is uniform throughout the body. Then T(t) = T_inf + (T_i - T_inf)*exp(-t/tau), where tau = rho*c*V/(h*A) = thermal capacitance/thermal conductance. Biot number compares conduction resistance to convection resistance: Bi = h*L_c/k.
**Push:** What is the Biot number for a 50 mm steel sphere cooling in air (h=25, k=50, L_c=V/A=0.00833 m)? -> Bi = 25*0.00833/50 = 0.00417 << 0.1. Lumped capacitance is valid.
**Trap:** Using lumped capacitance when Bi > 0.1 - temperature gradients exist inside the body, need Heisler charts or numerical methods.
**What they're really testing:** Whether you can check Biot number and apply lumped capacitance method.

### Q6. Heisler charts for transient conduction. [M]
**A:** Heisler charts provide temperature distributions for transient conduction in plane walls, cylinders, and spheres when Bi > 0.1. Three charts: (1) centre temperature vs Fourier number, (2) temperature distribution vs position, (3) heat transfer vs Fourier number. Fourier number Fo = alpha*t/L_c^2 where alpha = k/(rho*c) is thermal diffusivity.
**Push:** What is the Fourier number and what does it represent? -> Fo = alpha*t/L_c^2 = (k/(rho*c))*t/L_c^2. It represents the ratio of heat conducted to heat stored - dimensionless time.
**Trap:** Confusing Fourier number with Biot number - Fo is dimensionless time, Bi is dimensionless resistance ratio.
**What they're really testing:** Whether you can use Heisler charts and understand the dimensionless numbers.

### Q7. Fin efficiency and effectiveness. [H]
**A:** Fin efficiency eta_f = actual heat transfer / heat transfer if entire fin at base temperature. eta_f = tanh(mL)/(mL) for a straight rectangular fin, where m = sqrt(h*P/(k*A_c)). Fin effectiveness epsilon_f = heat transfer with fin / heat transfer without fin = (Q_with_fin)/(Q_without_fin). Effectiveness > 1 means fin is useful; typical value 2-10 for good fin design.
**Push:** What is the maximum possible fin effectiveness? -> Theoretically infinite if fin has zero thermal resistance, but practically 5-10 for good designs. Effectiveness < 1 means the fin is worse than no fin (wastes material).
**Trap:** Confusing efficiency with effectiveness - efficiency is about the fin itself, effectiveness compares fin vs no fin.
**What they're really testing:** Whether you can calculate fin efficiency and effectiveness, and understand their physical meaning.

### Q8. Fin design considerations. [M]
**A:** Fin design: (1) Material with high k (aluminium, copper) for better conduction along fin. (2) Thin, closely spaced fins for high surface area. (3) Fin length limited by efficiency (long fins have low efficiency). (4) Fin thickness vs spacing trade-off (thicker fins = better conduction but less surface area per volume). (5) Fin orientation for natural convection (vertical fins better for buoyancy-driven flow).
**Push:** Why are aluminium fins used on air-cooled engines? -> Aluminium has high thermal conductivity (k ~200 W/m-K), low density, and is easy to cast into complex fin shapes.
**Trap:** Making fins too long - efficiency drops exponentially with length, so very long fins add little heat transfer.
**What they're really testing:** Whether you understand fin design trade-offs and can select fin parameters.

### Q9. Conduction shape factor. [M]
**A:** Shape factor S is used for 2D/3D conduction where simple 1D formulas don't apply. Q = k*S*(T1-T2). Shape factor depends on geometry: for a cylinder in a medium, S = 2*pi*L/ln(r2/r1); for two parallel cylinders, S = 2*pi*L/ln((D^2/(4*r1*r2)) + ...). Shape factor is dimensionless times length.
**Push:** What is the shape factor for a sphere in an infinite medium? -> S = 4*pi*r (for a sphere of radius r in an infinite medium).
**Trap:** Confusing shape factor with area - shape factor is a dimensionless number that replaces A/L in the conduction equation.
**What they're really testing:** Whether you can use shape factor for complex conduction geometries.

### Q10. Thermal contact resistance. [M]
**A:** Thermal contact resistance occurs at the interface between two solid surfaces. R_contact = 1/(h_c*A) where h_c is contact conductance. Depends on: surface roughness (smoother = lower resistance), contact pressure (higher = lower resistance), interstitial fluid (air = high resistance, thermal paste = low resistance). Important in electronics cooling, engine blocks, and heat exchangers.
**Push:** How do you reduce thermal contact resistance? -> Apply thermal paste (replaces air gaps with conductive material), increase contact pressure, machine surfaces smoother, or use compliant interface (graphite pads, thermal pads).
**Trap:** Ignoring contact resistance in calculations - it can be significant, especially with rough surfaces and low pressure.
**What they're really testing:** Whether you understand thermal contact resistance and can mitigate it.

## 2. Convection - 10 questions

### Q11. Newton's law of cooling. [H]
**A:** Newton's law of cooling: Q = h*A*(T_s - T_inf), where h is convection coefficient, A is surface area, T_s is surface temperature, T_inf is fluid temperature. h depends on fluid properties, flow conditions, and geometry. For forced convection, h ~ 10-1000 W/m2-K; for natural convection, h ~ 5-25 W/m2-K.
**Push:** What is the difference between forced and natural convection? -> Forced: fluid motion driven by external means (fan, pump). Natural: fluid motion driven by buoyancy (density differences due to temperature).
**Trap:** Using Newton's law for radiation - radiation follows Stefan-Boltzmann law, not Newton's law.
**What they're really testing:** Whether you know Newton's law of cooling and can distinguish convection types.

### Q12. Dimensionless numbers in convection. [H]
**A:** Key dimensionless numbers: Re = rho*v*L/mu (inertia/viscous), Nu = h*L/k (convection/conduction), Pr = nu/alpha = mu*c_p/k (momentum diffusivity/thermal diffusivity), Gr = g*beta*delta_T*L^3/nu^2 (buoyancy/viscous), Ra = Gr*Pr (buoyancy*thermal diffusivity). Nu is the target (gives h). Re determines flow regime. Pr is fluid property. Gr/Ra determine natural convection regime.
**Push:** What is the physical meaning of Nusselt number? -> Nu = h*L/k = (convection heat transfer coefficient)/(conduction heat transfer coefficient). Nu = 1 means pure conduction; Nu > 1 means convection enhances heat transfer.
**Trap:** Confusing Prandtl number with other dimensionless groups - Pr is a fluid property (ratio of momentum to thermal diffusivity), not a flow condition.
**What they're really testing:** Whether you understand dimensionless numbers and their physical meanings.

### Q13. Forced convection correlations. [H]
**A:** Forced convection: Nu = f(Re, Pr, geometry). For laminar flow in a pipe: Nu = 3.66 for constant wall temperature, 4.36 for constant heat flux. For turbulent flow: Dittus-Boelter: Nu = 0.023*Re^0.8*Pr^n (n=0.4 for heating, 0.3 for cooling). For flow over flat plate: Nu = 0.664*Re^0.5*Pr^(1/3) for laminar, 0.037*Re^0.8*Pr^(1/3) for turbulent.
**Push:** What is the Dittus-Boelter equation and when is it valid? -> Nu = 0.023*Re^0.8*Pr^n. Valid for: turbulent flow (Re > 10000), 0.7 < Pr < 160, fully developed flow, small temperature differences.
**Trap:** Using Dittus-Boelter for laminar flow or outside its validity range - gives wrong h values.
**What they're really testing:** Whether you know forced convection correlations and their validity ranges.

### Q14. Natural convection correlations. [M]
**A:** Natural convection: Nu = f(Ra, Pr, geometry). For vertical plate: Nu = 0.59*Ra^0.25 for 10^4 < Ra < 10^9 (laminar), 0.10*Ra^(1/3) for 10^9 < Ra < 10^13 (turbulent). For horizontal plate: different coefficients for top/bottom surfaces. For enclosed spaces: Nu depends on Ra and aspect ratio.
**Push:** Why is natural convection heat transfer lower than forced convection? -> Because buoyancy-driven flow is weaker than externally driven flow, resulting in lower velocities and thinner boundary layers.
**Trap:** Using forced convection correlations for natural convection - natural convection has different physics (buoyancy, not external flow).
**What they're really testing:** Whether you can calculate natural convection heat transfer and know the correlations.

### Q15. Boundary layer theory in convection. [M]
**A:** Boundary layer: thin region near surface where velocity and temperature change from wall values to free stream values. Velocity boundary layer: delta (thickness). Thermal boundary layer: delta_t. If delta = delta_t, Pr = 1. If delta > delta_t, Pr > 1 (water, oils). If delta < delta_t, Pr < 1 (air, gases). Convection coefficient h is inversely proportional to thermal boundary layer thickness: h ~ k/delta_t.
**Push:** What does Prandtl number tell you about boundary layers? -> Pr = delta/delta_t. For air (Pr=0.7), thermal BL is thicker than velocity BL. For water (Pr=7), velocity BL is thicker than thermal BL.
**Trap:** Saying Prandtl number is a flow property - it's a fluid property, independent of flow conditions.
**What they're really testing:** Whether you understand boundary layer theory and the role of Prandtl number.

### Q16. Reynolds analogy. [M]
**A:** Reynolds analogy relates friction and heat transfer: St = Cf/2, where St = Nu/(Re*Pr) is Stanton number, Cf is friction coefficient. This means for fluids with Pr ~ 1 (gases), heat transfer and friction are directly related - you can predict heat transfer from pressure drop measurements. For Pr != 1, modified analogies (Prandtl-Taylor, Colburn) are used: St*Pr^(2/3) = Cf/2.
**Push:** Why is Reynolds analogy useful? -> It allows prediction of heat transfer coefficients from friction measurements (or vice versa) for gases, without needing separate heat transfer experiments.
**Trap:** Applying Reynolds analogy to liquids (Pr >> 1) - it's only valid for Pr ~ 1. Use modified analogies for other fluids.
**What they're really testing:** Whether you understand the relationship between friction and heat transfer.

### Q17. Boiling heat transfer. [M]
**A:** Boiling has four regimes on the boiling curve: (1) Natural convection (low delta_T), (2) Nucleate boiling (bubbles form at surface, high h, most efficient), (3) Transition boiling (unstable, film begins to form), (4) Film boiling (stable vapour film, low h, Leidenfrost point). Critical heat flux (CHF) is the maximum heat flux before transition to film boiling. Pool boiling: quiescent fluid. Flow boiling: fluid in motion.
**Push:** What is critical heat flux and why is it important? -> CHF is the maximum heat flux before transition to film boiling. Exceeding CHF causes a sudden temperature rise (burnout) in nuclear reactors and boilers.
**Trap:** Thinking boiling always increases with temperature - beyond CHF, heat transfer drops as film boiling begins.
**What they're really testing:** Whether you understand boiling regimes and the importance of critical heat flux.

### Q18. Condensation heat transfer. [M]
**A:** Film condensation: vapour condenses as a liquid film on the surface. Heat transfer through the film (conduction) dominates. Nusselt's theory: h = 0.943*(rho_l*(rho_l-rho_v)*g*k_l^3*h_fg/(mu_l*(T_sat-T_s)*L))^(1/4) for vertical plate. Dropwise condensation: droplets form and fall, much higher h (5-10x film condensation) but difficult to sustain.
**Push:** Why is film condensation heat transfer lower than dropwise? -> Film condensation has a liquid film that acts as a thermal resistance. Dropwise has minimal liquid on surface, so heat transfer is much higher.
**Trap:** Assuming dropwise condensation is common - it requires special surface treatment and is difficult to maintain in practice.
**What they're really testing:** Whether you understand condensation types and can calculate film condensation h.

### Q19. Internal flow heat transfer. [M]
**A:** Internal flow (pipe/duct): laminar or turbulent. Laminar: fully developed, Nu = 3.66 (constant T_s) or 4.36 (constant q). Thermal entry length: L_t/D = 0.05*Re*Pr. Turbulent: Dittus-Boelter or Gnielinski. For constant wall temperature, use LMTD method. For constant heat flux, use simple energy balance: Q = m_dot*c_p*(T_out-T_in).
**Push:** What is the thermal entry length for laminar flow? -> L_t/D = 0.05*Re*Pr. For water (Pr=7) at Re=1000: L_t/D = 0.05*1000*7 = 350. Very long!
**Trap:** Assuming fully developed flow in short pipes - if L < L_t, use entry region correlations.
**What they're really testing:** Whether you can analyze internal flow heat transfer and account for entry effects.

### Q20. External flow heat transfer. [M]
**A:** External flow over bodies: boundary layer develops from leading edge. For flat plate: laminar for Re < 5e5, turbulent for Re > 5e5. Average Nu for laminar: Nu_avg = 0.664*Re^0.5*Pr^(1/3). For turbulent: Nu_avg = 0.037*Re^0.8*Pr^(1/3). For cylinders: Churchill-Bernstein correlation. For spheres: Whitaker correlation.
**Push:** Why does heat transfer increase at the transition from laminar to turbulent flow? -> Turbulent flow has mixing that brings hot fluid from the wall to the free stream and cold fluid from the free stream to the wall, reducing thermal boundary layer thickness.
**Trap:** Using laminar correlations for turbulent flow or vice versa - they give very different h values.
**What they're really testing:** Whether you can calculate heat transfer for external flow and account for flow regime.

## 3. Radiation - 8 questions

### Q21. Stefan-Boltzmann law. [H]
**A:** Stefan-Boltzmann law: Q = epsilon*sigma*A*T^4, where sigma = 5.67e-8 W/m2-K4 (Stefan-Boltzmann constant), epsilon is emissivity (0 to 1), T is absolute temperature (K). For a blackbody (epsilon=1): Q = sigma*A*T^4. Net radiation between two surfaces: Q = epsilon*sigma*A*(T1^4 - T2^4) for small object in large enclosure.
**Push:** Why must temperature be in Kelvin? -> Because T^4 relationship requires absolute temperature. Using Celsius would give wrong (and possibly negative) results.
**Trap:** Using Celsius or Fahrenheit in Stefan-Boltzmann law - must use absolute temperature (Kelvin).
**What they're really testing:** Whether you know Stefan-Boltzmann law and can apply it correctly.

### Q22. Blackbody, grey body, emissivity. [H]
**A:** Blackbody: ideal emitter/absorber (epsilon = alpha = 1). Grey body: epsilon = alpha (constant, independent of wavelength) but < 1. Real surfaces: epsilon < 1, varies with wavelength and temperature. Emissivity: ratio of actual emission to blackbody emission at same temperature. Absorptivity alpha = 1 - reflectivity - transmissivity. For opaque bodies: alpha + rho = 1.
**Push:** What is the relationship between emissivity and absorptivity? -> For a grey body in thermal equilibrium, epsilon = alpha (Kirchhoff's law). For non-grey bodies, epsilon and alpha depend on wavelength and temperature.
**Trap:** Saying emissivity = 1 for all surfaces - only blackbody has epsilon = 1. Real surfaces have epsilon < 1.
**What they're really testing:** Whether you understand blackbody, grey body, and emissivity concepts.

### Q23. View factors. [H]
**A:** View factor F_ij = fraction of radiation leaving surface i that is intercepted by surface j. Rules: (1) Summation: sum(F_ij) = 1 for all j. (2) Reciprocity: A_i*F_ij = A_j*F_ji. (3) For two surfaces: F_12 = 1 (if surface 1 sees only surface 2). For concentric cylinders/spheres: F_inner-outer = 1. View factors depend only on geometry, not temperature or material.
**Push:** What is the view factor between two parallel plates of equal size? -> F_12 = 1 (each plate sees only the other plate). By reciprocity, F_21 = 1 (equal areas).
**Trap:** Thinking view factors depend on temperature or material - they are purely geometric.
**What they're really testing:** Whether you understand view factors and can apply summation and reciprocity rules.

### Q24. Radiation shields. [M]
**A:** Radiation shield: thin, low-emissivity sheet placed between two surfaces to reduce radiation heat transfer. For n shields between two surfaces: Q_with_shields = Q_without / (n+1) (if all surfaces have same emissivity). With different emissivities: Q = sigma*A*(T1^4-T2^4)/(1/epsilon1 + 1/epsilon2 - 1 + n*(2/epsilon_shield - 1)).
**Push:** How many shields are needed to reduce radiation by 50%? -> For equal emissivities: Q_with = Q_without/(n+1). For 50% reduction: 1/(n+1) = 0.5 -> n+1 = 2 -> n = 1. One shield reduces radiation by 50%.
**Trap:** Saying shields reduce radiation by 1/(n+1) regardless of emissivity - this is only true if all surfaces have the same emissivity.
**What they're really testing:** Whether you can calculate the effect of radiation shields.

### Q25. Solar radiation and greenhouse effect. [L]
**A:** Solar radiation: electromagnetic radiation from sun, peak wavelength ~0.5 microns (visible). Earth receives ~1367 W/m2 at top of atmosphere (solar constant). Greenhouse effect: glass/transparent materials transmit short-wave solar radiation but block long-wave infrared radiation emitted by warm surfaces, causing temperature rise. Used in solar collectors, greenhouses, and explains global warming.
**Push:** Why does a greenhouse get warm? -> Short-wave solar radiation passes through glass and warms surfaces inside. Warm surfaces emit long-wave infrared that cannot pass through glass, so heat is trapped.
**Trap:** Thinking greenhouse effect is only about CO2 - the basic physics is about wavelength-selective transmission through transparent materials.
**What they're really testing:** Whether you understand solar radiation and the greenhouse effect.

### Q26. Radiation exchange between surfaces. [M]
**A:** For two surfaces forming an enclosure: Q_12 = (sigma*(T1^4-T2^4))/( (1-epsilon1)/(epsilon1*A1) + 1/(A1*F_12) + (1-epsilon2)/(epsilon2*A2) ). For concentric cylinders/spheres: Q = sigma*A1*(T1^4-T2^4)/(1/epsilon1 + (A1/A2)*(1/epsilon2-1)). For large enclosure (A2 >> A1): Q = epsilon1*sigma*A1*(T1^4-T2^4).
**Push:** What simplifies when one surface is much larger than the other? -> The smaller surface sees the larger as a blackbody enclosure, so Q = epsilon1*sigma*A1*(T1^4-T2^4).
**Trap:** Using the parallel plate formula for non-parallel or non-enclosure geometries - must account for view factors.
**What they're really testing:** Whether you can calculate radiation exchange between surfaces.

### Q27. Radiation properties: absorptivity, reflectivity, transmissivity. [M]
**A:** For any surface: alpha + rho + tau = 1 (absorptivity + reflectivity + transmissivity). For opaque surfaces: alpha + rho = 1. For blackbody: alpha = 1, rho = 0, tau = 0. For specular reflection: angle of reflection = angle of incidence. For diffuse reflection: reflected radiation is uniform in all directions. Kirchhoff's law: for a surface in thermal equilibrium, epsilon = alpha (at same wavelength and temperature).
**Push:** What is the difference between specular and diffuse reflection? -> Specular: mirror-like, reflection angle = incidence angle. Diffuse: scattered in all directions (like matte paint).
**Trap:** Saying all surfaces are diffuse reflectors - some surfaces (mirrors, polished metals) are specular.
**What they're really testing:** Whether you understand radiation properties and their relationships.

### Q28. Thermal radiation in furnaces and boilers. [M]
**A:** In furnaces, radiation is the dominant heat transfer mode. Gas radiation: CO2 and H2O vapour are strong infrared absorbers/emitters. Luminous flames (soot) have high emissivity. Non-luminous flames (clean gas) have lower emissivity. Furnace design: maximize view factor from flame to heat transfer surfaces, use refractory walls to reflect radiation, maintain high flame temperature.
**Push:** Why are furnace walls lined with refractory material? -> To reflect radiation back into the furnace, maintaining high temperature and improving heat transfer to the tubes.
**Trap:** Treating furnace gases as transparent - CO2 and H2O vapour are strong infrared absorbers and emitters.
**What they're really testing:** Whether you understand radiation in high-temperature industrial applications.

## 4. Heat Exchangers - 12 questions

### Q29. Heat exchanger types. [H]
**A:** Types: (1) Concentric tube (double pipe) - simple, good for high pressure. (2) Shell and tube - most common in industry, good for large duties. (3) Plate - high effectiveness, compact, good for low viscosity. (4) Regenerative - stores heat in matrix, used in gas turbines and Stirling engines. Flow arrangements: parallel flow (same direction), counter flow (opposite direction, higher effectiveness), cross flow (one fluid mixed, other unmixed).
**Push:** Why is counter flow preferred over parallel flow? -> Counter flow maintains a larger temperature difference between fluids throughout the exchanger, giving higher effectiveness and requiring less surface area.
**Trap:** Saying parallel flow is never used - it's used when outlet temperature of cold fluid must not exceed inlet temperature of hot fluid (temperature cross).
**What they're really testing:** Whether you know heat exchanger types and flow arrangements.

### Q30. LMTD method. [H]
**A:** LMTD (Log Mean Temperature Difference): Q = U*A*LMTD, where LMTD = (delta_T1 - delta_T2)/ln(delta_T1/delta_T2). For counter flow: delta_T1 = T_h,in - T_c,out, delta_T2 = T_h,out - T_c,in. For parallel flow: delta_T1 = T_h,in - T_c,in, delta_T2 = T_h,out - T_c,out. LMTD correction factor F for multi-pass or cross flow.
**Push:** Why is LMTD used instead of arithmetic mean? -> Because temperature difference varies along the exchanger. LMTD is the correct average for exponential temperature variation.
**Trap:** Using arithmetic mean temperature difference instead of LMTD - gives wrong Q for large temperature differences.
**What they're really testing:** Whether you can use LMTD method for heat exchanger design.

### Q31. Effectiveness-NTU method. [H]
**A:** Effectiveness epsilon = Q_actual/Q_max = (actual heat transfer)/(maximum possible heat transfer). NTU = U*A/C_min (number of transfer units). Effectiveness depends on NTU and C_r = C_min/C_max (capacity ratio). For counter flow: epsilon = (1 - exp(-NTU*(1-C_r)))/(1 - C_r*exp(-NTU*(1-C_r))). For parallel flow: epsilon = (1 - exp(-NTU*(1+C_r)))/(1+C_r). Effectiveness-NTU is used when outlet temperatures are unknown.
**Push:** When do you use LMTD vs Effectiveness-NTU? -> LMTD when all four temperatures are known. Effectiveness-NTU when outlet temperatures are unknown (design problem).
**Trap:** Using LMTD when outlet temperatures are unknown - you can't calculate LMTD without all temperatures.
**What they're really testing:** Whether you can use Effectiveness-NTU method for heat exchanger design.

### Q32. Heat exchanger effectiveness. [H]
**A:** Effectiveness epsilon = Q_actual/Q_max, where Q_max = C_min*(T_h,in - T_c,in). epsilon ranges from 0 to 1. Higher epsilon means better heat transfer. For a given NTU, counter flow has highest effectiveness, parallel flow has lowest. As NTU -> infinity, epsilon -> 1 for counter flow (with C_r < 1), but epsilon -> 1/(1+C_r) for parallel flow.
**Push:** What is the maximum possible effectiveness for parallel flow? -> As NTU -> infinity, epsilon -> 1/(1+C_r). For C_r = 1 (equal capacity rates), max epsilon = 0.5.
**Trap:** Thinking effectiveness can always reach 1 - for parallel flow with equal capacity rates, maximum effectiveness is 0.5.
**What they're really testing:** Whether you understand effectiveness and its limits for different flow arrangements.

### Q33. Fouling in heat exchangers. [M]
**A:** Fouling is accumulation of unwanted material on heat transfer surfaces, reducing U and increasing pressure drop. Types: (1) Particulate (sediment), (2) Crystallization (scaling), (3) Biological (biofilm), (4) Chemical reaction (corrosion products), (5) Freezing. Fouling factor R_f = 1/U_dirty - 1/U_clean. Design with fouling factor to ensure performance over time. Cleaning methods: chemical, mechanical (brushing), ultrasonic.
**Push:** How does fouling affect heat exchanger design? -> Design with a fouling factor (R_f) added to thermal resistance. This increases required area by 10-30% depending on fluid.
**Trap:** Ignoring fouling in design - leads to undersized exchangers that fail to meet duty after a few months.
**What they're really testing:** Whether you understand fouling and can account for it in heat exchanger design.

### Q34. Shell and tube heat exchanger design. [M]
**A:** Shell and tube: tubes in a shell, baffles direct flow. Design parameters: (1) Number of tube passes (1, 2, 4, 6...), (2) Baffle type (segmental, disc-donut, rod), (3) Baffle spacing (affects pressure drop and vibration), (4) Tube pitch (triangular or square), (5) Shell diameter. Standards: TEMA (Tubular Exchanger Manufacturers Association) specifies design rules.
**Push:** What is the purpose of baffles in a shell and tube exchanger? -> Baffles direct shell-side flow across tubes (increasing h), support tubes (preventing vibration), and increase residence time.
**Trap:** Saying baffles only support tubes - they primarily direct flow for better heat transfer.
**What they're really testing:** Whether you understand shell and tube exchanger design and baffle function.

### Q35. Compact heat exchangers. [M]
**A:** Compact heat exchangers have high surface area per volume (> 700 m2/m3). Types: plate-fin, tube-fin, printed circuit. Used where space and weight are critical: automotive, aerospace, HVAC. Advantages: high effectiveness, small size. Disadvantages: high pressure drop, difficult to clean, limited pressure/temperature range.
**Push:** When would you use a compact heat exchanger instead of shell and tube? -> When space/weight is limited (automotive, aerospace), or for gas-gas applications where high surface area is needed.
**Trap:** Using compact exchangers for high-pressure or dirty fluids - they are difficult to clean and have pressure limits.
**What they're really testing:** Whether you can select the right heat exchanger type for given constraints.

### Q36. Regenerative heat exchangers. [M]
**A:** Regenerative heat exchanger: heat is stored in a matrix (rotating or fixed) and transferred between hot and cold streams alternately. Types: rotary (rotating matrix), fixed-bed (periodic switching). Used in gas turbines (regenerator), Stirling engines, and air preheaters. Effectiveness can be very high (> 90%) because the matrix approaches the temperature of the hot fluid.
**Push:** Why are regenerators used in gas turbines? -> To recover exhaust heat and preheat combustion air, improving cycle efficiency by 5-10 percentage points.
**Trap:** Confusing regenerative with recuperative - regenerative uses a matrix, recuperative uses a continuous heat transfer surface.
**What they're really testing:** Whether you understand regenerative heat exchangers and their applications.

### Q37. Heat exchanger sizing: area calculation. [M]
**A:** Heat exchanger area A = Q/(U*LMTD) for LMTD method, or A = NTU*C_min/U for Effectiveness-NTU method. Overall U includes: convection on both sides, conduction through wall, and fouling. For shell and tube: A = N_tubes * pi * D_o * L (outside surface area). Pressure drop check: delta_P = f*(L/D)*rho*v^2/2 + minor losses.
**Push:** What is the typical U value for water-water heat exchanger? -> ~500-1000 W/m2-K. For gas-gas: ~10-50 W/m2-K. For condensing steam-water: ~1000-3000 W/m2-K.
**Trap:** Using clean U values without fouling factor - leads to undersized exchangers.
**What they're really testing:** Whether you can size a heat exchanger and check pressure drop.

### Q38. Pinch analysis. [L]
**A:** Pinch analysis is a methodology for optimizing heat exchanger networks in process plants. It identifies the minimum energy requirement (MER) and minimum number of heat exchangers. Key concepts: composite curves (plotting temperature vs enthalpy), pinch point (where heat transfer is most constrained), and grand composite curve. Used to minimize utility (steam, cooling water) consumption.
**Push:** What is the pinch point? -> The point of minimum temperature difference between hot and cold composite curves. Heat cannot be transferred across the pinch without external utilities.
**Trap:** Thinking pinch analysis is only for heat exchanger design - it's for optimizing entire heat exchanger networks.
**What they're really testing:** Whether you understand pinch analysis for process heat integration.

### Q39. Heat pipes. [M]
**A:** Heat pipe: sealed tube with working fluid that evaporates at hot end and condenses at cold end, transferring heat with very high effective thermal conductivity (1000-100000 W/m-K). Components: evaporator (heat input), adiabatic section, condenser (heat output). Working fluid selection: water (100-200 deg C), ammonia (-60 to 100 deg C), sodium (500-1200 deg C). Used in electronics cooling, spacecraft, and solar collectors.
**Push:** Why is heat pipe thermal conductivity so high? -> Because phase change (evaporation/condensation) transfers large amounts of latent heat with small temperature difference, not conduction through solid.
**Trap:** Thinking heat pipe is a solid conductor - it's a two-phase heat transfer device.
**What they're really testing:** Whether you understand heat pipe operation and applications.

### Q40. Heat exchanger log mean temperature difference correction. [M]
**A:** For multi-pass or cross-flow heat exchangers, LMTD must be corrected: LMTD_corrected = F * LMTD_counterflow. F is correction factor (0 to 1) from charts based on P = (T_c,out - T_c,in)/(T_h,in - T_c,in) and R = (T_h,in - T_h,out)/(T_c,out - T_c,in). F < 1 because multi-pass arrangement is less efficient than pure counter flow.
**Push:** What is the minimum acceptable F value? -> Typically F > 0.75. Below 0.75, consider redesigning the exchanger (more passes, different arrangement).
**Trap:** Using uncorrected LMTD for multi-pass exchangers - gives wrong area calculation.
**What they're really testing:** Whether you can apply LMTD correction for multi-pass heat exchangers.

## 5. Advanced Topics - 10 questions

### Q41. Thermal diffusivity and its significance. [M]
**A:** Thermal diffusivity alpha = k/(rho*c_p) (m2/s). It measures how quickly heat spreads through a material. High alpha = heat spreads fast (metals). Low alpha = heat spreads slowly (insulators). Governs transient heat conduction: temperature response time proportional to L^2/alpha. Steel: alpha ~ 1.2e-5 m2/s. Water: alpha ~ 1.4e-7 m2/s.
**Push:** Why is thermal diffusivity important in transient problems? -> It determines how quickly temperature changes propagate through a material. Higher alpha means faster temperature equilibration.
**Trap:** Confusing thermal diffusivity with thermal conductivity - diffusivity includes density and specific heat, conductivity doesn't.
**What they're really testing:** Whether you understand thermal diffusivity and its role in transient conduction.

### Q42. Finned surfaces for heat exchangers. [M]
**A:** Finned surfaces increase heat transfer area, used when one fluid has much lower h than the other (gas side of air-cooled exchangers). Fin types: (1) Longitudinal (parallel to flow), (2) Radial (annular fins on tubes), (3) Plate-fin (stacked plates). Fin efficiency decreases with fin length. Fin spacing affects pressure drop and fouling. Materials: aluminium (light, conductive), copper (very conductive), steel (high temperature).
**Push:** Why are fins added to the gas side, not the liquid side? -> Because gas h is much lower (10-100) than liquid h (500-10000). Fins compensate for the low gas-side h by increasing area.
**Trap:** Adding fins to both sides - wasteful; fins should be on the side with lower h.
**What they're really testing:** Whether you can design finned surfaces and understand when they're needed.

### Q43. Heat transfer in packed beds. [L]
**A:** Packed bed: solid particles packed in a container, fluid flows through void spaces. Heat transfer: convection between fluid and particles, conduction through particles and contact points. Effective thermal conductivity depends on particle conductivity, void fraction, and fluid conductivity. Used in: chemical reactors, thermal storage, and drying processes.
**Push:** What is the void fraction in a packed bed? -> Volume of voids / total volume. Typically 0.3-0.5 for random packing, lower for ordered packing.
**Trap:** Using solid conductivity for packed bed - effective conductivity is much lower due to void spaces and contact resistance.
**What they're really testing:** Whether you understand heat transfer in porous media.

### Q44. Thermal stress in heat exchangers. [M]
**A:** Thermal stress occurs when temperature gradients cause differential expansion. In heat exchangers: (1) Tube-to-tubesheet joint stress (differential expansion between shell and tubes), (2) Baffle cut stress (flow-induced vibration + thermal), (3) Nozzle stress (thermal shock). Design: use expansion joints (bellows, slip joints) for large temperature differences, or use U-tube bundles that can expand freely.
**Push:** How do you handle thermal expansion in a shell and tube exchanger? -> Use U-tube bundle (tubes can expand freely), or add expansion joint (bellows) in shell, or use floating head design.
**Trap:** Ignoring thermal expansion - can cause tube-to-tubesheet joint failure or shell cracking.
**What they're really testing:** Whether you understand thermal stress in heat exchangers and can design for it.

### Q45. Heat transfer in microchannels. [L]
**A:** Microchannels: channels with hydraulic diameter < 1 mm. Heat transfer: enhanced due to high surface area to volume ratio. Single-phase: Nu ~ constant (3.66 for circular), but h is high due to small D. Two-phase: boiling in microchannels has different regimes (confined boiling). Applications: electronics cooling, microreactors, compact heat exchangers.
**Push:** Why is heat transfer enhanced in microchannels? -> High surface area to volume ratio (A/V ~ 1/D) gives high h for given volume. Also, short thermal entry length means fully developed flow quickly.
**Trap:** Applying macroscale correlations to microchannels - surface effects and rarefaction effects become significant.
**What they're really testing:** Whether you understand heat transfer in microscale devices.

### Q46. Thermal energy storage. [M]
**A:** Thermal energy storage (TES): store heat for later use. Types: (1) Sensible heat (water, rock, concrete) - store heat by temperature change. (2) Latent heat (phase change materials, PCM) - store heat by phase change at constant temperature. (3) Thermochemical - store heat by chemical reaction. Applications: solar thermal plants, building HVAC, industrial waste heat recovery.
**Push:** What is the advantage of latent heat storage over sensible heat? -> Higher energy density (latent heat >> sensible heat for same volume), and constant temperature during discharge (better for process heating).
**Trap:** Thinking TES is only for solar - it's used in many industrial applications for load shifting and waste heat recovery.
**What they're really testing:** Whether you understand thermal energy storage types and applications.

### Q47. Heat transfer in nanofluids. [L]
**A:** Nanofluids: base fluid (water, oil) with nanoparticles (metal, metal oxide, carbon) suspended. Enhanced thermal conductivity (10-50% increase) and heat transfer coefficient. Mechanism: Brownian motion of nanoparticles, thermal conductivity enhancement, and boundary layer modification. Challenges: stability, agglomeration, increased viscosity, cost.
**Push:** What is the main challenge with nanofluids? -> Stability - nanoparticles tend to agglomerate and settle over time, reducing enhancement. Surface modification and surfactants are used to improve stability.
**Trap:** Thinking nanofluids are ready for commercial use - they are still primarily research-stage due to stability and cost issues.
**What they're really testing:** Whether you understand nanofluid heat transfer and current limitations.

### Q48. Heat transfer in porous media. [L]
**A:** Porous media: solid matrix with interconnected pores. Heat transfer: conduction through solid and fluid, convection between solid and fluid, radiation in high-temperature pores. Effective properties: effective thermal conductivity, permeability, porosity. Used in: catalytic reactors, fuel cells, thermal insulation, and geothermal systems.
**Push:** What is Darcy's law for flow in porous media? -> v = -(k/mu)*dp/dx, where k is permeability (m2), mu is viscosity. Flow is proportional to pressure gradient.
**Trap:** Using empty-space properties for porous media - effective properties are different due to solid matrix and tortuosity.
**What they're really testing:** Whether you understand heat transfer in porous media.

### Q49. Heat transfer coefficient measurement. [M]
**A:** Methods to measure h: (1) Direct: measure Q, A, delta_T, calculate h = Q/(A*delta_T). (2) Inverse: measure temperature distribution, solve inverse heat conduction problem. (3) Transient: lumped capacitance method, h = rho*c*V/(A*tau). (4) Wilson plot: vary flow rate, plot 1/U vs 1/h, extract h from slope.
**Push:** What is the Wilson plot method? -> Plot 1/U vs 1/(flow rate)^0.8. The slope gives the convection resistance on the variable-flow side, and the intercept gives the other resistances.
**Trap:** Measuring h at a single point and assuming it's uniform - h varies with position and flow conditions.
**What they're really testing:** Whether you can measure heat transfer coefficients and understand the methods.

### Q50. Heat transfer in buildings. [M]
**A:** Building heat transfer: (1) Conduction through walls, roof, floor (U-values). (2) Convection (natural ventilation, forced HVAC). (3) Solar radiation through windows (solar gain). (4) Infiltration (air leakage). Thermal comfort: PMV (Predicted Mean Vote) based on temperature, humidity, air velocity, clothing, activity. Energy efficiency: insulation, double glazing, thermal mass, passive solar design.
**Push:** What is the U-value of a wall? -> Overall heat transfer coefficient including all layers and surface resistances. Typical: uninsulated brick wall U ~ 2.0 W/m2-K, insulated wall U ~ 0.3 W/m2-K.
**Trap:** Using thermal conductivity instead of U-value for building envelope - U-value includes convection resistances on both sides.
**What they're really testing:** Whether you understand building heat transfer and energy efficiency.

## File Statistics

**Total questions: 50**

**By tag:**
- [H] High-yield: ~18 questions
- [M] Medium-yield: ~26 questions
- [L] Occasional: ~6 questions

**By section:**
- Conduction fundamentals: 10 questions
- Convection: 10 questions
- Radiation: 8 questions
- Heat exchangers: 12 questions
- Advanced topics: 10 questions

**Standard values used consistently:** k_steel=50 W/m-K, k_copper=400, sigma=5.67e-8, g=9.81, pi=3.1416, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers Heat Transfer - essential for automobiles, petrochem, and construction interviews.