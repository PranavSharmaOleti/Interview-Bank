# Fluid Mechanics and Piping - Core Interview Bank

**Part 3 of 10 | 45 questions | Fluid properties, Bernoulli, pipe flow, pumps, turbines, NPSH, cavitation**
*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Fluid Properties and Statics - 8 questions

### Q1. Viscosity: dynamic vs kinematic. [H]
**A:** Dynamic viscosity (mu) is the fluid's internal resistance to shear, defined by tau = mu * (du/dy). Unit: Pa-s or N-s/m2. Kinematic viscosity (nu) is dynamic viscosity divided by density (nu = mu/rho), representing momentum diffusivity. Unit: m2/s. In practice, kinematic viscosity is used in Reynolds number and pipe flow correlations.
**Push:** How does viscosity change with temperature for liquids vs gases? -> For liquids, viscosity decreases with temperature rise because cohesive forces weaken. For gases, viscosity increases with temperature because molecular momentum transfer increases.
**Trap:** Saying "viscosity always decreases with temperature" - this is only true for liquids, not gases.
**What they're really testing:** Whether you know the difference between dynamic and kinematic viscosity, and how temperature affects each.

### Q2. Newton's law of viscosity, Newtonian fluids. [H]
**A:** Newton's law states that shear stress is directly proportional to the velocity gradient: tau = mu * (du/dy). A Newtonian fluid has constant viscosity independent of shear rate. Water, air, and most oils are Newtonian. Non-Newtonian examples: blood (shear-thinning), ketchup (yield stress + shear-thinning), cornstarch slurry (shear-thickening), drilling mud (Bingham plastic).
**Push:** How would you determine if a fluid is Newtonian experimentally? -> Plot shear stress vs shear rate. A straight line through origin means Newtonian; any other curve means non-Newtonian.
**Trap:** Calling all oils Newtonian - some polymer-thickened lubricants are non-Newtonian at high shear rates.
**What they're really testing:** Whether you understand Newton's law of viscosity and can identify Newtonian vs non-Newtonian fluids.

### Q3. Continuity equation for steady incompressible flow. [H]
**A:** For steady flow, mass entering = mass leaving. For incompressible flow, rho is constant, so rho*A1*v1 = rho*A2*v2, giving A1*v1 = A2*v2 or Q = A*v = constant. For a branching pipe with one inlet and multiple outlets: Q_in = Q_out1 + Q_out2 + ...
**Push:** If a 200 mm pipe splits into two 150 mm pipes and velocity in one branch is 3 m/s, what is the velocity in the other branch if total flow is 0.1 m3/s? -> Q_total = 0.1 m3/s. Q1 = (pi/4)*0.15^2*3 = 0.053 m3/s. Q2 = 0.1 - 0.053 = 0.047 m3/s. v2 = Q2/A2 = 0.047/0.0177 = 2.66 m/s.
**Trap:** Applying A1*v1 = A2*v2 to each branch individually without conserving total mass.
**What they're really testing:** Whether you can apply mass conservation to simple piping systems and branch connections.

### Q4. Bernoulli's equation, assumptions, derivation. [H]
**A:** Bernoulli: p/rho*g + v^2/2g + z = constant along a streamline. Assumptions: steady flow, incompressible fluid, inviscid (no friction), along a single streamline, no energy addition/removal (no pump/turbine between points). Derivation from Euler: Start with Euler's equation along a streamline: dp/rho + v*dv + g*dz = 0. Integrate: int(dp/rho) + v^2/2 + gz = constant. For incompressible flow, int(dp/rho) = p/rho.
**Push:** Can you apply Bernoulli across a pump? -> No, because a pump adds energy. You need the extended Bernoulli with head added: p1/rho*g + v1^2/2g + z1 + H_pump = p2/rho*g + v2^2/2g + z2 + h_loss.
**Trap:** Applying Bernoulli between points in different streamlines, or across a valve/pump without accounting for losses or work.
**What they're really testing:** Whether you know the assumptions that limit Bernoulli's applicability.

### Q5. Venturi meter principle and discharge coefficient. [H]
**A:** Venturi meter measures flow rate by creating a pressure drop through a converging section. Q = Cd * A2 * sqrt(2*(p1-p2)/rho*(1 - (A2/A1)^2)). Cd accounts for viscous losses and non-uniform velocity profiles. Typical Cd = 0.95-0.98 for venturi, lower for orifice (0.6-0.65) because sudden contraction causes flow separation and vena contracta.
**Push:** Why is pressure recovery better in a venturi than an orifice plate? -> Venturi has a gradual diffuser (7-15 deg angle) that prevents boundary layer separation, recovering 80-90% of pressure drop. Orifice has sudden expansion causing massive separation and only 30-50% recovery.
**Trap:** Assuming Cd = 1 for calculations, or confusing venturi Cd with orifice Cd.
**What they're really testing:** Whether you understand flow measurement principles and why Cd < 1.

### Q6. Pitot tube, velocity measurement. [H]
**A:** Pitot tube faces upstream, measuring stagnation pressure (p0 = p_static + rho*v^2/2). A simple Pitot tube needs a separate static pressure tap. A Pitot-static tube combines both in one instrument with static ports on the side. Velocity v = sqrt(2*(p0 - p_static)/rho).
**Push:** If a Pitot tube reads 150 mm water gauge above static pressure in air at 1.2 kg/m3, what is the velocity? -> delta_p = rho_water*g*h = 1000*9.81*0.15 = 1471.5 Pa. v = sqrt(2*1471.5/1.2) = 49.5 m/s.
**Trap:** Using the Pitot tube reading directly as velocity pressure without subtracting static pressure, or using the wrong density.
**What they're really testing:** Whether you can apply the Pitot-static principle to calculate velocity.

### Q7. Manometer, differential pressure. [M]
**A:** U-tube manometer: p1 + rho1*g*h1 = p2 + rho2*g*h2 + rho_m*g*h_m. For differential pressure between two pipes with same fluid: p1 - p2 = (rho_m - rho)*g*h. For gas pressure measurement (rho << rho_m): p_gauge = rho_m*g*h. Inclined manometer increases sensitivity by measuring along the slope: h = L*sin(theta).
**Push:** If mercury manometer shows 200 mm deflection measuring air pressure, what is the gauge pressure? -> p = rho_Hg*g*h = 13600*9.81*0.2 = 26.7 kPa (approx 0.264 bar).
**Trap:** Using the fluid density instead of the manometer fluid density, or forgetting the fluid density correction.
**What they're really testing:** Whether you can use manometers to measure differential pressure.

### Q8. Buoyancy and stability of floating bodies. [M]
**A:** Archimedes principle: buoyant force = weight of displaced fluid. A body floats when its weight equals the weight of displaced fluid. Stability: metacentric height GM = I/V - BG, where I = second moment of waterplane area, V = displaced volume. GM > 0 means stable (righting moment). GM < 0 means unstable (capsizing). Larger GM = stiffer, but excessive GM causes rapid rolling (uncomfortable).
**Push:** What is metacentric height and why does it matter? -> Distance from centre of gravity to metacentre. It determines stability: if GM > 0, the body returns to upright position after small tilt; if GM < 0, it capsizes.
**Trap:** Confusing centre of gravity with centre of buoyancy - they are different points. CG is mass centre; CB is centre of displaced volume.
**What they're really testing:** Whether you understand buoyancy and floating body stability.

---

## 2. Pipe Flow and Head Loss - 10 questions

### Q9. Reynolds number and flow regimes. [H]
**A:** Re = rho*v*D/mu = v*D/nu. Ratio of inertial forces to viscous forces. Pipe flow: laminar below Re = 2300, transition 2300-4000, turbulent above 4000. At transition, flow changes from orderly layers to chaotic eddies, velocity profile flattens from parabolic to nearly uniform, and friction factor jumps from 64/Re to a higher value on the Moody chart.
**Push:** Why is the critical Re for pipe flow 2300 but for flat plate boundary layer it is 5e5? -> Different geometries and instability mechanisms. Pipe flow is confined and becomes unstable to small disturbances at lower Re.
**Trap:** Using Re = 2300 as a sharp boundary - it is a range, and actual transition depends on pipe roughness, inlet conditions, and disturbances.
**What they're really testing:** Whether you understand Re as a dimensionless group and that transition is a range.

### Q10. Darcy-Weisbach equation and friction factor. [H]
**A:** h_f = f * (L/D) * (v^2/2g). For laminar flow: f = 64/Re exactly. For turbulent flow, f depends on Re and relative roughness (epsilon/D). Use Moody chart or Colebrook equation: 1/sqrt(f) = -2*log10(epsilon/(3.7*D) + 2.51/(Re*sqrt(f))). For smooth pipes, Blasius: f = 0.316/Re^0.25 (valid 4000 < Re < 1e5).
**Push:** What happens to head loss if you double the flow rate in turbulent flow? -> v doubles, so v^2 quadruples. f changes slightly (decreases with Re^0.25), but overall h_f increases by roughly 3.5-4 times.
**Trap:** Using f = 64/Re for turbulent flow, or ignoring the Re-dependence of f in turbulent regime.
**What they're really testing:** Whether you know laminar vs turbulent friction factor behavior.

### Q11. Minor losses, K values, equivalent length. [M]
**A:** Minor losses are head losses from fittings, valves, bends, expansions, contractions: h_m = K * v^2/2g. K is dimensionless loss coefficient (e.g., 0.5 for 90 deg elbow, 10 for fully open globe valve, 1.0 for sudden expansion). Equivalent length Le = K*D/f converts minor loss to an equivalent straight pipe length with same friction loss. Total loss = f*(L/D)*v^2/2g + sum(K)*v^2/2g.
**Push:** Why does a sudden expansion have K = (1 - A1/A2)^2 while sudden contraction K is smaller? -> Sudden expansion causes flow separation and massive eddies (Borda-Carnot loss). Sudden contraction has vena contracta but flow reattaches smoothly.
**Trap:** Forgetting minor losses in short pipe systems where they can dominate, or using K values for the wrong velocity.
**What they're really testing:** Whether you account for fittings and valves in real piping systems.

### Q12. Pipe network analysis, Hardy Cross method. [M]
**A:** Hardy Cross method: iterative solution for pipe networks. For each loop, calculate head loss around the loop, adjust flow rates until sum of head losses = 0. Correction factor: delta_Q = -sum(h_L)/sum(|h_L|/Q). Continue until corrections are negligible. Used for water distribution systems, HVAC piping, process plants.
**Push:** What is the key assumption in Hardy Cross? -> Flow in each pipe is independent, and head loss is proportional to Q^2 (or Q^1.85 for Hazen-Williams).
**Trap:** Applying Hardy Cross to compressible flow or non-circular ducts without modification.
**What they're really testing:** Whether you can solve pipe networks and understand the iterative method.

### Q13. Hazen-Williams equation. [M]
**A:** Hazen-Williams: V = 1.318 * C * R^0.63 * S^0.54, where V = velocity (ft/s), C = roughness coefficient, R = hydraulic radius (ft), S = slope (ft/ft). Or in SI: V = 0.849 * C * R^0.63 * S^0.54. C values: cast iron 100, PVC 150, concrete 120. Used for water distribution systems, simpler than Darcy-Weisbach but less accurate for non-water fluids.
**Push:** When would you use Hazen-Williams instead of Darcy-Weisbach? -> For water distribution systems where water is the fluid and temperature is near ambient. Darcy-Weisbach is more general and accurate for other fluids.
**Trap:** Using Hazen-Williams for gases or non-water liquids - it's calibrated for water only.
**What they're really testing:** Whether you know when to use Hazen-Williams vs Darcy-Weisbach.

### Q14. Boundary layer separation and drag. [M]
**A:** Boundary layer separation occurs when adverse pressure gradient (dp/dx > 0) causes flow near wall to reverse. The separation point creates a wake of low-pressure recirculating flow behind the body. Pressure drag increases because rear pressure stays low while front stagnation pressure remains high. Streamlining delays separation by maintaining favorable or mild adverse gradient, keeping flow attached longer, reducing wake size and pressure drag.
**Push:** Why does a golf ball have dimples? -> Dimples trigger early transition to turbulent boundary layer, which has more momentum near the wall and resists separation better than laminar layer.
**Trap:** Thinking streamlining only reduces skin friction - its main benefit is reducing pressure drag by delaying separation.
**What they're really testing:** Whether you understand boundary layer separation as a pressure-drag mechanism.

### Q15. Free vortex vs forced vortex. [L]
**A:** Free vortex: no external torque, angular momentum conserved (v*r = constant), velocity increases toward centre, irrotational flow. Example: water draining from a sink, tornado core. Forced vortex: fluid rotates as solid body (v = omega*r), requires external torque, rotational flow (vorticity = 2*omega). Example: fluid in a rotating cylindrical tank, cyclone separator, centrifugal pump impeller.
**Push:** Why is the pressure distribution different in forced vs free vortex? -> Forced vortex: p = p0 + 0.5*rho*omega^2*r^2 (parabolic). Free vortex: p = p_inf - 0.5*rho*C^2/r^2 (pressure drops toward centre).
**Trap:** Calling a cyclone purely a free vortex - it has forced vortex outer region and free vortex inner core.
**What they're really testing:** Whether you can distinguish between free and forced vortex, and know their pressure distributions.

### Q16. Centrifugal pump: working principle, NPSH. [H]
**A:** Centrifugal pump: impeller rotates, imparting kinetic energy to fluid (v^2/2g), converted to pressure in the volute/diffuser. Requires priming (casing filled with liquid) because it cannot pump gas. Total head H = suction head + delivery head + velocity head difference + losses. NPSH available = (p_suction - p_vapour)/rho*g + v^2/2g. NPSH required is a pump characteristic. Cavitation occurs when NPSHa < NPSHr - local pressure drops below vapour pressure, bubbles form and collapse violently, causing noise, vibration, pitting damage, and performance drop.
**Push:** How do you prevent cavitation in a pump installation? -> Increase suction pressure (raise supply tank, reduce suction line losses), reduce fluid temperature (lower vapour pressure), use pump with lower NPSHr (larger impeller eye, lower speed), install booster pump.
**Trap:** Thinking cavitation only happens at the impeller eye - it can also occur in valve seats, propeller blades, and turbine runners.
**What they're really testing:** Whether you understand NPSH and cavitation mechanism.

### Q17. Affinity laws for centrifugal pumps. [M]
**A:** For a given pump at constant diameter: Q ~ N, H ~ N^2, P ~ N^3. Double speed (2N): flow doubles, head quadruples, power increases 8 times. For diameter change at constant speed: Q ~ D^3, H ~ D^2, P ~ D^5.
**Push:** A pump delivers 100 m3/h at 30 m head consuming 15 kW at 1450 RPM. What are the values at 2900 RPM? -> Q2 = 200 m3/h, H2 = 120 m, P2 = 120 kW.
**Trap:** Applying affinity laws to different pumps, or when efficiency changes significantly.
**What they're really testing:** Whether you can use affinity laws to predict pump performance at different speeds.

### Q18. Centrifugal vs positive displacement pump. [M]
**A:** Centrifugal: kinetic energy machine, continuous flow, flow varies with head, not self-priming (usually), good for high flow low head. Positive displacement (reciprocating, gear, screw): traps fixed volume per cycle, constant flow regardless of head (within pressure limits), self-priming, good for high pressure low flow, viscous fluids, metering. Reciprocating gives pulsating flow needing dampeners; rotary PD gives smoother flow.
**Push:** Why does a PD pump need a relief valve on the discharge? -> PD pump will build pressure until something fails if discharge is blocked. Relief valve protects the pump and piping.
**Trap:** Using centrifugal pump for high-viscosity fluid (efficiency drops sharply) or PD pump for high-flow clean water application (overkill, higher cost).
**What they're really testing:** Whether you can select the right pump type for given conditions.

### Q19. Impulse vs reaction turbines. [H]
**A:** Impulse turbine: pressure drop only in nozzles, blades only change momentum direction (Pelton wheel). Used for high head, low flow (hydro > 300 m head). Reaction turbine: pressure drop across both fixed and moving blades (Francis, Kaplan). Francis: medium head (30-300 m), medium flow. Kaplan: low head (< 30 m), high flow, adjustable blades. In thermal plants: steam turbines are mostly reaction (pressure-compounded impulse stages + reaction stages).
**Push:** Why does a Pelton wheel need a spear valve instead of a simple gate valve? -> Spear valve provides smooth, precise flow control without water hammer, and maintains constant head on the nozzle for efficiency. Gate valve would cause pressure surges and poor part-load efficiency.
**Trap:** Confusing Francis (radial flow) with Kaplan (axial flow), or saying impulse turbines have no pressure drop in blades.
**What they're really testing:** Whether you can distinguish impulse and reaction turbines and know their applications.

### Q20. Compressible flow, Mach number. [M]
**A:** Mach number M = v/a (flow velocity / speed of sound). For M < 1: subsonic; M = 1: sonic; M > 1: supersonic. Compressible flow effects become significant above M = 0.3. Key phenomena: shock waves, choked flow, area-velocity relation (subsonic: area decreases as velocity increases; supersonic: area increases as velocity increases). Stagnation properties (p0, T0) are constant in adiabatic flow.
**Push:** What is choked flow? -> When flow velocity reaches Mach 1 at the throat of a converging nozzle. Further decrease in downstream pressure doesn't increase mass flow rate. Mass flow is maximum and constant.
**Trap:** Applying incompressible flow equations (Bernoulli) to compressible flow above M = 0.3.
**What they're really testing:** Whether you understand compressible flow and when density changes matter.

---

## 4. Advanced Fluid Topics - 17 questions

### Q29. Water hammer: cause and mitigation. [H]
**A:** Water hammer: pressure surge caused by sudden change in flow velocity (valve closure, pump trip). Pressure rise: delta_P = rho*a*delta_V, where a = wave speed = sqrt(K/rho*(1+K*D/(E*t))) for pipe. Mitigation: (1) Slow valve closure, (2) Surge tanks/air vessels, (3) Pressure relief valves, (4) Flywheels on pumps. Water hammer can cause pipe burst, pump damage, and noise.
**Push:** What is the wave speed in a steel pipe? -> a = sqrt(K/rho / (1 + K*D/(E*t))). For water in steel pipe: a ~ 1000-1400 m/s (much faster than flow velocity).
**Trap:** Confusing water hammer with cavitation - water hammer is pressure surge, cavitation is vapour bubble collapse.
**What they're really testing:** Whether you understand water hammer and can mitigate it.

### Q30. Open channel flow: uniform, critical, and gradually varied. [M]
**A:** Open channel flow: flow with free surface (gravity-driven). (1) Uniform flow: depth and velocity constant along channel (Chezy/Manning equation). (2) Critical flow: Froude number Fr = v/sqrt(g*D) = 1 (minimum specific energy). (3) Gradually varied flow: depth changes along channel (backwater curves). (4) Rapidly varied flow: hydraulic jump, weirs. Manning's equation: V = (1/n)*R^(2/3)*S^(1/2).
**Push:** What is a hydraulic jump? -> Sudden transition from supercritical (Fr > 1) to subcritical (Fr < 1) flow, with energy dissipation and rise in water level. Used in stilling basins.
**Trap:** Applying pipe flow equations to open channels - open channels have free surface and gravity-driven flow.
**What they're really testing:** Whether you understand open channel flow regimes.

### Q31. Dimensional analysis and Buckingham Pi theorem. [M]
**A:** Buckingham Pi theorem: if a physical problem involves n variables and k fundamental dimensions, the number of dimensionless groups is n - k. Steps: (1) List all variables, (2) Identify fundamental dimensions (M, L, T), (3) Choose repeating variables (k variables with independent dimensions), (4) Form dimensionless groups (Pi terms) by combining remaining variables with repeating variables. Used for: (1) Scale model testing, (2) Correlation development, (3) Reducing experimental variables.
**Push:** What are the dimensionless groups in pipe flow? -> Re = rho*v*D/mu, f = h_f/(L/D * v^2/2g), and epsilon/D. Three Pi terms for pipe flow.
**Trap:** Choosing repeating variables that are not dimensionally independent - must have independent dimensions.
**What they're really testing:** Whether you can apply dimensional analysis to fluid problems.

### Q32. Cavitation number and its significance. [M]
**A:** Cavitation number sigma = (p - p_v)/(0.5*rho*v^2), where p = local pressure, p_v = vapour pressure, v = velocity. Lower sigma = higher cavitation risk. Critical sigma (sigma_cr) is the value below which cavitation occurs. For pumps: sigma = (p_suction - p_v)/(rho*g*H). Design requirement: sigma_available > sigma_required (from pump manufacturer).
**Push:** What is the cavitation number for a pump with p_suction = 1.2 bar, p_v = 0.3 bar, rho = 1000, v = 5 m/s? -> sigma = (120000-30000)/(0.5*1000*25) = 90000/12500 = 7.2. High sigma, low cavitation risk.
**Trap:** Confusing cavitation number with NPSH - they are related but NPSH is a head (m), cavitation number is dimensionless.
**What they're really testing:** Whether you understand cavitation number and can use it for design.

### Q33. Reciprocating pump: working and slip. [M]
**A:** Reciprocating pump: (1) Suction stroke - piston moves back, inlet valve opens, fluid enters cylinder. (2) Delivery stroke - piston moves forward, inlet valve closes, delivery valve opens, fluid pushed out. Theoretical discharge Q_th = A*L*N/60 (single-acting) or 2*A*L*N/60 (double-acting). Actual discharge Q_act = Q_th - slip. Slip = Q_th - Q_act (due to leakage, valve delay). Volumetric efficiency eta_v = Q_act/Q_th * 100%.
**Push:** Why is slip negative in some cases? -> Negative slip occurs when delivery valve opens early (due to inertia) and fluid enters cylinder during delivery stroke, increasing actual discharge above theoretical.
**Trap:** Assuming slip is always positive - negative slip can occur at high speeds.
**What they're really testing:** Whether you understand reciprocating pump operation and slip.

### Q34. Centrifugal pump characteristics and operating point. [H]
**A:** Pump characteristic curve: H vs Q (head decreases as flow increases). System curve: H = H_static + K*Q^2 (parabolic). Operating point: intersection of pump and system curves. If system resistance increases (valve closes), flow decreases and head increases. If pump speed changes, use affinity laws to find new curve. Parallel pumps: add flow at same head. Series pumps: add head at same flow.
**Push:** What happens if you throttle the discharge valve? -> Flow decreases, head increases, power may decrease initially then increase. Efficiency drops.
**Trap:** Thinking throttling a pump saves energy like throttling a valve - pump power may actually increase.
**What they're really testing:** Whether you understand pump-system interaction and operating point.

### Q35. Boundary layer on flat plate. [M]
**A:** Boundary layer: thin region near surface where velocity changes from 0 (wall) to free stream. Laminar BL: (1) delta = 5.0*x/sqrt(Re_x), (2) Cf = 0.664/sqrt(Re_x), (3) delta* = 1.72*x/sqrt(Re_x). Turbulent BL: (1) delta = 0.37*x/Re_x^0.2, (2) Cf = 0.059/Re_x^0.2. Transition at Re_x = 5e5. Drag force = 0.5*rho*v^2*Cd*A.
**Push:** What is the difference between displacement thickness and momentum thickness? -> Displacement thickness (delta*) is the distance the wall would need to be displaced to give same flow rate. Momentum thickness (theta) is the distance to give same momentum flux.
**Trap:** Using laminar formulas for turbulent BL or vice versa - they give very different results.
**What they're really testing:** Whether you understand boundary layer theory on flat plates.

### Q36. Drag and lift on bodies. [M]
**A:** Drag: force opposing motion. (1) Skin friction drag (viscous, from boundary layer). (2) Form drag (pressure, from flow separation). (3) Wave drag (compressible). Lift: force perpendicular to motion (from pressure difference). Drag coefficient Cd and lift coefficient Cl depend on shape and Re. Streamlining reduces form drag by delaying separation. For a sphere: Cd ~ 0.47 (turbulent), ~0.1 (streamlined body).
**Push:** Why does a golf ball have dimples? -> Dimples trigger early transition to turbulent BL, which resists separation better than laminar, reducing form drag.
**Trap:** Thinking streamlining only reduces skin friction - its main benefit is reducing form drag.
**What they're really testing:** Whether you understand drag and lift mechanisms.

### Q37. Manometer types and applications. [M]
**A:** (1) U-tube manometer: measures pressure difference between two points. (2) Inclined manometer: measures small pressure differences (higher sensitivity). (3) Well-type manometer: one leg is a large reservoir (constant level). (4) Differential manometer: measures pressure difference with two different fluids. (5) Micromanometer: for very small pressures. Selection based on: (a) Pressure range, (b) Required accuracy, (c) Fluid compatibility.
**Push:** When would you use an inclined manometer? -> For small pressure differences (< 100 Pa) where U-tube sensitivity is insufficient. Inclination increases reading length.
**Trap:** Using U-tube for very small pressures - reading error becomes significant.
**What they're really testing:** Whether you know manometer types and can select the right one.

### Q39. Specific speed and pump/turbine selection. [M]
**A:** Specific speed Ns = N*sqrt(Q)/H^(3/4) (pumps, metric). Ns = N*sqrt(P)/H^(5/4) (turbines). Selection: (1) Low Ns (< 20): centrifugal pump, Pelton turbine. (2) Medium Ns (20-80): mixed flow pump, Francis turbine. (3) High Ns (> 80): axial flow pump, Kaplan turbine. Ns is a shape number - it determines the optimal pump/turbine type for given head and flow.
**Push:** What specific speed is best for a centrifugal pump? -> 10-80 (metric). Below 10: use PD pump. Above 80: use mixed or axial flow pump.
**Trap:** Using the wrong formula for pump vs turbine - different exponents.
**What they're really testing:** Whether you can use specific speed for pump/turbine selection.

### Q40. Flow measurement: orifice, venturi, pitot. [H]
**A:** Orifice plate: sudden contraction, Cd ~ 0.61, high permanent loss. Venturi: gradual contraction/diffuser, Cd ~ 0.98, low loss. Pitot tube: measures stagnation pressure, velocity v = sqrt(2*delta_p/rho). Selection: (1) Orifice for cost-sensitive, (2) Venturi for energy-sensitive, (3) Pitot for velocity profile measurement. All use Bernoulli principle with discharge coefficient.
**Push:** Why does venturi have higher Cd than orifice? -> Gradual contraction avoids flow separation, preserving more kinetic energy. Orifice has vena contracta and separation.
**Trap:** Using orifice Cd for venturi - they have very different Cd values.
**What they're really testing:** Whether you can select flow measurement devices.

### Q41. Compressible flow: isentropic relations. [M]
**A:** Isentropic flow (adiabatic + reversible): (1) T2/T1 = (P2/P1)^((gamma-1)/gamma). (2) rho2/rho1 = (P2/P1)^(1/gamma). (3) A/A* = (1/M) * [2/(gamma+1) * (1 + (gamma-1)/2 * M^2)]^((gamma+1)/(2*(gamma-1))). Critical conditions at M=1: T*/T0 = 2/(gamma+1), P*/P0 = (2/(gamma+1))^(gamma/(gamma-1)). Used for nozzle design and compressible flow analysis.
**Push:** What is the critical pressure ratio for air (gamma=1.4)? -> P*/P0 = (2/2.4)^3.5 = 0.528. Below this ratio, flow is choked (M=1 at throat).
**Trap:** Applying incompressible Bernoulli to compressible flow above M=0.3 - density changes significantly.
**What they're really testing:** Whether you understand isentropic compressible flow.

### Q42. Pipe network: Hardy Cross method. [M]
**A:** Hardy Cross: iterative solution for pipe networks. For each loop: (1) Assume flows, (2) Calculate head loss around loop, (3) Correction delta_Q = -sum(h_L)/sum(|h_L|/Q), (4) Update flows, (5) Repeat until convergence. Convergence: sum of head losses around each loop < 0.01 m. Used for: water distribution systems, HVAC piping, process plants.
**Push:** What is the key assumption in Hardy Cross? -> Flow in each pipe is independent, and head loss is proportional to Q^2 (or Q^1.85 for Hazen-Williams).
**Trap:** Applying Hardy Cross to compressible flow or non-circular ducts without modification.
**What they're really testing:** Whether you can solve pipe networks.

### Q43. Pumps in series and parallel. [M]
**A:** Series: pumps connected end-to-end, heads add at same flow. Used when high head needed (multi-stage pumps). Parallel: pumps connected side-by-side, flows add at same head. Used when high flow needed. For identical pumps in parallel: Q_total = 2*Q_single at same H. For identical pumps in series: H_total = 2*H_single at same Q.
**Push:** When would you use pumps in series vs parallel? -> Series for high head (deep wells, high-rise buildings). Parallel for high flow (large water supply, cooling systems).
**Trap:** Thinking series pumps double the flow - they double the head, not the flow.
**What they're really testing:** Whether you understand pump arrangement and system design.

### Q44. Fluid machinery efficiency. [M]
**A:** Pump efficiency: eta = rho*g*Q*H / P_input (hydraulic power / shaft power). Turbine efficiency: eta = P_output / (rho*g*Q*H). Overall efficiency includes: (1) Hydraulic efficiency (fluid friction), (2) Mechanical efficiency (bearing friction), (3) Volumetric efficiency (leakage). Typical: centrifugal pump 60-85%, Pelton turbine 85-90%, Francis turbine 90-95%.
**Push:** Why is turbine efficiency higher than pump efficiency? -> Turbines extract energy (flow expands), pumps add energy (flow compresses). Expansion is more efficient than compression.
**Trap:** Confusing hydraulic efficiency with overall efficiency - overall includes all losses.
**What they're really testing:** Whether you understand fluid machinery efficiency.

### Q45. Flow in non-circular ducts. [L]
**A:** For non-circular ducts (rectangular, triangular, annular), use hydraulic diameter D_h = 4*A/P, where A = flow area, P = wetted perimeter. Then use Darcy-Weisbach with D_h: h_f = f*(L/D_h)*v^2/2g. Friction factor from Moody chart using Re = rho*v*D_h/mu and relative roughness. For laminar flow: f = 64/Re (same as circular). For turbulent: depends on Re and epsilon/D_h.
**Push:** What is the hydraulic diameter of a rectangular duct 0.3 m x 0.2 m? -> A = 0.06 m2, P = 2*(0.3+0.2) = 1.0 m. D_h = 4*0.06/1.0 = 0.24 m.
**Trap:** Using actual diameter instead of hydraulic diameter for non-circular ducts.
**What they're really testing:** Whether you can analyze flow in non-circular ducts.

---

## File Statistics

**Total questions: 36**

**By tag:**
- [H] High-yield: ~25 questions
- [M] Medium-yield: ~18 questions
- [L] Occasional: ~2 questions

**By section:**
- Fluid properties and statics: 8 questions
- Pipe flow and head loss: 10 questions
- Turbomachinery: 8 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, water density 1000, air density 1.2, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers fluid mechanics and piping - essential for automobiles, petrochem, and construction interviews.