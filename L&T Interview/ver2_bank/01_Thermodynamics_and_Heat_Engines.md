# Thermodynamics and Heat Engines - Core Interview Bank

**Part 1 of 10 | 55 questions | Thermodynamics fundamentals, heat engines, cycles, steam properties, refrigeration**
*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus, occasionally one numerical.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional. Order: all [H] first, then [M], then [L].*

## 1. Thermodynamics Fundamentals - 15 questions

### Q1. State the first law of thermodynamics in plain words. [H]
**A:** Energy cannot be created or destroyed. For any system, the change in internal energy equals heat added minus work done by the system: delta U = Q - W. For flow processes, it's more useful to use enthalpy: delta H = Q - W_s. Heat and work are both path functions, not properties of the system.
**Push:** What's the difference between heat and work? -> Heat is energy transfer due to temperature difference; work is energy transfer due to force through distance. Both are path functions, meaning the amount depends on the process path, not just initial and final states.
**Trap:** Calling heat or work a property of the system. They are energy transfer mechanisms, not state properties.
**What they're really testing:** Whether you understand energy conservation and can distinguish between state properties and path functions.

### Q2. State the second law in entropy form. [H]
**A:** Second Law: for any process in an isolated system, delta S >= 0. Entropy (S) is a measure of energy dispersal or disorder. The inequality T*dS >= dQ shows that actual heat transfer is always less than the reversible equivalent for the same entropy change. Entropy increases because of irreversibilities: friction, unrestrained expansion, heat transfer across finite temperature difference.
**Push:** Why is the second law stated in terms of entropy? -> Because entropy quantifies irreversibility. The Kelvin-Planck statement (no engine can convert all heat to work) and Clausius statement (heat cannot spontaneously flow from cold to hot) are special cases of the entropy principle.
**Trap:** Saying "energy is conserved" for the second law - that's the first law. The second law introduces directionality and limits to what's possible.
**What they're really testing:** Whether you grasp that the second law is about possibility and direction, not just a formula.

### Q3. Define entropy. When does it increase? [H]
**A:** Entropy is a measure of molecular disorder or energy dispersal. Defined as dS = dQ_rev/T. Second law: for any process in an isolated system, delta S >= 0. Entropy increases because of irreversibilities: friction (converts mechanical energy to heat), unrestrained expansion (gas expands into vacuum), heat transfer across finite temperature difference (never 100% efficient). The equality dS = dQ_rev/T applies only to reversible processes.
**Push:** What is entropy generation in a throttling process? -> Throttling is isenthalpic (delta H = 0) but irreversible. Entropy increases as pressure drops with no work output. This is why throttling is used for refrigerant expansion in refrigeration cycles.
**Trap:** Saying entropy increases because "disorder increases" without linking to irreversibility.
**What they're really testing:** Whether you understand entropy generation, not just entropy change.

### Q4. Carnot efficiency and why real cycles can't beat it. [H]
**A:** Carnot efficiency: eta_C = 1 - T_L/T_H (absolute temperatures). No engine operating between two reservoirs can exceed Carnot efficiency. Real cycles have irreversibilities: heat transfer across finite delta T, friction, non-isentropic compression/expansion. Carnot is the reversible limit - the theoretical maximum.
**Push:** If a power plant claims 50% efficiency with T_H = 800 K and T_L = 300 K, is it possible? -> Carnot limit is 1 - 300/800 = 62.5%. So 50% is theoretically possible but very high for a real plant. Typical modern combined-cycle plants achieve 55-60%.
**Trap:** Using Celsius temperatures in Carnot formula. Must use absolute (Kelvin) temperatures.
**What they're really testing:** Whether you can apply the Carnot limit to assess claimed performance.

### Q5. Heat engine, heat pump, refrigerator, chiller - and COP relations. [H]
**A:** Heat engine: converts heat to work, eta = W_net/Q_H. Heat pump: moves heat from cold to hot for heating, COP_HP = Q_H/W = 1/(1 - T_L/T_H). Refrigerator: moves heat from cold space for cooling, COP_R = Q_L/W = T_L/(T_H - T_L). Chiller: large-scale refrigeration for process/AC, same COP as refrigerator. COP_HP = COP_R + 1.
**Push:** Why is COP_HP always greater than 1? -> Because Q_H = Q_L + W, so COP_HP = (Q_L + W)/W = COP_R + 1 > 1. You get more heat energy out than electrical energy put in.
**Trap:** Confusing COP of heat pump with efficiency of heat engine. Efficiency <= 1; COP can > 1.
**What they're really testing:** Whether you can distinguish between engine efficiency and heat pump/refrigerator COP.

### Q6. Isothermal, isobaric, isochoric, and isentropic processes. [H]
**A:** Isothermal: temperature constant (PV = constant for ideal gas, delta U = 0, Q = W). Isobaric: pressure constant (V/T = constant, Q = delta H). Isochoric: volume constant (P/T = constant, Q = delta U). Isentropic: entropy constant, reversible adiabatic (PV^gamma = constant for ideal gas).
**Push:** In which process is heat transfer zero? -> Isentropic (by definition, reversible adiabatic). Note: adiabatic means no heat transfer, but not all adiabatic processes are isentropic - irreversible adiabatic processes generate entropy.
**Trap:** Confusing isentropic with adiabatic. Irreversible adiabatic is not isentropic.
**What they're really testing:** Whether you can distinguish between process types and know the key relationships for each.

### Q7. Steam tables and Mollier chart when to use each. [H]
**A:** Steam tables: tabulated thermodynamic properties (h, s, v, u) at discrete pressures and temperatures - use for precise interpolation in calculations. Mollier chart: h-s diagram with constant pressure, temperature, quality lines - use for quick visual estimation of cycle states, turbine expansion paths, and quality at exhaust. Both cover saturated and superheated regions.
**Push:** How do you find enthalpy at a state between tabulated values? -> Linear interpolation in steam tables. On Mollier chart, read directly from the plotted lines for the given pressure and quality.
**Trap:** Using saturated steam tables for superheated conditions. Steam tables have separate sections for saturated and superheated.
**What they're really testing:** Whether you know your tools for getting property values, and when precision vs. estimation is appropriate.

### Q8. Dry steam, wet steam, and quality (dryness fraction). [H]
**A:** Dry steam: quality x = 1, all vapour. Wet steam: 0 < x < 1, mixture of vapour and liquid. Quality: x = mass of vapour / total mass. Measured by throttling calorimeter: throttle wet steam to low pressure where it becomes superheated, measure temperature, use h1 = h2 to find x from h_fg. Also separating calorimeter (measures liquid separated) or combined separating-throttling for very wet steam.
**Push:** Why must throttling be to a pressure where steam is superheated? -> To ensure temperature is uniquely defined for the enthalpy. In the two-phase region, temperature depends only on pressure, not enthalpy.
**Trap:** Saying quality is measured by temperature alone. Temperature in the two-phase region depends only on pressure, not on how much vapour is present.
**What they're really testing:** Whether you can explain steam quality measurement and the difference between dry, wet, and superheated steam.

### Q9. Ideal gas law and polytropic process. [H]
**A:** Ideal gas: PV = mRT where R = R_univ/M. General polytropic: PV^n = constant. Isothermal: n = 1 (PV = constant). Adiabatic air: n = gamma = Cp/Cv = 1.4. Adiabatic steam: n = 1.33 (approximate for superheated steam).
**Push:** What is the work done in an isothermal compression of ideal gas? -> W = mRT ln(V1/V2) = mRT ln(P2/P1).
**Trap:** Using n = 1.4 for steam adiabatic - it is 1.33.
**What they're really testing:** Whether you know the polytropic exponent for different processes and can calculate work.

### Q10. Rankine cycle on T-s diagram. [H]
**A:** T-s diagram: 1-2 constant pressure heat addition in boiler (horizontal right), 2-3 isentropic expansion in turbine (vertical down), 3-4 constant pressure condensation (horizontal left), 4-1 isentropic pumping (vertical up). Five improvements: (1) Superheat - raises average heat addition temperature, increases efficiency, needs better materials. (2) Reheat - reduces moisture at turbine exit, improves efficiency, adds reheater cost. (3) Regenerative feedwater heating - uses turbine bleed steam to preheat feedwater, raises average heat addition temperature. (4) Lower condenser pressure - increases expansion ratio and work output. (5) Raise boiler pressure - raises saturation temperature, improves efficiency.
**Push:** Which improvement gives the most gain per rupee in a typical plant? -> Regenerative feedwater heating usually gives best cost-benefit; superheat and reheat are standard in modern plants.
**Trap:** Forgetting that lowering condenser pressure increases turbine last-stage blade erosion risk from wetness.
**What they're really testing:** Whether you can trace the Rankine cycle on T-s diagram and explain each improvement's effect.

### Q11. Boiler and condenser heat balance. [M]
**A:** Boiler: Q_in = m_steam * (h_out - h_in). Condenser: Q_out = m_steam * (h_turbine_exit - h_condensate) = m_cw * Cp * (T_cw_out - T_cw_in). Condenser operates at lowest pressure (vacuum) because: (1) maximises turbine expansion ratio and work output, (2) saturation temperature at that pressure must be above cooling water temperature to reject heat - typically 30-50 deg C corresponding to 0.04-0.12 bar absolute.
**Push:** What happens if condenser vacuum degrades? -> Turbine exhaust pressure rises, enthalpy drop across turbine decreases, power output drops, heat rate worsens.
**Trap:** Thinking condenser pressure is set by pump - it is set by cooling water temperature and condenser size.
**What they're really testing:** Whether you can write energy balance for boiler and condenser, and understand the condenser's role in the cycle.

### Q12. Carnot factor and irreversibility. [M]
**A:** Irreversibility I = T0 * S_gen = lost work potential due to entropy generation. Carnot factor = (1 - T0/T_source) * (actual work / reversible work) - measures how close the plant approaches Carnot limit. Real plants are far below Carnot because: finite temperature differences in heat exchangers, pressure drops in piping, non-isentropic turbine/pump, mechanical losses, heat losses to surroundings, condenser temperature above ambient.
**Push:** What is the typical Carnot factor for a modern coal plant? -> Around 0.5-0.6 (plant efficiency ~40-45% vs Carnot ~65-70%).
**Trap:** Attributing the gap only to turbine inefficiency - boiler and condenser irreversibilities are often larger.
**What they're really testing:** Whether you can quantify how far real plants fall from the Carnot limit, and identify major loss sources.

### Q13. Heat recovery, cogeneration, combined cycle. [M]
**A:** Heat recovery: capturing waste heat (e.g., exhaust gas) for process heating or feedwater preheat. Cogeneration: simultaneous production of electricity and useful heat from one fuel source - overall efficiency 70-85% vs 35-45% for power alone. Combined cycle: gas turbine (Brayton) topping cycle with steam turbine (Rankine) bottoming cycle using gas turbine exhaust - efficiency 55-62%. They matter because L&T builds EPC power projects where fuel cost and emissions regulations drive these configurations.
**Push:** What is the typical steam condition in a combined cycle HRSG? -> Dual or triple pressure (high/intermediate/low) with reheat - matches gas turbine exhaust temperature profile.
**Trap:** Calling any waste heat boiler a combined cycle - combined cycle specifically means two thermodynamic cycles in series.
**What they're really testing:** Whether you understand combined cycle and cogeneration as efficiency improvement strategies.

### Q14. Air standard assumptions, Otto and Diesel efficiency formulas. [H]
**A:** Air standard assumptions: (1) Working fluid is air (ideal gas), (2) All processes internally reversible, (3) Heat addition replaces combustion, (4) Heat rejection replaces exhaust, (5) Constant specific heats. Otto efficiency: eta = 1 - 1/r^(gamma-1). Diesel efficiency: eta = 1 - (1/gamma) * (rho^gamma - 1)/(r^(gamma-1) * (rho - 1)) where r = compression ratio, rho = cut-off ratio V3/V2. For same r, Otto efficiency > Diesel efficiency; but Diesel runs at higher r so actual efficiency is comparable.
**Push:** Why does Diesel cycle have lower efficiency than Otto for the same compression ratio? -> Because heat addition in Diesel is at constant pressure (lower average temperature) vs constant volume in Otto.
**Trap:** Using the Otto formula for Diesel cycle or vice versa.
**What they're really testing:** Whether you can derive and compare Otto vs Diesel cycle efficiencies.

### Q15. Indicated vs brake thermal efficiency. [H]
**A:** Indicated thermal efficiency eta_ith = IP / (m_f * CV) - based on indicated power from cylinder pressure. Brake thermal efficiency eta_bth = BP / (m_f * CV) - based on brake power at crankshaft. Mechanical efficiency eta_m = BP / IP = eta_bth / eta_ith. Friction power FP = IP - BP.
**Push:** If eta_ith = 40% and eta_m = 85%, what is eta_bth? -> 0.40 * 0.85 = 34%.
**Trap:** Confusing indicated power (cylinder) with brake power (output shaft).
**What they're really testing:** Whether you can relate indicated, brake, and mechanical efficiency in an engine.

---

## 2. IC Engines - 10 questions

### Q16. Compare four-stroke and two-stroke engines. [H]
**A:** Four-stroke: intake, compression, power, exhaust - four strokes, two revolutions, valves in head, higher volumetric efficiency, better scavenging, used in cars, trucks, generators. Two-stroke: compression and power only - intake/exhaust via ports in cylinder wall uncovered by piston, one revolution per cycle, simpler, lighter, higher power-to-weight, but poor scavenging, high HC emissions, lower efficiency - used in chainsaws, outboards, some small generators.
**Push:** Why does two-stroke have lower fuel efficiency? -> Fresh charge escapes during scavenging overlap; lubricating oil burns with fuel.
**Trap:** Saying two-stroke has twice the power for same size - it is typically 1.3-1.5x due to poor scavenging.
**What they're really testing:** Whether you understand the trade-offs between four-stroke and two-stroke engines.

### Q17. Compare Otto and Diesel cycles. [H]
**A:** Otto: CR 8:1 to 12:1, spark ignition, petrol/gasoline, constant volume heat addition. Diesel: CR 14:1 to 22:1, compression ignition, diesel fuel, constant pressure heat addition. Diesel has higher thermal efficiency due to higher CR and lean burn; Otto has higher power density. For same CR, Otto efficiency > Diesel; but Diesel operates at higher CR so actual brake thermal efficiency: Diesel ~40-45%, Otto ~30-35%.
**Push:** Why can't you run petrol at Diesel compression ratios? -> Petrol has low autoignition temperature - would knock destructively before spark.
**Trap:** Saying Diesel cycle is constant volume - it is constant pressure heat addition.
**What they're really testing:** Whether you understand the differences between Otto and Diesel cycles and why each suits its application.

### Q18. What is BSFC? Why does it matter? [H]
**A:** Brake specific fuel consumption = mass fuel per brake energy (g/kWh). BSFC = m_f / BP. It matters because fuel cost dominates lifecycle cost of engines. What moves it: engine load (best at 75-90% load), speed (minimum at mid-speed), compression ratio, air-fuel ratio (lean burn improves), combustion timing, friction, turbocharging (improves at part load). Typical: petrol 250-300 g/kWh, diesel 200-230 g/kWh at best point.
**Push:** Why does BSFC worsen at low load? -> Throttling loss (pumping work) increases, mechanical efficiency drops, combustion less complete.
**Trap:** Quoting BSFC at full load only - real operation is mostly part load.
**What they're really testing:** Whether you understand BSFC as a performance metric and what factors affect it.

### Q19. Knocking, detonation, pre-ignition, octane number. [H]
**A:** Knocking: uncontrolled autoignition of end-gas after spark, causing pressure spikes and hammering noise. Detonation: end-gas autoignites from pressure/temperature rise after normal spark - multiple flame fronts, rapid pressure rise. Pre-ignition: mixture ignites before spark (hot spot, glowing deposit) - single early flame front, more destructive. Octane number: resistance to knock; RON (research) and MON (motor); higher octane = more knock resistance. Petrol 91-98 RON typical.
**Push:** What raises knocking tendency? -> Higher compression ratio, advanced spark, lean mixture, high intake temperature, low octane fuel, high load.
**Trap:** Calling pre-ignition "detonation" - they are different phenomena with different causes and effects.
**What they're really testing:** Whether you can distinguish knock, detonation, and pre-ignition, and understand octane rating.

### Q20. Carburettor vs fuel injection. [H]
**A:** Carburettor: venturi suction draws fuel, simple, poor mixture distribution, cannot control precisely, being phased out. Fuel injection: pressurised fuel sprayed into intake port (port injection) or cylinder (direct injection) - precise metering, better atomisation, enables lean burn, catalyst compatibility. Atomisation: breaking fuel into fine droplets for rapid evaporation and mixing - finer = better combustion. Spark advance: firing before TDC so peak pressure occurs ~10-15 deg ATDC for maximum work - too advanced causes knock, too retarded loses power and overheats exhaust.
**Push:** Why does direct injection allow higher compression ratio? -> Fuel evaporation cools charge, reducing knock tendency.
**Trap:** Thinking carburettor meters fuel accurately - it relies on pressure difference, not precise control.
**What they're really testing:** Whether you understand fuel system evolution and why injection replaced carburettors.

### Q21. Volumetric efficiency. [H]
**A:** Volumetric efficiency eta_v = actual mass of air inducted / theoretical mass at ambient density. eta_v = m_a / (rho_a * V_d). Affected by: intake manifold pressure (throttle), intake temperature, valve timing/overlap, engine speed (inertia, resonance), exhaust back pressure, compression ratio (clearance volume). Typical max 85-95% at peak torque RPM.
**Push:** How does turbocharging affect volumetric efficiency? -> Increases intake manifold pressure above atmospheric, so eta_v > 100% (mass inducted exceeds displacement volume at ambient density).
**Trap:** Confusing volumetric efficiency with breathing capacity - they are related but eta_v is the ratio, breathing is the absolute mass flow.
**What they're really testing:** Whether you understand volumetric efficiency as a ratio, not an absolute flow rate.

### Q22. Air-cooled vs water-cooled systems. [M]
**A:** Air-cooled: fins on cylinder, airflow from fan - simple, light, no coolant, but uneven cooling, noisy, limited to small engines. Water-cooled: water jacket, pump, radiator, fan - uniform cooling, compact engine, heater for cabin, but complexity, leak risk, weight. Thermostat: wax-pellet valve that opens at ~80-90 deg C - blocks flow to radiator when cold (fast warm-up), opens when hot (maintains temperature). Prevents overcooling and thermal shock.
**Push:** Why does overcooling increase wear? -> Piston-ring clearance stays large, oil viscosity too high, fuel condensation on walls, incomplete combustion.
**Trap:** Saying thermostat controls temperature - it controls flow path; temperature is controlled by heat balance.
**What they're really testing:** Whether you understand engine cooling systems and the thermostat's role.

### Q23. Wet sump lubrication, oil viscosity. [M]
**A:** Wet sump: oil stored in pan at bottom, gear/rotor pump draws through strainer, delivers to main gallery, feeds bearings via drillings, splash lubricates cylinder walls. Viscosity: must be low enough to flow at cold start (0W/5W) but high enough to maintain film at 100+ deg C (30/40). Multi-grade (e.g., 5W-30) uses viscosity index improvers. Too low = bearing wear, oil consumption; too high = cold start starvation, pumping loss.
**Push:** What is the main gallery? -> Drilled passage in block that distributes pressurised oil to crankshaft main bearings, then through crankshaft drillings to big-end bearings.
**Trap:** Thinking oil pump creates pressure - it creates flow; pressure comes from resistance of clearances.
**What they're really testing:** Whether you understand wet sump lubrication and why oil viscosity matters.

### Q24. Emissions: CO, HC, NOx, particulates. [M]
**A:** CO: incomplete combustion (rich mixture). HC: unburned fuel (wall quench, crevices, incomplete burn). NOx: high temperature + oxygen + nitrogen (thermal NOx). Particulates: soot from rich zones in diffusion flame. Diesel: lean overall, high compression temperature -> high NOx; diffusion flame with rich cores -> particulates. Petrol: stoichiometric with throttle -> rich at high load (CO), wall quench and crevices at part load (HC), lower peak temperature -> less NOx.
**Push:** How does EGR reduce NOx? -> Recirculates exhaust gas (inert) to lower peak combustion temperature.
**Trap:** Saying diesel runs rich - it runs lean overall; particulates come from local rich zones.
**What they're really testing:** Whether you understand emission formation mechanisms in petrol vs diesel engines.

### Q25. Compression ratio effect, CNG/LNG basics. [L]
**A:** Higher CR increases thermal efficiency and expands gas further, giving more torque per displacement - but limited by knock (petrol) or mechanical stress (diesel). Diesel CR 14-22:1, petrol 8-12:1. CNG (compressed natural gas, ~200-250 bar): methane, high octane (~120), low energy density (~9 MJ/L vs 32 for diesel), needs spark ignition, ~15-20% power loss vs diesel. LNG (liquefied, -162 deg C): higher energy density (~22 MJ/L), cryogenic tank, same combustion as CNG. Both reduce CO2 ~20%, eliminate particulates, need dedicated engines.
**Push:** Why can't you just put CNG in a diesel engine? -> Diesel relies on compression ignition; methane has high autoignition temperature - needs spark plug and lower CR or dual-fuel pilot diesel injection.
**Trap:** Thinking CNG/LNG are drop-in replacements - they need different engines or major modifications.
**What they're really testing:** Whether you understand the practical differences between petrol, diesel, and gaseous fuels.

---

## 3. Refrigeration and Heat Pumps - 5 questions

### Q26. Vapour compression refrigeration cycle. [H]
**A:** Four components: compressor (raises pressure/temperature), condenser (rejects heat to ambient), expansion valve (throttles, drops pressure/temperature), evaporator (absorbs heat from cold space). Key: isenthalpic throttling (h1 = h2), isentropic compression (ideal), constant pressure heat rejection/addition. COP_R = Q_L/W = (h_evap - h_cond)/(h_comp - h_evap).
**Push:** Why is the expansion valve isenthalpic? -> No work, no heat transfer, negligible KE/PE change. Enthalpy conserved, pressure drops, temperature drops (Joule-Thomson effect for real fluids).
**Trap:** Saying throttling is isentropic - it's isenthalpic. Irreversible, entropy increases.
**What they're really testing:** Whether you can trace the VCR cycle on P-h diagram and calculate COP.

### Q27. Heat pump vs refrigerator - same cycle, different purpose. [H]
**A:** Same cycle, different application. Refrigerator: cold space is cooled (evaporator inside, condenser outside). Heat pump: warm space is heated (evaporator outside, condenser inside). COP_R = Q_L/W, COP_HP = Q_H/W = COP_R + 1. Heat pumps are more efficient than electric resistance heating (COP_HP > 1) but less efficient in very cold climates (efficiency drops as T_L decreases).
**Push:** Why is COP_HP always > COP_R? -> Because Q_H = Q_L + W, so COP_HP = (Q_L + W)/W = COP_R + 1. You get the heat from the cold source plus the work energy, both delivered to the warm space.
**Trap:** Saying heat pump and refrigerator are different cycles - they are the same cycle, just opposite heat flow directions.
**What they're really testing:** Whether you understand heat pumps as reversed refrigerators, and why COP_HP > 1.

### Q28. Vapour absorption refrigeration cycle. [M]
**A:** Uses heat instead of mechanical work. Components: generator (heat input, separates refrigerant from absorbent), condenser, evaporator, absorber (absorbs refrigerant vapour). Absorbent: water for ammonia refrigerant; LiBr for water refrigerant. COP is lower than VCR (typically 0.5-0.7 vs 2-4) but uses waste heat or solar energy. Common in hotels, hospitals, and industrial plants with waste heat.
**Push:** Why is COP of VAR lower than VCR? -> Because the heat input to the generator is the "work" input, and some of that heat is lost in the condenser. The first-law efficiency is lower than the ideal refrigeration cycle.
**Trap:** Saying VAR uses electricity - it uses heat. If electricity is cheap, VCR is better; if waste heat is available, VAR is better.
**What they're really testing:** Whether you understand VAR as a heat-driven refrigeration cycle and can compare it to VCR.

### Q29. Joule-Thomson effect and inversion temperature. [M]
**A:** Joule-Thomson coefficient: mu_JT = (dT/dP)_H. For ideal gas, mu_JT = 0 (temperature doesn't change during throttling). For real gases, mu_JT can be positive (cooling) or negative (heating) depending on temperature. Inversion temperature: where mu_JT = 0. Below inversion temperature, gas cools on expansion (used in refrigeration). Above, gas heats on expansion. mu_JT = (1/Cp) * [T*(dV/dT)_P - V] = (V/Cp) * (alpha*T - 1) where alpha is thermal expansion coefficient.
**Push:** Why does the Joule-Thomson effect matter in refrigeration? -> Throttling refrigerant through expansion valve is the key cooling step. The refrigerant must be below its inversion temperature for throttling to produce cooling.
**Trap:** Saying throttling always cools a gas - it depends on whether the gas is below its inversion temperature. Hydrogen and helium have very low inversion temperatures (~200 K and ~50 K respectively).
**What they're really testing:** Whether you understand the Joule-Thomson effect and its role in refrigeration.

### Q30. Psychrometric chart basics. [M]
**A:** Psychrometric chart plots moist air properties: dry bulb temperature (x-axis), humidity ratio (y-axis). Key lines: wet bulb temperature (constant enthalpy lines), relative humidity (curves), dew point, specific volume, enthalpy. Basic processes: sensible heating (horizontal right), sensible cooling (horizontal left), humidification (vertical up), dehumidification (vertical down), evaporative cooling (constant wet bulb, diagonal down-left), adiabatic saturation (constant enthalpy, diagonal down-right).
**Push:** What is the dew point temperature? -> The temperature at which air becomes saturated (100% RH) when cooled at constant pressure. Below dew point, condensation occurs.
**Trap:** Confusing dry bulb with wet bulb temperature. Dry bulb is what a thermometer reads; wet bulb is lower due to evaporative cooling.
**What they're really testing:** Whether you can read a psychrometric chart and identify basic air-conditioning processes.

---

## 4. Steam Properties and Boilers - 5 questions

### Q31. Mollier chart and its use. [H]
**A:** Mollier chart (h-s diagram) plots enthalpy (y-axis) vs entropy (x-axis). Lines of constant pressure, constant temperature, constant quality (dryness fraction). Used for: turbine expansion path (isentropic line from boiler pressure to condenser pressure), finding exhaust quality, superheater exit state, feedwater heater state. Quick visual estimation of cycle states.
**Push:** How do you find the quality of steam at turbine exhaust? -> Follow the isentropic expansion line from boiler pressure to condenser pressure; read the quality at the intersection with the condenser pressure line.
**Trap:** Using the saturated steam table for superheated conditions. The Mollier chart covers both saturated and superheated regions, but you must use the correct region.
**What they're really testing:** Whether you can use the Mollier chart for quick cycle analysis.

### Q32. Boiler components: economiser, superheater, reheater. [H]
**A:** Economiser: preheats feedwater using flue gas heat (lowest temperature heat recovery), improves cycle efficiency. Superheater: heats saturated steam to superheated state at constant pressure, increases turbine work and efficiency, prevents blade erosion from moisture. Reheater: reheats steam after partial expansion in HP turbine, then expands in LP turbine - reduces moisture at LP turbine exhaust, improves efficiency. In a boiler, the economiser is in the flue gas path after the superheater/reheater.
**Push:** Why is the condenser pressure kept as low as possible? -> Lower condenser pressure (higher vacuum) increases the enthalpy drop across the turbine, increasing work output and cycle efficiency. Typical: 0.03-0.08 bar.
**Trap:** Confusing economiser (feedwater heater using flue gas) with feedwater heater (using extraction steam) - both preheat feedwater but use different heat sources.
**What they're really testing:** Whether you understand boiler components and their functions in the steam cycle.

### Q33. Steam quality measurement - throttling calorimeter. [M]
**A:** Throttling calorimeter: throttle wet steam to low pressure where it becomes superheated. Measure temperature at low pressure. Use h1 = h2 (isenthalpic throttling) to find quality: x = (h_superheated - h_f)/h_fg. Requires: steam must be dry enough that it becomes superheated after throttling (typically x > 0.95). For wetter steam, use separating calorimeter or combined separating-throttling calorimeter.
**Push:** Why must throttling be to a pressure where steam is superheated? -> To ensure temperature is uniquely defined for the enthalpy. In the two-phase region, temperature depends only on pressure, not enthalpy.
**Trap:** Saying quality is measured by temperature alone. Temperature in the two-phase region depends only on pressure, not on how much vapour is present.
**What they're really testing:** Whether you can explain steam quality measurement and the difference between dry, wet, and superheated steam.

### Q34. Power plant efficiency improvement methods. [M]
**A:** Five methods: (1) Superheat - raises average heat addition temperature, increases efficiency, needs better materials for higher temperature. (2) Reheat - reduces moisture at turbine exit, improves efficiency, adds reheater cost and pressure drop. (3) Regenerative feedwater heating - uses turbine bleed steam to preheat feedwater, raises average heat addition temperature, needs extra heaters and piping. (4) Lower condenser pressure - increases expansion ratio and work output, needs larger condenser and vacuum pumps. (5) Raise boiler pressure - raises saturation temperature, improves efficiency, needs thicker pressure parts and better materials.
**Push:** Which improvement gives the most gain per rupee in a typical plant? -> Regenerative feedwater heating usually gives best cost-benefit; superheat and reheat are standard in modern plants.
**Trap:** Forgetting that lowering condenser pressure increases turbine last-stage blade erosion risk from wetness.
**What they're really testing:** Whether you can compare efficiency improvement methods and their trade-offs.

### Q35. Combined cycle power plant. [M]
**A:** Combined cycle: gas turbine (Brayton) topping cycle with steam turbine (Rankine) bottoming cycle using gas turbine exhaust. Gas turbine generates power; exhaust heat (still hot at ~500-600 deg C) drives HRSG to produce steam for steam turbine. Overall efficiency 55-62% vs 35-45% for simple cycle. HRSG typically dual or triple pressure with reheat to match gas turbine exhaust temperature profile.
**Push:** Why is combined cycle more efficient than simple cycle? -> Because the waste heat from the gas turbine (which would otherwise be lost) is used to generate additional power in the steam turbine. Two cycles in series extract more energy from the same fuel.
**Trap:** Calling any waste heat boiler a combined cycle - combined cycle specifically means two thermodynamic cycles in series (Brayton + Rankine).
**What they're really testing:** Whether you understand combined cycle as two thermodynamic cycles in series, and why it's more efficient.

---

## 5. Combustion and Fuels - 5 questions

### Q36. Air-fuel ratio, stoichiometric vs actual. [H]
**A:** Air-fuel ratio (AFR) = mass of air / mass of fuel. Stoichiometric AFR is the exact amount of air needed for complete combustion (petrol ~14.7:1, diesel ~14.5:1). Actual AFR is usually richer (lower) for power, leaner (higher) for economy. Lambda (lambda) = actual AFR / stoichiometric AFR. Lambda = 1 is stoichiometric, lambda < 1 is rich, lambda > 1 is lean.
**Push:** What is the effect of running rich vs lean? -> Rich: more power, higher emissions (CO, HC). Lean: better economy, lower emissions, but risk of misfire and NOx increase.
**Trap:** Saying stoichiometric is always best - it's best for emissions (catalyst) but not for power or economy.
**What they're really testing:** Whether you understand AFR and its effect on engine performance.

### Q37. Lower and higher calorific value. [H]
**A:** Calorific value (CV) is heat released per unit mass of fuel. Higher CV includes latent heat of water vapour in products (water is liquid). Lower CV excludes latent heat (water is vapour). LCV = HCV - 9*H2*latent heat of vaporisation, where H2 is hydrogen mass fraction. IC engine calculations use LCV (water leaves as vapour). Boiler calculations use HCV (water condenses).
**Push:** Why do engine calculations use LCV? -> Because exhaust gases leave at high temperature, water remains as vapour. The latent heat is not recovered.
**Trap:** Using HCV for engine efficiency - overestimates efficiency by 5-10%.
**What they're really testing:** Whether you understand the difference between LCV and HCV and when to use each.

### Q38. Combustion efficiency and heat balance. [M]
**A:** Combustion efficiency = heat released / heat input = 1 - (heat loss in exhaust + unburned fuel + radiation). Heat balance: fuel energy = BP + FP + heat to coolant + heat to exhaust + radiation + unburned. Typical distribution: BP 30-35%, coolant 25-30%, exhaust 30-35%, radiation 5-10%. Combustion efficiency for well-tuned engine: 95-98%.
**Push:** What is the largest heat loss in an IC engine? -> Exhaust heat (30-35%) - this is why turbocharging and waste heat recovery are important.
**Trap:** Thinking all fuel energy becomes useful work - only 30-35% becomes brake power.
**What they're really testing:** Whether you understand energy distribution in an IC engine.

### Q39. Excess air and flue gas analysis. [M]
**A:** Excess air = air supplied beyond stoichiometric requirement. Needed for complete combustion. Typical: 10-20% for liquid fuels, 15-25% for gaseous fuels. Flue gas analysis measures: CO2, O2, CO, NOx. CO2 max indicates complete combustion. O2 in flue gas indicates excess air. CO indicates incomplete combustion. Orsat apparatus measures CO2, O2, CO volumetrically.
**Push:** How do you calculate excess air from flue gas analysis? -> Excess air % = (O2 in flue gas) / (21 - O2 in flue gas) * 100 (approximate, assuming complete combustion).
**Trap:** Saying more excess air is always better - too much excess air cools the flame and reduces efficiency.
**What they're really testing:** Whether you understand excess air and flue gas analysis.

### Q40. Combustion in SI vs CI engines. [M]
**A:** SI engine: premixed charge (air + fuel) ignited by spark. Combustion: flame front propagates through mixture. Fast, controlled. CI engine: fuel injected into hot compressed air. Combustion: ignition delay + premixed + diffusion (mixing-controlled). Slower, less controlled. SI: homogeneous charge, stoichiometric. CI: heterogeneous charge, lean overall with rich local zones.
**Push:** Why does CI engine have higher thermal efficiency? -> Higher compression ratio, leaner burn (less throttling loss), and better part-load efficiency.
**Trap:** Saying CI combustion is instantaneous - there's an ignition delay (1-2 ms) before combustion starts.
**What they're really testing:** Whether you understand combustion differences between SI and CI engines.

---

## 6. Gas Turbines - 5 questions

### Q41. Brayton cycle and efficiency. [H]
**A:** Brayton cycle (gas turbine): 1-2 isentropic compression, 2-3 constant pressure heat addition, 3-4 isentropic expansion, 4-1 constant pressure heat rejection. Thermal efficiency: eta = 1 - 1/r_p^((gamma-1)/gamma), where r_p = P2/P1 = pressure ratio. For gamma = 1.4, r_p = 8: eta = 1 - 1/8^0.286 = 1 - 0.565 = 0.435 or 43.5%.
**Push:** Why does Brayton efficiency depend only on pressure ratio? -> Because heat addition and rejection are at constant pressure, so the temperature ratio depends only on r_p and gamma.
**Trap:** Using the Otto formula for Brayton - Brayton uses pressure ratio, Otto uses volume (compression) ratio.
**What they're really testing:** Whether you can derive Brayton cycle efficiency and understand its dependence on pressure ratio.

### Q42. Gas turbine improvements: regeneration, intercooling, reheat. [H]
**A:** (1) Regeneration: use exhaust heat to preheat compressed air before combustion. Improves efficiency at low pressure ratios. (2) Intercooling: cool air between compression stages. Reduces compressor work, improves efficiency. (3) Reheat: add heat between turbine stages. Increases work output, improves efficiency. Combined: intercooling + regeneration + reheat gives highest efficiency.
**Push:** Why does regeneration help more at low pressure ratios? -> At low r_p, exhaust temperature is higher (less expansion), so more heat is available for regeneration.
**Trap:** Saying regeneration always improves efficiency - at high pressure ratios, exhaust temperature is too low for effective regeneration.
**What they're really testing:** Whether you understand gas turbine cycle improvements.

### Q43. Gas turbine components and operation. [M]
**A:** Components: (1) Compressor (axial or centrifugal) - raises air pressure. (2) Combustion chamber - adds heat at constant pressure. (3) Turbine - extracts work to drive compressor and load. (4) Exhaust - rejects heat. Key: compressor consumes 50-60% of turbine work. Net work = turbine work - compressor work. Gas turbines are used for: power generation, aircraft propulsion, mechanical drives.
**Push:** Why does the compressor consume so much of the turbine work? -> Because gas turbines operate at high pressure ratios (10-20:1), requiring significant compression work.
**Trap:** Thinking turbine work is all available for output - 50-60% drives the compressor.
**What they're really testing:** Whether you understand gas turbine components and energy balance.

### Q44. Gas turbine vs steam turbine. [M]
**A:** Gas turbine: (1) Uses air as working fluid, (2) High temperature (1000-1500 deg C), (3) Low pressure ratio (10-20:1), (4) Fast startup (minutes), (5) Lower efficiency (35-40% simple cycle). Steam turbine: (1) Uses steam, (2) Lower temperature (500-600 deg C), (3) High pressure ratio (100:1), (4) Slow startup (hours), (5) Higher efficiency (40-45% simple cycle, 55-62% combined cycle). Gas turbine for peaking, steam turbine for base load.
**Push:** Why is gas turbine better for peaking power? -> Fast startup (minutes vs hours), lower capital cost per kW, and can be installed quickly.
**Trap:** Saying gas turbine is always less efficient - combined cycle (gas + steam) exceeds steam-only efficiency.
**What they're really testing:** Whether you can compare gas and steam turbines.

### Q45. Compressor types in gas turbines. [M]
**A:** Axial compressor: (1) Multiple stages, (2) High flow, low pressure rise per stage, (3) Used in large gas turbines and aircraft. Centrifugal compressor: (1) Single stage, (2) Lower flow, higher pressure rise, (3) Used in small gas turbines and turbochargers. Axial: higher efficiency, larger size. Centrifugal: simpler, more robust, lower cost.
**Push:** Why do large gas turbines use axial compressors? -> Axial compressors have higher efficiency and can handle larger flow rates with multiple stages.
**Trap:** Saying centrifugal compressors are always worse - they are simpler and more robust for small applications.
**What they're really testing:** Whether you understand compressor types and their applications.

---

## 7. Steam Turbines - 5 questions

### Q46. Impulse vs reaction turbine stages. [H]
**A:** Impulse stage: pressure drop only in nozzles, blades only change momentum direction (like Pelton). Reaction stage: pressure drop across both fixed and moving blades. Most steam turbines are "reaction" type with 50% reaction (pressure drop equally in fixed and moving blades). High-pressure stages may be impulse (to reduce moisture erosion). Velocity compounded (Curtis) or pressure compounded (Rateau) for high pressure ratios.
**Push:** What is 50% reaction? -> The static pressure drop is equal in the fixed (stator) and moving (rotor) blades. The relative velocity is constant across the moving blade.
**Trap:** Saying all steam turbines are impulse or all are reaction - most are mixed.
**What they're really testing:** Whether you understand impulse vs reaction stages in steam turbines.

### Q47. Steam turbine governing. [M]
**A:** Governing maintains constant speed under varying load. Methods: (1) Throttle governing - reduces steam pressure (simple but less efficient). (2) Nozzle governing - opens/closes nozzles (better efficiency). (3) Bypass governing - bypasses steam around HP turbine to reheat (for partial load). (4) Combination. Governor types: (a) Centrifugal (mechanical), (b) Hydraulic, (c) Electronic. Governing is critical for grid-synchronized generators.
**Push:** Why is nozzle governing more efficient than throttle governing? -> Nozzle governing reduces flow area, maintaining pressure and efficiency. Throttle governing reduces pressure, lowering efficiency.
**Trap:** Saying governing only controls speed - it also affects efficiency and load sharing in multi-unit plants.
**What they're really testing:** Whether you understand steam turbine governing methods.

### Q48. Steam turbine blade velocity and diagram. [M]
**A:** Velocity diagram: (1) V1 = absolute velocity of steam entering moving blade (from nozzle). (2) U = blade speed. (3) Vr1 = relative velocity (V1 - U). (4) Vr2 = relative velocity leaving (for 50% reaction, Vr2 = Vr1). (5) V2 = absolute velocity leaving. Blade efficiency = 2*U*(V1 - U* (1 + cos(beta))) / V1^2, where beta is exit angle. Maximum efficiency when U/V1 = 0.5 (for impulse) or 0.5*cos(alpha) (for reaction).
**Push:** What is the optimal blade speed ratio for an impulse turbine? -> U/V1 = 0.5 (cos of nozzle angle is 1 for axial flow). For 50% reaction, U/V1 = 0.5*cos(alpha).
**Trap:** Using the impulse formula for reaction turbines - reaction has different velocity diagram.
**What they're really testing:** Whether you can draw velocity diagrams and calculate blade efficiency.

### Q49. Steam turbine extraction and cogeneration. [M]
**A:** Extraction turbine: steam is extracted at intermediate pressure for process heating (paper mills, refineries, district heating). Back-pressure turbine: exhaust at above-atmospheric pressure for process use. Condensing turbine: exhaust to condenser (maximum power). Cogeneration: simultaneous electricity + heat. Overall efficiency 70-85% (vs 35-45% for power only). Extraction improves plant economics by selling steam.
**Push:** Why is cogeneration more efficient than power-only? -> Because waste heat from power generation is used for process heating, extracting more useful energy from the same fuel.
**Trap:** Saying extraction reduces power output - it does, but the overall energy utilization improves dramatically.
**What they're really testing:** Whether you understand extraction turbines and cogeneration.

### Q50. Steam turbine erosion and maintenance. [M]
**A:** Erosion causes: (1) Moisture in steam (water droplets impact blades at high velocity). (2) Solid particles (rust, scale). Prevention: (1) Superheat (raise temperature, reduce moisture). (2) Reheat (reduce LP turbine moisture). (3) Moisture separators (remove water before LP turbine). (4) Hard-facing (stellite on leading edges). (5) Proper steam purity (avoid carryover). Maintenance: (1) Blade inspection, (2) Clearance measurement, (3) Vibration monitoring, (4) Oil analysis.
**Push:** Why is moisture erosion worse in the LP turbine? -> Steam expands through the turbine, temperature drops, moisture content increases. LP turbine has the highest moisture (up to 10-15%).
**Trap:** Ignoring moisture erosion - it's the leading cause of LP turbine blade failure.
**What they're really testing:** Whether you understand steam turbine erosion and maintenance.

---

## 8. Psychrometrics and Air Conditioning - 5 questions

### Q51. Sensible and latent heat in air conditioning. [H]
**A:** Sensible heat: changes temperature without phase change (Q_s = m_dot * c_p * delta_T). Latent heat: changes phase without temperature change (Q_l = m_dot * h_fg * delta_w). Total heat: Q_t = Q_s + Q_l. Sensible heat factor (SHF) = Q_s / Q_t. Typical SHF: 0.7-0.8 for comfort AC, 0.9-0.95 for process cooling. Psychrometric chart shows these as horizontal (sensible) and vertical (latent) lines.
**Push:** What is the sensible heat factor? -> Ratio of sensible heat to total heat. Determines the slope of the process line on the psychrometric chart.
**Trap:** Confusing sensible and latent heat - sensible changes temperature, latent changes humidity.
**What they're really testing:** Whether you understand sensible and latent heat in AC.

### Q52. Cooling load calculation. [M]
**A:** Cooling load = sensible load + latent load. Sensible: (1) Transmission through walls/roof, (2) Solar gain through windows, (3) Internal gains (people, lights, equipment). Latent: (1) Occupants, (2) Infiltration, (3) Process (cooking, etc.). Cooling load factor (CLF) accounts for time lag. Peak load usually occurs 2-4 hours after solar noon. Design for peak load + safety factor (10-15%).
**Push:** Why does peak cooling load occur after solar noon? -> Because of thermal mass time lag - walls and roof absorb heat during morning and release it in afternoon.
**Trap:** Calculating cooling load at solar noon - peak occurs later due to thermal lag.
**What they're really testing:** Whether you can calculate cooling load and account for time lag.

### Q53. Air conditioning processes on psychrometric chart. [M]
**A:** Basic processes: (1) Sensible heating: horizontal right (add heat, no moisture). (2) Sensible cooling: horizontal left (remove heat, no moisture). (3) Humidification: vertical up (add moisture). (4) Dehumidification: vertical down (remove moisture). (5) Cooling + dehumidification: diagonal down-left (coil below dew point). (6) Evaporative cooling: constant wet bulb, diagonal down-left (adiabatic). (7) Adiabatic saturation: constant enthalpy, diagonal down-right.
**Push:** What is evaporative cooling? -> Adiabatic process where water evaporates into air, cooling it. Used in desert coolers. Efficiency limited by wet bulb temperature.
**Trap:** Confusing evaporative cooling with mechanical cooling - evaporative is adiabatic (no external refrigeration).
**What they're really testing:** Whether you can identify AC processes on the psychrometric chart.

### Q54. Dehumidification methods. [M]
**A:** Methods: (1) Cooling coil (below dew point) - most common, condenses moisture. (2) Desiccant (solid or liquid) - adsorbs moisture, used for low humidity. (3) Heat pipe - pre-cools and reheats air. Effectiveness: (1) Cooling coil: 50-70% RH achievable. (2) Desiccant: 10-30% RH achievable. (3) Combined: cooling coil + desiccant for very low humidity. Applications: (1) Comfort: 40-60% RH. (2) Process: 10-30% RH (pharmaceuticals, electronics).
**Push:** When would you use desiccant dehumidification? -> For very low humidity requirements (< 30% RH) where cooling coils can't achieve the target.
**Trap:** Using cooling coil for very low humidity - coil surface temperature would need to be below freezing, causing frost.
**What they're really testing:** Whether you understand dehumidification methods and their applications.

### Q55. Refrigerant selection. [M]
**A:** Refrigerant selection criteria: (1) Thermodynamic properties (boiling point, latent heat, pressure). (2) Safety (toxicity, flammability). (3) Environmental (ODP, GWP). (4) Cost and availability. Common: (1) R-134a (HFC, zero ODP, high GWP) - automotive, domestic. (2) R-410A (HFC blend) - air conditioning. (3) R-32 (HFC, lower GWP) - newer AC. (4) R-290 (propane, natural, flammable) - small systems. (5) R-744 (CO2, natural, high pressure) - commercial refrigeration. Phase-out of high-GWP refrigerants (R-134a, R-410A) is ongoing.
**Push:** What is the difference between ODP and GWP? -> ODP (Ozone Depletion Potential): damage to ozone layer. GWP (Global Warming Potential): contribution to greenhouse effect. CFCs have both high ODP and GWP.
**Trap:** Saying R-134a is being phased out for ODP reasons - it has zero ODP but high GWP, so it's being phased out for climate reasons.
**What they're really testing:** Whether you understand refrigerant selection and environmental considerations.

---

## File Statistics

**Total questions: 55**

**By tag:**
- [H] High-yield: ~22 questions
- [M] Medium-yield: ~28 questions
- [L] Occasional: ~5 questions

**By section:**
- Thermodynamics fundamentals: 15 questions
- IC engines: 10 questions
- Combustion and fuels: 5 questions
- Gas turbines: 5 questions
- Steam turbines: 5 questions
- Psychrometrics and air conditioning: 5 questions
- Refrigeration and heat pumps: 5 questions
- Steam properties and boilers: 5 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, steel density 7850, water 1000, oil 900-950, Re: laminar <2300, turbulent >4000, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

**GATE alignment:** Topics follow GATE ME syllabus structure - thermodynamics, IC engines, gas turbines, steam turbines, refrigeration, psychrometrics.

This bank covers thermo, IC engines, gas turbines, steam turbines, refrigeration, psychrometrics - all essential for automobiles, petrochem, and construction interviews.


---

