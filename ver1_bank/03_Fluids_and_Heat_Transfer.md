# Fluid Mechanics and Heat Transfer - L&T GET technical interview bank

**Part 3 of 8 | 28 questions | Fluid mechanics fundamentals and heat transfer modes with plant applications**

*Mechanical GET panel, 30-45 min, GATE-lite depth.
*Note on format: in this file the answer to the **Push:** question is given on its own **A:** line directly beneath it, so you will see two A lines per question.*
 Tags: [H] asked very commonly, [M] asked regularly, [L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing recall, they are testing whether you can reason out loud.*

## 1. Fluid Mechanics - 16 questions

### Q1. Define dynamic viscosity and kinematic viscosity. What is the difference, and what are their units? [H]

**A:** Dynamic viscosity (mu) is the fluid's internal resistance to shear, defined by tau = mu * (du/dy). Its unit is Pa-s or N-s/m2. Kinematic viscosity (nu) is dynamic viscosity divided by density (nu = mu/rho), representing momentum diffusivity. Its unit is m2/s. In practice, kinematic viscosity is used in Reynolds number and pipe flow correlations because it combines the fluid's viscous and inertial properties.

**Push:** How does viscosity change with temperature for liquids vs gases?
**A:** For liquids, viscosity decreases with temperature rise because cohesive forces weaken. For gases, viscosity increases with temperature because molecular momentum transfer increases.

**Trap:** Saying "viscosity always decreases with temperature" - this is only true for liquids, not gases.

### Q2. State Newton's law of viscosity. What is a Newtonian fluid? Give examples of non-Newtonian fluids. [H]

**A:** Newton's law states that shear stress is directly proportional to the velocity gradient: tau = mu * (du/dy). A Newtonian fluid has constant viscosity independent of shear rate. Water, air, and most oils are Newtonian. Non-Newtonian examples: blood (shear-thinning), ketchup (yield stress + shear-thinning), cornstarch slurry (shear-thickening), drilling mud (Bingham plastic).

**Push:** How would you determine if a fluid is Newtonian experimentally?
**A:** Plot shear stress vs shear rate. A straight line through origin means Newtonian; any other curve means non-Newtonian.

**Trap:** Calling all oils Newtonian - some polymer-thickened lubricants are non-Newtonian at high shear rates.

### Q3. Derive the continuity equation for steady incompressible flow in a pipe. What changes for a branching pipe? [H]

**A:** For steady flow, mass entering = mass leaving. For incompressible flow, rho is constant, so rho * A1 * v1 = rho * A2 * v2, giving A1*v1 = A2*v2 or Q = A*v = constant. For a branching pipe with one inlet and multiple outlets, the sum of outlet flow rates equals the inlet flow rate: Q_in = Q_out1 + Q_out2 + ...

**Push:** If a 200 mm pipe splits into two 150 mm pipes and velocity in one branch is 3 m/s, what is the velocity in the other branch if total flow is 0.1 m3/s?
**A:** Q_total = 0.1 m3/s. Q1 = (pi/4)*0.15^2*3 = 0.053 m3/s. Q2 = 0.1 - 0.053 = 0.047 m3/s. v2 = Q2/A2 = 0.047/0.0177 = 2.66 m/s.

**Trap:** Applying A1*v1 = A2*v2 to each branch individually without conserving total mass.

### Q4. State Bernoulli's equation and list all its assumptions. How do you derive it from Euler's equation? [H]

**A:** Bernoulli: p/rho*g + v^2/2g + z = constant along a streamline. Assumptions: steady flow, incompressible fluid, inviscid (no friction), along a single streamline, no energy addition/removal (no pump/turbine between points). Derivation from Euler: Start with Euler's equation along a streamline: dp/rho + v*dv + g*dz = 0. Integrate: int(dp/rho) + v^2/2 + gz = constant. For incompressible flow, int(dp/rho) = p/rho, giving p/rho + v^2/2 + gz = constant.

**Push:** Can you apply Bernoulli across a pump?
**A:** No, because a pump adds energy. You need the extended Bernoulli with head added: p1/rho*g + v1^2/2g + z1 + H_pump = p2/rho*g + v2^2/2g + z2 + h_loss.

**Trap:** Applying Bernoulli between points in different streamlines, or across a valve/pump without accounting for losses or work.

### Q5. Explain the venturi meter principle. What is the discharge coefficient Cd and why is it less than 1? [H]

**A:** Venturi meter measures flow rate by creating a pressure drop through a converging section. From Bernoulli and continuity: Q = Cd * A2 * sqrt(2*(p1-p2)/rho*(1 - (A2/A1)^2)). Cd accounts for viscous losses and non-uniform velocity profiles. Typical Cd = 0.95-0.98 for venturi, lower for orifice (0.6-0.65) because sudden contraction causes flow separation and vena contracta.

**Push:** Why is pressure recovery better in a venturi than an orifice plate?
**A:** Venturi has a gradual diffuser (7-15 deg angle) that prevents boundary layer separation, recovering 80-90% of pressure drop. Orifice has sudden expansion causing massive separation and only 30-50% recovery.

**Trap:** Assuming Cd = 1 for calculations, or confusing venturi Cd with orifice Cd.

### Q6. How does a Pitot tube measure velocity? What is the difference between a Pitot tube and a Pitot-static tube? [H]

**A:** Pitot tube faces upstream, measuring stagnation pressure (p0 = p_static + rho*v^2/2). A simple Pitot tube needs a separate static pressure tap. A Pitot-static tube combines both in one instrument with static ports on the side. Velocity v = sqrt(2*(p0 - p_static)/rho).

**Push:** If a Pitot tube reads 150 mm water gauge above static pressure in air at 1.2 kg/m3, what is the velocity?
**A:** delta_p = rho_water*g*h = 1000*9.81*0.15 = 1471.5 Pa. v = sqrt(2*1471.5/1.2) = 49.5 m/s.

**Trap:** Using the Pitot tube reading directly as velocity pressure without subtracting static pressure, or using the wrong density (air vs water).

### Q7. Define Reynolds number. What are the laminar, transition, and turbulent ranges for pipe flow? What physically changes at transition? [H]

**A:** Re = rho*v*D/mu = v*D/nu. It represents ratio of inertial forces to viscous forces. Pipe flow: laminar below Re = 2300, transition 2300-4000, turbulent above 4000. At transition, flow changes from orderly layers to chaotic eddies, velocity profile flattens from parabolic to nearly uniform, and friction factor jumps from 64/Re to a higher value on the Moody chart.

**Push:** Why is the critical Re for pipe flow 2300 but for flat plate boundary layer it is 5e5?
**A:** Different geometries and instability mechanisms. Pipe flow is confined and becomes unstable to small disturbances at lower Re. Flat plate boundary layer transitions due to Tollmien-Schlichting waves amplified by freestream turbulence.

**Trap:** Using Re = 2300 as a sharp boundary - it is a range, and actual transition depends on pipe roughness, inlet conditions, and disturbances.

### Q8. State the Darcy-Weisbach equation for head loss. What is the friction factor for laminar flow? How do you find it for turbulent flow? [H]

**A:** h_f = f * (L/D) * (v^2/2g). For laminar flow: f = 64/Re exactly. For turbulent flow, f depends on Re and relative roughness (epsilon/D). Use the Moody chart or Colebrook equation: 1/sqrt(f) = -2*log10(epsilon/(3.7*D) + 2.51/(Re*sqrt(f))). For smooth pipes, Blasius approximation: f = 0.316/Re^0.25 (valid 4000 < Re < 1e5).

**Push:** What happens to head loss if you double the flow rate in turbulent flow?
**A:** v doubles, so v^2 quadruples. f changes slightly (decreases with Re^0.25), but overall h_f increases by roughly 3.5-4 times. In laminar flow, h_f is linear with v (since f = 64/Re), so doubling v doubles h_f.

**Trap:** Using f = 64/Re for turbulent flow, or ignoring the Re-dependence of f in turbulent regime.

### Q9. What are minor losses? How do you account for them using K values and equivalent length? [M]

**A:** Minor losses are head losses from fittings, valves, bends, expansions, contractions: h_m = K * v^2/2g. K is dimensionless loss coefficient (e.g., 0.5 for 90° elbow, 10 for fully open globe valve, 1.0 for sudden expansion). Equivalent length Le = K*D/f converts minor loss to an equivalent straight pipe length with same friction loss. Total loss = f*(L/ D)*v^2/2g + sum(K)*v^2/2g.

**Push:** Why does a sudden expansion have K = (1 - A1/A2)^2 while sudden contraction K is smaller?
**A:** Sudden expansion causes flow separation and massive eddies (Borda-Carnot loss). Sudden contraction has vena contracta but flow reattaches smoothly, so loss is mainly from expansion after vena contracta.

**Trap:** Forgetting minor losses in short pipe systems where they can dominate, or using K values for the wrong velocity (upstream vs downstream).

### Q10. Explain how a U-tube manometer works. How do you measure differential pressure between two points? [M]

**A:** U-tube manometer: p1 + rho1*g*h1 = p2 + rho2*g*h2 + rho_m*g*h_m. For differential pressure between two pipes with same fluid: p1 - p2 = (rho_m - rho)*g*h. For gas pressure measurement (rho << rho_m): p_gauge = rho_m*g*h. Inclined manometer increases sensitivity by measuring along the slope: h = L*sin(theta).

**Push:** If mercury manometer shows 200 mm deflection measuring air pressure, what is the gauge pressure?
**A:** p = rho_Hg*g*h = 13600*9.81*0.2 = 26.7 kPa (approx 0.264 bar).

**Trap:** Using the fluid density instead of the manometer fluid density, or forgetting the fluid density correction when both legs contain the process fluid.

### Q11. Describe the working principle of a centrifugal pump. What is NPSH and why is cavitation a problem? [H]

**A:** Centrifugal pump: impeller rotates, imparting kinetic energy to fluid (v^2/2g), converted to pressure in the volute/diffuser. Requires priming (casing filled with liquid) because it cannot pump gas. Total head H = suction head + delivery head + velocity head difference + losses. NPSH available = (p_suction - p_vapour)/rho*g + v^2/2g. NPSH required is a pump characteristic. Cavitation occurs when NPSHa < NPSHr - local pressure drops below vapour pressure, bubbles form and collapse violently, causing noise, vibration, pitting damage, and performance drop.

**Push:** How do you prevent cavitation in a pump installation?
**A:** Increase suction pressure (raise supply tank, reduce suction line losses), reduce fluid temperature (lower vapour pressure), use pump with lower NPSHr (larger impeller eye, lower speed), install booster pump.

**Trap:** Thinking cavitation only happens at the impeller eye - it can also occur in valve seats, propeller blades, and turbine runners.

### Q12. State the affinity laws for centrifugal pumps. If you double the speed, what happens to flow, head, and power? [M]

**A:** For a given pump at constant diameter: Q ~ N, H ~ N^2, P ~ N^3. Double speed (2N): flow doubles, head quadruples, power increases 8 times. For diameter change at constant speed: Q ~ D^3, H ~ D^2, P ~ D^5.

**Push:** A pump delivers 100 m3/h at 30 m head consuming 15 kW at 1450 RPM. What are the values at 2900 RPM?
**A:** Q2 = 200 m3/h, H2 = 120 m, P2 = 120 kW.

**Trap:** Applying affinity laws to different pumps, or when efficiency changes significantly, or ignoring that NPSHr also changes with speed.

### Q13. What is the difference between a centrifugal pump and a positive displacement pump? When would you use each? [M]

**A:** Centrifugal: kinetic energy machine, continuous flow, flow varies with head, not self-priming (usually), good for high flow low head. Positive displacement (reciprocating, gear, screw): traps fixed volume per cycle, constant flow regardless of head (within pressure limits), self-priming, good for high pressure low flow, viscous fluids, metering. Reciprocating gives pulsating flow needing dampeners; rotary PD gives smoother flow.

**Push:** Why does a PD pump need a relief valve on the discharge?
**A:** PD pump will build pressure until something fails if discharge is blocked. Relief valve protects the pump and piping.

**Trap:** Using centrifugal pump for high-viscosity fluid (efficiency drops sharply) or PD pump for high-flow clean water application (overkill, higher cost).

### Q14. Compare impulse and reaction turbines. Name one example of each and where they are used. [H]

**A:** Impulse turbine: pressure drop only in nozzles, blades only change momentum direction (Pelton wheel). Used for high head, low flow (hydro > 300 m head). Reaction turbine: pressure drop across both fixed and moving blades (Francis, Kaplan). Francis: medium head (30-300 m), medium flow. Kaplan: low head (< 30 m), high flow, adjustable blades. In thermal plants: steam turbines are mostly reaction (pressure-compounded impulse stages + reaction stages).

**Push:** Why does a Pelton wheel need a spear valve instead of a simple gate valve?
**A:** Spear valve provides smooth, precise flow control without water hammer, and maintains constant head on the nozzle for efficiency. Gate valve would cause pressure surges and poor part-load efficiency.

**Trap:** Confusing Francis (radial flow) with Kaplan (axial flow), or saying impulse turbines have no pressure drop in blades (there is small pressure drop due to friction).

### Q15. What is boundary layer separation? Why does it increase drag? How does streamlining help? [M]

**A:** Boundary layer separation occurs when adverse pressure gradient (dp/dx > 0) causes flow near wall to reverse. The separation point creates a wake of low-pressure recirculating flow behind the body. Pressure drag increases because rear pressure stays low while front stagnation pressure remains high. Streamlining delays separation by maintaining favorable or mild adverse gradient, keeping flow attached longer, reducing wake size and pressure drag. Friction drag increases slightly but net drag drops.

**Push:** Why does a golf ball have dimples?
**A:** Dimples trigger early transition to turbulent boundary layer, which has more momentum near the wall and resists separation better than laminar layer. This moves separation point rearward, shrinking the wake and reducing pressure drag significantly despite higher skin friction.

**Trap:** Thinking streamlining only reduces skin friction - its main benefit is reducing pressure drag by delaying separation.

### Q16. What is the difference between a free vortex and a forced vortex? Give an example of each. [L]

**A:** Free vortex: no external torque, angular momentum conserved (v*r = constant), velocity increases toward centre, irrotational flow. Example: water draining from a sink, tornado core. Forced vortex: fluid rotates as solid body (v = omega*r), requires external torque, rotational flow (vorticity = 2*omega). Example: fluid in a rotating cylindrical tank, cyclone separator, centrifugal pump impeller passages.

**Push:** Why is the pressure distribution different in forced vs free vortex?
**A:** Forced vortex: p = p0 + 0.5*rho*omega^2*r^2 (parabolic). Free vortex: p = p_inf - 0.5*rho*C^2/r^2 (pressure drops toward centre). In a cyclone, the forced vortex outer region has high pressure at walls, free vortex core has low pressure at centre.

**Trap:** Calling a cyclone purely a free vortex - it has forced vortex outer region and free vortex inner core.

**What they're really testing:** Whether you can apply conservation principles (mass, momentum, energy) to real pipe systems and rotating machinery, and understand where ideal equations break down due to viscosity, turbulence, and separation.

## 2. Heat Transfer - 12 questions

### Q17. State the three modes of heat transfer. Give one equation for each and explain the physical mechanism. [H]

**A:** Conduction: Fourier's law q = -k*A*dT/dx. Heat transfer through molecular collisions in solids/stationary fluids without bulk motion. Convection: Newton's law q = h*A*(Ts - T_inf). Heat transfer between a surface and moving fluid combining conduction at the wall and advection in the bulk. Radiation: Stefan-Boltzmann q = epsilon*sigma*A*(Ts^4 - T_surr^4). Electromagnetic wave emission from matter above 0 K, no medium required, works in vacuum.

**Push:** Which mode dominates in a vacuum?
**A:** Radiation only - conduction and convection require a material medium.

**Trap:** Calling convection "just conduction with fluid motion" - the advection term fundamentally changes the heat transfer mechanism and introduces dependence on flow velocity, geometry, and fluid properties.

### Q18. Derive the thermal resistance for conduction through a plane wall, a hollow cylinder, and a hollow sphere. [H]

**A:** Plane wall: R = L/(k*A). Cylinder: R = ln(r2/r1)/(2*pi*k*L). Sphere: R = (1/r1 - 1/r2)/(4*pi*k). Derivation: Start with Fourier's law in appropriate coordinates, separate variables, integrate from r1 to r2. For cylinder: q = -k*(2*pi*r*L)*dT/dr -> q*dr/r = -2*pi*k*L*dT -> integrate to get q*ln(r2/r1) = 2*pi*k*L*(T1-T2) -> R = ln(r2/r1)/(2*pi*k*L).

**Push:** For a pipe with insulation, which resistance dominates - pipe wall or insulation?
**A:** Usually insulation, because k_insulation << k_pipe (e.g., 0.05 vs 50 W/m-K) and ln(r2/r1) grows with thickness.

**Trap:** Using plane wall formula R = L/kA for cylinders/spheres, or forgetting the 2*pi*L or 4*pi factors.

### Q19. What is the critical radius of insulation? Derive r_c = k/h. What happens below and above it? [H]

**A:** For a cylinder with convection outside, total resistance R_total = ln(r2/r1)/(2*pi*k*L) + 1/(h*2*pi*r2*L). Heat loss q = (T1-T_inf)/R_total. Differentiate q w.r.t r2 and set to zero: dR/dr2 = 0 gives 1/(k*r2) - 1/(h*r2^2) = 0 -> r_c = k/h. Below r_c (r2 < k/h): adding insulation DECREASES total resistance, INCREASES heat loss. Above r_c: adding insulation increases resistance, decreases heat loss. For sphere: r_c = 2k/h. Critical radius is small for typical insulations (k ~ 0.05, h ~ 10 -> r_c = 5 mm), so pipes larger than 10 mm OD always benefit from insulation.

**Push:** Does critical radius exist for plane walls?
**A:** No, because conduction area is constant while convection area is also constant. For plane walls, adding insulation always increases resistance and decreases heat loss.

**Trap:** Thinking you should never insulate small pipes - for pipes below critical radius (rare), insulation increases heat loss, but these are typically not insulated anyway or have h very low (natural convection) making r_c larger.

### Q20. Explain the Nusselt number and Reynolds analogy. What is the physical significance of Nu? [M]

**A:** Nusselt number Nu = h*L/k = convection heat transfer / conduction heat transfer across the boundary layer. It represents the dimensionless temperature gradient at the wall. Reynolds analogy: St = Cf/2 where St = Nu/(Re*Pr) is Stanton number, Cf is skin friction coefficient. It links momentum transfer (friction) to heat transfer (convection) through boundary layer similarity. Valid for Pr approx 1 (gases).

**Push:** For turbulent flow in a pipe, what correlation would you use for Nu?
**A:** Dittus-Boelter: Nu = 0.023*Re^0.8*Pr^n where n = 0.4 for heating, 0.3 for cooling. Valid for Re > 10000, 0.7 < Pr < 160, L/D > 60.

**Trap:** Using laminar correlations (Nu = 3.66 constant) for turbulent flow, or forgetting the Prandtl number exponent difference for heating vs cooling.

### Q21. State the Stefan-Boltzmann law. What are emissivity, absorptivity, and reflectivity? How are they related for a grey body? [M]

**A:** E_b = sigma*T^4 (black body emissive power, sigma = 5.67e-8 W/m2-K4). Real surface: E = epsilon*E_b. Emissivity epsilon = E/E_b (0 to 1). Absorptivity alpha = absorbed/incident radiation. Reflectivity rho = reflected/incident. For opaque surface: alpha + rho = 1. Kirchhoff's law: at thermal equilibrium, epsilon = alpha. Grey body: epsilon constant with wavelength. Black body: epsilon = 1, alpha = 1, rho = 0.

**Push:** If a surface has epsilon = 0.8 at 500 K, what is its absorptivity for radiation from a source at 1500 K?
**A:** For a grey body, epsilon is wavelength-independent, so alpha = epsilon = 0.8 regardless of source temperature. For a real (non-grey) surface, alpha depends on the source spectrum and may differ from epsilon at the surface temperature.

**Trap:** Assuming alpha = epsilon always - only true at thermal equilibrium or for grey surfaces. For non-grey surfaces, alpha depends on the incident radiation spectrum.

### Q22. What is the view factor (shape factor)? State the reciprocity and summation rules. [M]

**A:** View factor F_ij = fraction of radiation leaving surface i that directly strikes surface j. Reciprocity: A_i*F_ij = A_j*F_ji. Summation: sum_j F_ij = 1 for an enclosure (all radiation leaving i must hit some surface in the enclosure). For N surfaces, there are N^2 view factors, but only N(N-1)/2 independent ones due to these rules.

**Push:** What is F_11 for a convex surface? For a concave surface?
**A:** Convex: F_11 = 0 (no self-viewing). Concave: F_11 > 0 (can see itself).

**Trap:** Forgetting the area weighting in reciprocity, or assuming F_ij = F_ji without the area ratio.

### Q23. Explain the LMTD method for heat exchanger analysis. When do you use the correction factor F? [H]

**A:** LMTD = (delta_T1 - delta_T2)/ln(delta_T1/delta_T2) for counterflow. Heat transfer Q = U*A*LMTD. For crossflow, multipass, or other complex flows, actual mean temperature difference is less than counterflow LMTD: Q = U*A*F*LMTD_counterflow. F is a correction factor (0 < F <= 1) depending on geometry, number of passes, and temperature ratios P = (t2-t1)/(T1-t1), R = (T1-T2)/(t2-t1). F is found from charts.

**Push:** What is the minimum value of F for a feasible design?
**A:** Typically F > 0.75-0.80. Below this, the configuration is inefficient and you should change flow arrangement or add passes.

**Trap:** Using counterflow LMTD directly for a 1-2 shell-and-tube exchanger without the F factor, or calculating LMTD for parallel flow when the exchanger is counterflow.

### Q24. What is the effectiveness-NTU method? Define effectiveness and NTU. When is it preferred over LMTD? [M]

**A:** Effectiveness epsilon = actual heat transfer / maximum possible heat transfer = Q / (C_min*(Th_in - Tc_in)). NTU = U*A/C_min (number of transfer units). For any flow arrangement, epsilon = f(NTU, C_r) where C_r = C_min/C_max. Preferred when outlet temperatures are unknown (sizing problem) because LMTD requires iterative solution. Also useful for comparing exchanger performance independent of flow rates.

**Push:** What is the maximum possible effectiveness for a counterflow exchanger?
**A:** epsilon_max = 1 when NTU -> infinity and C_r < 1. For C_r = 1, epsilon = NTU/(1+NTU) approaches 1 asymptotically. For parallel flow, epsilon_max = 1/(1+C_r) < 1.

**Trap:** Using LMTD when both outlet temperatures are unknown - it becomes an iterative trial-and-error problem. NTU method gives direct solution.

### Q25. What is fouling factor? How does it affect heat exchanger performance? [M]

**A:** Fouling factor R_f = 1/h_foul is the additional thermal resistance from deposits on heat transfer surfaces (scale, corrosion, biological growth, particulates). Overall U_clean = 1/(1/hi + 1/ho + R_wall). U_fouled = 1/(1/hi + 1/ho + R_wall + R_fi + R_fo). Fouling reduces U, decreases heat transfer, increases pressure drop, requires larger area or higher flow rates. Typical values: cooling water 0.0002-0.0005 m2-K/W, steam condensate 0.0001, oil 0.0005-0.001.

**Push:** How do you account for fouling in heat exchanger design?
**A:** Design with U_design = 1/(1/U_clean + R_f) or specify excess area (typically 15-30% over clean requirement). Include fouling factors from TEMA standards.

**Trap:** Ignoring fouling in design - a clean exchanger will meet duty initially but degrade rapidly in service.

### Q26. Explain the function of an economiser, superheater, and condenser in a boiler/steam cycle. [H]

**A:** Economiser: preheats feedwater using flue gas heat (lowest temperature heat recovery), improves cycle efficiency. Superheater: heats saturated steam to superheated state at constant pressure, increases turbine work and efficiency, prevents blade erosion from moisture. Condenser: condenses exhaust steam at constant pressure/temperature, rejects latent heat to cooling water, maintains low turbine back pressure (vacuum), returns condensate to cycle. In a boiler, the economiser is in the flue gas path after the superheater/reheater.

**Push:** Why is the condenser pressure kept as low as possible?
**A:** Lower condenser pressure (higher vacuum) increases the enthalpy drop across the turbine, increasing work output and cycle efficiency. Typical condenser pressure: 0.03-0.08 bar (3-8 kPa) corresponding to 25-40 deg C saturation temperature.

**Trap:** Confusing economiser (feedwater heater using flue gas) with feedwater heater (using extraction steam) - both preheat feedwater but use different heat sources.

### Q27. Why are turbine blades cooled? What is regenerative feedwater heating and how does it improve efficiency? [M]

**A:** Modern gas/steam turbines operate at inlet temperatures (1400-1600 deg C) exceeding blade material limits (~1100 deg C). Blades are cooled by bleeding compressor air (gas turbine) or steam (steam turbine) through internal passages and film cooling holes. Regenerative feedwater heating: bleed steam from turbine stages heats feedwater in closed/open heaters before boiler. This raises average temperature of heat addition, reducing irreversibility, improving cycle efficiency by 10-15%. Typical plant has 5-7 feedwater heaters.

**Push:** What is the trade-off in regenerative heating?
**A:** Bleeding steam reduces turbine work output, but the reduction in boiler heat input is proportionally larger, so net efficiency increases. The optimal number of heaters balances efficiency gain against cost/complexity.

**Trap:** Thinking blade cooling air/steam is "free" - it reduces turbine work because it bypasses expansion stages.

### Q28. Why are steam pipes lagged (insulated)? What happens if lagging is damaged or missing? [L]

**A:** Lagging reduces heat loss from steam pipes, maintaining steam quality (dryness fraction), reducing fuel consumption, and preventing condensation that causes water hammer. Missing/damaged lagging causes: increased heat loss (energy waste), steam condensation -> water hammer risk (slug of water at high velocity damages fittings), reduced steam temperature at point of use, safety hazard (hot surfaces), potential freezing of condensate in cold weather.

**Push:** What is the typical heat loss from a bare 100 mm steam pipe at 10 bar vs insulated?
**A:** Bare: ~3000-4000 W/m. With 50 mm insulation: ~100-150 W/m. Insulation pays back in weeks.

**Trap:** Using asbestos-containing lagging (banned) or insulation without proper vapour barrier on cold lines (causes corrosion under insulation).

**What they're really testing:** Whether you understand heat transfer equipment (exchangers, boilers, turbines) as integrated systems where conduction, convection, and radiation interact, and where practical issues (fouling, condensation, material limits) drive design decisions.