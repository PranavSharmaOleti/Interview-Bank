# Thermodynamics and IC Engines - L&T GET technical interview bank

**Part 2 of 8 | 28 questions | Laws, cycles, steam properties, engine performance**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly, [L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing recall, they are testing whether you can reason out loud.*

## 1. Thermodynamics - 16 questions

### Q1. State the four laws of thermodynamics in one line each and what each is used for. [H]

**A:** Zeroth: if A equals B and B equals C, then A equals C - basis of temperature measurement. First: energy cannot be created or destroyed, delta U = Q - W - energy balance for any system. Second: entropy of an isolated system never decreases, heat flows from hot to cold - sets direction and limits efficiency. Third: entropy approaches a constant (zero for perfect crystal) as temperature approaches absolute zero - reference for absolute entropy values.

**Push:** Why is the second law stated in terms of entropy? **A:** Because entropy quantifies irreversibility; the Kelvin-Planck and Clausius statements are special cases of the entropy principle.

**Trap:** Saying "energy is conserved" for the second law - that is the first law.

### Q2. What is the difference between heat and work? Why is enthalpy H = U + PV used for flow processes? [H]

**A:** Heat is energy transfer due to temperature difference; work is energy transfer due to force through distance - both are path functions, not properties. Enthalpy combines internal energy U with flow work PV; for steady flow the energy equation reduces to delta H = Q - W_s, so enthalpy directly accounts for the energy carried by the flowing fluid across boundaries.

**Push:** When would you use internal energy instead of enthalpy? **A:** Closed systems (no mass flow) where boundary work PdV is explicit.

**Trap:** Calling heat or work a property of the system.

### Q3. Define entropy. State the second law in entropy form and explain why entropy increases in real processes. [H]

**A:** Entropy is a measure of molecular disorder or energy dispersal, defined as dS = dQ_rev/T. Second law: for any process in an isolated system, delta S >= 0. Entropy increases because irreversibilities (friction, unrestrained expansion, heat transfer across finite temperature difference) generate entropy - the inequality T*dS >= dQ shows actual heat transfer is always less than reversible equivalent for same entropy change.

**Push:** What is entropy generation in a throttling process? **A:** Throttling is isenthalpic but irreversible; entropy increases as pressure drops with no work output.

**Trap:** Saying entropy increases because "disorder increases" without linking to irreversibility.

### Q4. What is Carnot efficiency? State Carnot theorem and explain why no real cycle beats it. [H]

**A:** Carnot efficiency eta_C = 1 - T_L/T_H (absolute temperatures). Carnot theorem: no engine operating between two reservoirs can exceed Carnot efficiency. Real cycles have irreversibilities - heat transfer across finite delta T, friction, non-isentropic compression/expansion - so their efficiency is always lower. Carnot is the reversible limit.

**Push:** If a power plant claims 50% efficiency with T_H = 800 K and T_L = 300 K, is it possible? **A:** Carnot limit is 1 - 300/800 = 62.5%, so 50% is theoretically possible but very high for a real plant.

**Trap:** Using Celsius temperatures in the Carnot formula.

### Q5. Distinguish between heat engine, heat pump, refrigerator, and chiller. Give the COP relations. [H]

**A:** Heat engine: converts heat to work, eta = W_net/Q_H. Heat pump: moves heat from cold to hot for heating, COP_HP = Q_H/W = 1/(1 - T_L/T_H). Refrigerator: moves heat from cold space for cooling, COP_R = Q_L/W = T_L/(T_H - T_L). Chiller: large-scale refrigeration for process/AC, same COP as refrigerator. COP_HP = COP_R + 1.

**Push:** Why is COP_HP always greater than 1? **A:** Because Q_H = Q_L + W, so COP_HP = (Q_L + W)/W = COP_R + 1 > 1.

**Trap:** Confusing COP of heat pump with efficiency of heat engine.

### Q6. Sketch the Rankine cycle on a T-s diagram. Name the four processes and list the five ways to improve cycle efficiency with effect and cost of each. [H]

**A:** T-s diagram: 1-2 constant pressure heat addition in boiler (horizontal right), 2-3 isentropic expansion in turbine (vertical down), 3-4 constant pressure condensation (horizontal left), 4-1 isentropic pumping (vertical up). Five improvements: (1) Superheat - raises average heat addition temperature, increases efficiency, needs better materials for higher temperature. (2) Reheat - reduces moisture at turbine exit, improves efficiency, adds reheater cost and pressure drop. (3) Regenerative feedwater heating - uses turbine bleed steam to preheat feedwater, raises average heat addition temperature, needs extra heaters and piping. (4) Lower condenser pressure - increases expansion ratio and work output, needs larger condenser and vacuum pumps. (5) Raise boiler pressure - raises saturation temperature, improves efficiency, needs thicker pressure parts and better materials.

**Push:** Which improvement gives the most gain per rupee in a typical plant? **A:** Regenerative feedwater heating usually gives best cost-benefit; superheat and reheat are standard in modern plants.

**Trap:** Forgetting that lowering condenser pressure increases turbine last-stage blade erosion risk from wetness.

### Q7. Write the ideal gas law and the general gas law PV^m = constant. What is m for isothermal, adiabatic air, and adiabatic steam? [H]

**A:** Ideal gas: PV = mRT where R = R_univ/M. General polytropic: PV^n = constant. Isothermal: n = 1 (PV = constant). Adiabatic air: n = gamma = Cp/Cv = 1.4. Adiabatic steam: n = 1.33 (approximate for superheated steam).

**Push:** What is the work done in an isothermal compression of ideal gas? **A:** W = mRT ln(V1/V2) = mRT ln(P2/P1).

**Trap:** Using n = 1.4 for steam adiabatic - it is 1.33.

### Q8. What are steam tables and the Mollier chart? When do you use each? [H]

**A:** Steam tables: tabulated thermodynamic properties (h, s, v, u) at discrete pressures and temperatures - use for precise interpolation in calculations. Mollier chart: h-s diagram with constant pressure, temperature, quality lines - use for quick visual estimation of cycle states, turbine expansion paths, and quality at exhaust. Both cover saturated and superheated regions.

**Push:** How do you find enthalpy at a state between tabulated values? **A:** Linear interpolation in steam tables; on Mollier chart, read directly from the plotted lines.

**Trap:** Using saturated steam tables for superheated conditions.

### Q9. Define dry steam, wet steam, and quality (dryness fraction). How is quality measured? [H]

**A:** Dry steam: quality x = 1, all vapour. Wet steam: 0 < x < 1, mixture of vapour and liquid. Quality x = mass of vapour / total mass. Measured by throttling calorimeter: throttle wet steam to low pressure where it becomes superheated, measure temperature, use h1 = h2 to find x from h_fg. Also separating calorimeter (measures liquid separated) or combined separating-throttling for very wet steam.

**Push:** Why must throttling be to a pressure where steam is superheated? **A:** To ensure temperature is uniquely defined for the enthalpy - in two-phase region, temperature depends only on pressure, not enthalpy.

**Trap:** Saying quality is measured by temperature alone.

### Q10. What is held constant in isothermal, isobaric, isochoric, and isentropic processes? [H]

**A:** Isothermal: temperature constant (PV = constant for ideal gas). Isobaric: pressure constant (V/T = constant). Isochoric: volume constant (P/T = constant). Isentropic: entropy constant, reversible adiabatic (PV^gamma = constant for ideal gas).

**Push:** In which process is heat transfer zero? **A:** Isentropic (by definition, reversible adiabatic) - also adiabatic but not necessarily isentropic if irreversible.

**Trap:** Confusing isentropic with adiabatic - irreversible adiabatic is not isentropic.

### Q11. Define irreversibility. What is the Carnot factor of a power plant? Why is plant efficiency far below Carnot? [M]

**A:** Irreversibility I = T0 * S_gen = lost work potential due to entropy generation. Carnot factor = (1 - T0/T_source) * (actual work / reversible work) - measures how close the plant approaches Carnot limit. Real plants are far below Carnot because: finite temperature differences in heat exchangers, pressure drops in piping, non-isentropic turbine/pump, mechanical losses, heat losses to surroundings, condenser temperature above ambient.

**Push:** What is the typical Carnot factor for a modern coal plant? **A:** Around 0.5-0.6 (plant efficiency ~40-45% vs Carnot ~65-70%).

**Trap:** Attributing the gap only to turbine inefficiency - boiler and condenser irreversibilities are often larger.

### Q12. Explain boiler and condenser heat balance. Why does the condenser sit at the lowest pressure and temperature? [M]

**A:** Boiler: Q_in = m_steam * (h_out - h_in). Condenser: Q_out = m_steam * (h_turbine_exit - h_condensate) = m_cw * Cp * (T_cw_out - T_cw_in). Condenser operates at lowest pressure (vacuum) because: (1) maximises turbine expansion ratio and work output, (2) saturation temperature at that pressure must be above cooling water temperature to reject heat - typically 30-50 deg C corresponding to 0.04-0.12 bar absolute.

**Push:** What happens if condenser vacuum degrades? **A:** Turbine exhaust pressure rises, enthalpy drop across turbine decreases, power output drops, heat rate worsens.

**Trap:** Thinking condenser pressure is set by pump - it is set by cooling water temperature and condenser size.

### Q13. Distinguish cycle efficiency from Carnot efficiency. What is reversible vs irreversible work? [M]

**A:** Cycle efficiency = W_net/Q_in for the actual cycle. Carnot efficiency = 1 - T_L/T_H for the same temperature limits - the theoretical maximum. Reversible work W_rev = maximum work obtainable between given states (isentropic). Irreversible work W_irrev = actual work < W_rev due to entropy generation. The difference W_rev - W_irrev = T0 * S_gen = irreversibility.

**Push:** For a turbine with isentropic efficiency 85%, what is the relationship? **A:** W_actual = 0.85 * W_isentropic.

**Trap:** Using cycle efficiency formula for Carnot efficiency.

### Q14. What is heat recovery, cogeneration, and combined cycle? Why do they matter in a power project? [M]

**A:** Heat recovery: capturing waste heat (e.g., exhaust gas) for process heating or feedwater preheat. Cogeneration: simultaneous production of electricity and useful heat from one fuel source - overall efficiency 70-85% vs 35-45% for power alone. Combined cycle: gas turbine (Brayton) topping cycle with steam turbine (Rankine) bottoming cycle using gas turbine exhaust - efficiency 55-62%. They matter because L&T builds EPC power projects where fuel cost and emissions regulations drive these configurations.

**Push:** What is the typical steam condition in a combined cycle HRSG? **A:** Dual or triple pressure (high/intermediate/low) with reheat - matches gas turbine exhaust temperature profile.

**Trap:** Calling any waste heat boiler a combined cycle - combined cycle specifically means two thermodynamic cycles in series.

### Q15. List the air standard assumptions. Give the thermal efficiency formulas for Otto and Diesel cycles. [H]

**A:** Air standard assumptions: (1) Working fluid is air (ideal gas), (2) All processes internally reversible, (3) Heat addition replaces combustion, (4) Heat rejection replaces exhaust, (5) Constant specific heats. Otto efficiency: eta = 1 - 1/r^(gamma-1). Diesel efficiency: eta = 1 - (1/gamma) * (rho^gamma - 1)/(r^(gamma-1) * (rho - 1)) where r = compression ratio, rho = cut-off ratio V3/V2. For same r, Otto efficiency > Diesel efficiency; but Diesel runs at higher r so actual efficiency is comparable.

**Push:** Why does Diesel cycle have lower efficiency than Otto for the same compression ratio? **A:** Because heat addition in Diesel is at constant pressure (lower average temperature) vs constant volume in Otto.

**Trap:** Using the Otto formula for Diesel cycle or vice versa.

### Q16. What is the difference between indicated and brake thermal efficiency? How do they relate to mechanical efficiency? [H]

**A:** Indicated thermal efficiency eta_ith = IP / (m_f * CV) - based on indicated power from cylinder pressure. Brake thermal efficiency eta_bth = BP / (m_f * CV) - based on brake power at crankshaft. Mechanical efficiency eta_m = BP / IP = eta_bth / eta_ith. Friction power FP = IP - BP.

**Push:** If eta_ith = 40% and eta_m = 85%, what is eta_bth? **A:** 0.40 * 0.85 = 34%.

**Trap:** Confusing indicated power (cylinder) with brake power (output shaft).

**What they're really testing:** Can you apply thermodynamic laws to real equipment, trace energy flow through a cycle, and quantify losses - the daily work of a power plant or engine engineer.

## 2. IC Engines - 12 questions

### Q17. Compare four-stroke and two-stroke engines: sequence, port arrangement, efficiency, applications. [H]

**A:** Four-stroke: intake, compression, power, exhaust - four strokes, two revolutions, valves in head, higher volumetric efficiency, better scavenging, used in cars, trucks, generators. Two-stroke: compression and power only - intake/exhaust via ports in cylinder wall uncovered by piston, one revolution per cycle, simpler, lighter, higher power-to-weight, but poor scavenging, high HC emissions, lower efficiency - used in chainsaws, outboards, some small generators.

**Push:** Why does two-stroke have lower fuel efficiency? **A:** Fresh charge escapes during scavenging overlap; lubricating oil burns with fuel.

**Trap:** Saying two-stroke has twice the power for same size - it is typically 1.3-1.5x due to poor scavenging.

### Q18. Compare Otto and Diesel cycles: compression ratio, ignition, fuel, efficiency. [H]

**A:** Otto: CR 8:1 to 12:1, spark ignition, petrol/gasoline, constant volume heat addition. Diesel: CR 14:1 to 22:1, compression ignition, diesel fuel, constant pressure heat addition. Diesel has higher thermal efficiency due to higher CR and lean burn; Otto has higher power density. For same CR, Otto efficiency > Diesel; but Diesel operates at higher CR so actual brake thermal efficiency: Diesel ~40-45%, Otto ~30-35%.

**Push:** Why can't you run petrol at Diesel compression ratios? **A:** Petrol has low autoignition temperature - would knock destructively before spark.

**Trap:** Saying Diesel cycle is constant volume - it is constant pressure heat addition.

### Q19. Define air standard efficiency, indicated thermal efficiency, and brake thermal efficiency. [H]

**A:** Air standard efficiency: theoretical cycle efficiency based on air standard assumptions (eta_otto = 1 - 1/r^(gamma-1), eta_diesel formula). Indicated thermal efficiency: IP / (m_f * CV) - efficiency of converting fuel energy to cylinder work. Brake thermal efficiency: BP / (m_f * CV) - efficiency of converting fuel energy to useful shaft work. eta_bth < eta_ith < eta_air_standard due to real losses.

**Push:** Which efficiency does BSFC relate to? **A:** Brake thermal efficiency - BSFC = 3600 / (eta_bth * CV) in g/kWh.

**Trap:** Using air standard efficiency to estimate actual fuel consumption.

### Q20. Explain indicated power, brake power, friction power, and mechanical efficiency. [H]

**A:** Indicated power IP = work from cylinder pressure diagram = P_mep * L * A * N * k / 60 (k = 1 for 2-stroke, 1/2 for 4-stroke). Brake power BP = 2 * pi * N * T / 60 (T = torque). Friction power FP = IP - BP (pumping, rubbing, accessory losses). Mechanical efficiency eta_m = BP / IP = 1 - FP/IP. Typical eta_m = 80-90% at full load, drops at part load.

**Push:** How do you measure FP in the lab? **A:** Motoring test (engine run by motor, measure power input) or Willans line (BP vs fuel rate extrapolation to zero fuel).

**Trap:** Thinking FP is only piston-ring friction - pumping and accessory losses are significant.

### Q21. What is BSFC? Why does it matter and what moves it? [H]

**A:** Brake specific fuel consumption = mass fuel per brake energy (g/kWh). BSFC = m_f / BP. It matters because fuel cost dominates lifecycle cost of engines. What moves it: engine load (best at 75-90% load), speed (minimum at mid-speed), compression ratio, air-fuel ratio (lean burn improves), combustion timing, friction, turbocharging (improves at part load). Typical: petrol 250-300 g/kWh, diesel 200-230 g/kWh at best point.

**Push:** Why does BSFC worsen at low load? **A:** Throttling loss (pumping work) increases, mechanical efficiency drops, combustion less complete.

**Trap:** Quoting BSFC at full load only - real operation is mostly part load.

### Q22. Define volumetric efficiency. What affects it? [H]

**A:** Volumetric efficiency eta_v = actual mass of air inducted / theoretical mass at ambient density. eta_v = m_a / (rho_a * V_d). Affected by: intake manifold pressure (throttle), intake temperature, valve timing/overlap, engine speed (inertia, resonance), exhaust back pressure, compression ratio (clearance volume). Typical max 85-95% at peak torque RPM.

**Push:** How does turbocharging affect volumetric efficiency? **A:** Increases intake manifold pressure above atmospheric, so eta_v > 100% (mass inducted exceeds displacement volume at ambient density).

**Trap:** Confusing volumetric efficiency with breathing capacity - they are related but eta_v is the ratio, breathing is the absolute mass flow.

### Q23. What is knocking? Distinguish detonation from pre-ignition. What is octane number? [H]

**A:** Knocking: uncontrolled autoignition of end-gas after spark, causing pressure spikes and hammering noise. Detonation: end-gas autoignites from pressure/temperature rise after normal spark - multiple flame fronts, rapid pressure rise. Pre-ignition: mixture ignites before spark (hot spot, glowing deposit) - single early flame front, more destructive. Octane number: resistance to knock; RON (research) and MON (motor); higher octane = more knock resistance. Petrol 91-98 RON typical.

**Push:** What raises knocking tendency? **A:** Higher compression ratio, advanced spark, lean mixture, high intake temperature, low octane fuel, high load.

**Trap:** Calling pre-ignition "detonation" - they are different phenomena with different causes and effects.

### Q24. Compare carburettor and fuel injection. What is atomisation and why does spark advance matter? [H]

**A:** Carburettor: venturi suction draws fuel, simple, poor mixture distribution, cannot control precisely, being phased out. Fuel injection: pressurised fuel sprayed into intake port (port injection) or cylinder (direct injection) - precise metering, better atomisation, enables lean burn, catalyst compatibility. Atomisation: breaking fuel into fine droplets for rapid evaporation and mixing - finer = better combustion. Spark advance: firing before TDC so peak pressure occurs ~10-15 deg ATDC for maximum work - too advanced causes knock, too retarded loses power and overheats exhaust.

**Push:** Why does direct injection allow higher compression ratio? **A:** Fuel evaporation cools charge, reducing knock tendency.

**Trap:** Thinking carburettor meters fuel accurately - it relies on pressure difference, not precise control.

### Q25. Describe air-cooled vs water-cooled systems. What is the thermostat's role? [M]

**A:** Air-cooled: fins on cylinder, airflow from fan - simple, light, no coolant, but uneven cooling, noisy, limited to small engines. Water-cooled: water jacket, pump, radiator, fan - uniform cooling, compact engine, heater for cabin, but complexity, leak risk, weight. Thermostat: wax-pellet valve that opens at ~80-90 deg C - blocks flow to radiator when cold (fast warm-up), opens when hot (maintains temperature). Prevents overcooling and thermal shock.

**Push:** Why does overcooling increase wear? **A:** Piston-ring clearance stays large, oil viscosity too high, fuel condensation on walls, incomplete combustion.

**Trap:** Saying thermostat controls temperature - it controls flow path; temperature is controlled by heat balance.

### Q26. Explain wet sump lubrication. Why does oil viscosity matter? [M]

**A:** Wet sump: oil stored in pan at bottom, gear/rotor pump draws through strainer, delivers to main gallery, feeds bearings via drillings, splash lubricates cylinder walls. Viscosity: must be low enough to flow at cold start (0W/5W) but high enough to maintain film at 100+ deg C (30/40). Multi-grade (e.g., 5W-30) uses viscosity index improvers. Too low = bearing wear, oil consumption; too high = cold start starvation, pumping loss.

**Push:** What is the main gallery? **A:** Drilled passage in block that distributes pressurised oil to crankshaft main bearings, then through crankshaft drillings to big-end bearings.

**Trap:** Thinking oil pump creates pressure - it creates flow; pressure comes from resistance of clearances.

### Q27. List major emissions: CO, HC, NOx, particulates. Why does diesel give more NOx and petrol more CO/HC? [M]

**A:** CO: incomplete combustion (rich mixture). HC: unburned fuel (wall quench, crevices, incomplete burn). NOx: high temperature + oxygen + nitrogen (thermal NOx). Particulates: soot from rich zones in diffusion flame. Diesel: lean overall, high compression temperature -> high NOx; diffusion flame with rich cores -> particulates. Petrol: stoichiometric with throttle -> rich at high load (CO), wall quench and crevices at part load (HC), lower peak temperature -> less NOx.

**Push:** How does EGR reduce NOx? **A:** Recirculates exhaust gas (inert) to lower peak combustion temperature.

**Trap:** Saying diesel runs rich - it runs lean overall; particulates come from local rich zones.

### Q28. How does compression ratio affect torque? What are CNG/LNG basics for heavy equipment? [L]

**A:** Higher CR increases thermal efficiency and expands gas further, giving more torque per displacement - but limited by knock (petrol) or mechanical stress (diesel). Diesel CR 14-22:1, petrol 8-12:1. CNG (compressed natural gas, ~200-250 bar): methane, high octane (~120), low energy density (~9 MJ/L vs 32 for diesel), needs spark ignition, ~15-20% power loss vs diesel. LNG (liquefied, -162 deg C): higher energy density (~22 MJ/L), cryogenic tank, same combustion as CNG. Both reduce CO2 ~20%, eliminate particulates, need dedicated engines.

**Push:** Why can't you just put CNG in a diesel engine? **A:** Diesel relies on compression ignition; methane has high autoignition temperature - needs spark plug and lower CR or dual-fuel pilot diesel injection.

**Trap:** Thinking CNG/LNG are drop-in replacements - they need different engines or major modifications.

**What they're really testing:** Can you connect thermodynamic cycle analysis to actual engine hardware decisions - compression ratio, fuel choice, cooling, lubrication, emissions - that determine whether a machine performs and lasts on site.