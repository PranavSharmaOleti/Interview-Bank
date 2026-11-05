# Manufacturing, Welding, and NDT - Core Interview Bank

**Part 8 of 10 | 50 questions | Casting, forming, machining, heat treatment, welding processes, NDT methods, tolerances, metrology**

*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Casting - 10 questions

### Q1. Sand casting process and defects. [H]
**A:** Sand casting: (1) Make pattern (wood/metal), (2) Prepare mould (sand + binder), (3) Pour molten metal, (4) Solidify, (5) Shakeout, (6) Clean and inspect. Common defects: (a) Shrinkage cavities (insufficient feeding), (b) Gas porosity (trapped gas), (c) Sand inclusions (poor mould), (d) Cold shuts (incomplete fusion), (e) Hot tearing (restrained contraction). Solutions: proper gating system, riser design, degassing, mould quality.
**Push:** What is a riser and why is it needed? -> Riser is a reservoir of molten metal that feeds the casting as it shrinks during solidification, preventing shrinkage cavities.
**Trap:** Saying sand casting is only for low-quality parts - modern sand casting with proper process control produces high-quality parts.
**What they're really testing:** Whether you understand the sand casting process and common defects.

### Q2. Investment casting (lost wax). [H]
**A:** Investment casting: (1) Make wax pattern (injection), (2) Assemble patterns on tree, (3) Dip in ceramic slurry, (4) Burn out wax (dewax), (5) Pour metal, (6) Break mould, (7) Cut and finish. Advantages: excellent surface finish (Ra 1.6-3.2 microns), high dimensional accuracy (IT 8-10), complex shapes, thin walls. Used for turbine blades, medical implants, jewellery, aerospace components.
**Push:** Why is investment casting used for turbine blades? -> Because it can produce complex internal cooling passages and airfoil shapes with tight tolerances and good surface finish.
**Trap:** Thinking investment casting is only for small parts - large parts (up to 100 kg) can be cast using investment casting.
**What they're really testing:** Whether you know investment casting process and its advantages.

### Q3. Die casting: hot chamber vs cold chamber. [H]
**A:** Die casting: high-pressure injection of molten metal into metal mould. Hot chamber: melting furnace is part of machine, metal is pumped directly - fast cycle, good for low melting point metals (Zn, Mg, Pb). Cold chamber: metal is ladled into separate chamber - slower cycle, used for high melting point metals (Al, Cu, brass). Advantages: high production rate, excellent surface finish, tight tolerances. Disadvantages: high tooling cost, limited to non-ferrous metals.
**Push:** Why can't you use hot chamber for aluminium? -> Aluminium reacts with iron in the hot chamber, and the high melting point (660 deg C) damages the pump components.
**Trap:** Using hot chamber for high-melting-point metals - causes equipment damage and contamination.
**What they're really testing:** Whether you can distinguish hot chamber and cold chamber die casting.

### Q4. Continuous casting. [M]
**A:** Continuous casting: molten metal is poured into a water-cooled mould, solidified shell is withdrawn continuously, and cut to length. Advantages: high yield (no ingot cropping), uniform quality, lower energy, faster production. Used for: steel slabs, billets, blooms; aluminium ingots; copper rods. Key parameters: casting speed, mould oscillation, secondary cooling, electromagnetic stirring.
**Push:** Why is continuous casting preferred over ingot casting for steel? -> Higher yield (95% vs 80%), better quality (less segregation), lower cost, and continuous production.
**Trap:** Thinking continuous casting is only for steel - it's used for aluminium, copper, and other metals too.
**What they're really testing:** Whether you understand continuous casting and its advantages.

### Q5. Solidification and shrinkage. [H]
**A:** Solidification: liquid -> solid with volume change (shrinkage). Shrinkage allowance: (1) Liquid shrinkage (contraction before solidification), (2) Solidification shrinkage (volume reduction during phase change), (3) Solid shrinkage (contraction after solidification). Pattern allowances: shrinkage allowance (metal-specific), draft allowance (taper for removal), machining allowance (extra material for finishing), distortion allowance (for warping). Feeding: risers supply molten metal to compensate for solidification shrinkage.
**Push:** What is the shrinkage allowance for cast iron vs steel? -> Cast iron: ~0.8-1.0%, steel: ~1.5-2.0%, aluminium: ~1.3-1.6%. Cast iron shrinks less due to graphite expansion during solidification.
**Trap:** Using the same shrinkage allowance for all metals - each metal has different shrinkage characteristics.
**What they're really testing:** Whether you understand solidification shrinkage and pattern allowances.

### Q6. Gating system design. [M]
**A:** Gating system: (1) Pouring basin (receives metal), (2) Sprue (vertical channel), (3) Runner (horizontal channel), (4) Gate (entry to mould cavity), (5) Riser (feeding). Design goals: fill mould quickly without turbulence, avoid air aspiration, ensure directional solidification (riser solidifies last). Gating ratio: sprue area : runner area : gate area (typically 1:2:4 for non-pressurised, 4:2:1 for pressurised).
**Push:** What is the difference between pressurised and non-pressurised gating? -> Pressurised: gate area < runner area, metal under pressure, less turbulence but more erosion. Non-pressurised: gate area > runner area, gravity flow, less erosion but more air aspiration risk.
**Trap:** Making gates too small - causes turbulence and air aspiration; making gates too large - causes shrinkage and poor feeding.
**What they're really testing:** Whether you can design a gating system and understand the trade-offs.

### Q7. Shell moulding. [M]
**A:** Shell moulding: (1) Heat metal pattern, (2) Apply sand-resin mixture (sticks to hot pattern), (3) Cure shell (bake at 150-300 deg C), (4) Remove shell from pattern, (5) Assemble two halves, (6) Pour metal. Advantages: better surface finish (Ra 2.5-6.3), higher accuracy (IT 9-11), thinner walls possible, good for medium production. Disadvantages: higher cost than sand casting, limited size.
**Push:** Why is shell moulding better than sand casting for surface finish? -> Because the shell is smooth and hard, unlike sand mould which has rough surface and can erode during pouring.
**Trap:** Thinking shell moulding is just sand casting with a different binder - it's a different process with different capabilities.
**What they're really testing:** Whether you know shell moulding and can compare it to sand casting.

### Q8. Centrifugal casting. [M]
**A:** Centrifugal casting: molten metal is poured into a rotating mould, centrifugal force distributes metal to outer wall, creating a hollow cylinder. Advantages: dense, fine-grained structure, no core needed, good for cylindrical parts (pipes, rings, bushings). Types: (1) True centrifugal (rotating mould, hollow part), (2) Semi-centrifugal (rotating mould, solid part with central hole), (3) Centrifuged (rotating mould, non-symmetrical part).
**Push:** Why does centrifugal casting produce denser parts? -> Centrifugal force pushes denser metal to outer wall and lighter impurities (slag, gas) to inner surface, which is later machined off.
**Trap:** Thinking centrifugal casting can only make perfectly cylindrical parts - semi-centrifugal and centrifuged types handle other shapes.
**What they're really testing:** Whether you understand centrifugal casting and its advantages.

### Q9. Casting defects and inspection. [H]
**A:** Common casting defects: (1) Shrinkage (insufficient feeding), (2) Porosity (gas or shrinkage), (3) Inclusions (sand, slag), (4) Cold shuts (incomplete fusion), (5) Hot tearing (restrained contraction), (6) Misruns (insufficient metal), (7) Flash (excess metal at parting line). Inspection: visual, dimensional, NDT (RT, UT, MT, PT), pressure test (for castings).
**Push:** How do you distinguish shrinkage porosity from gas porosity? -> Shrinkage porosity is irregular, angular, in thick sections. Gas porosity is spherical, smooth, anywhere in casting.
**Trap:** Saying all porosity is the same - shrinkage and gas porosity have different causes and locations.
**What they're really testing:** Whether you can identify casting defects and their causes.

### Q10. Metal mould casting (gravity die casting). [M]
**A:** Gravity die casting: molten metal poured into permanent metal mould (die) under gravity. Advantages: better surface finish than sand casting, higher accuracy, longer mould life, faster production. Disadvantages: higher tooling cost, limited to non-ferrous metals (Al, Mg, Zn), not for complex internal features. Moulds are preheated and coated with refractory wash.
**Push:** Why is gravity die casting limited to non-ferrous metals? -> Ferrous metals have high melting points that damage steel moulds; also, iron reacts with steel moulds.
**Trap:** Using gravity die casting for ferrous metals - causes mould damage and contamination.
**What they're really testing:** Whether you know gravity die casting and its limitations.

## 2. Forming and Machining - 10 questions

### Q11. Forging processes: open die vs closed die. [H]
**A:** Open die forging: workpiece is compressed between flat dies, shape controlled by hammering/placement. Used for large parts (shafts, discs, rings). Closed die forging (impression die): workpiece is compressed in a die with shaped cavities. Used for complex parts (crankshafts, connecting rods, gears). Advantages: good grain flow, high strength, good surface finish. Disadvantages: high tooling cost (closed die), limited to simple shapes (open die).
**Push:** Why is forged part stronger than cast part? -> Forging aligns grain flow along the shape, improving strength and toughness. Casting has random grain structure with potential defects.
**Trap:** Saying forging always produces better parts - forging has higher cost and is limited by die complexity.
**What they're really testing:** Whether you can distinguish open die and closed die forging.

### Q12. Rolling process and types. [H]
**A:** Rolling: metal is passed between rotating rolls to reduce thickness and shape. Hot rolling: above recrystallization temperature, large reductions, rough surface. Cold rolling: below recrystallization temperature, small reductions, smooth surface, strain hardening. Types: (1) Flat rolling (plates, sheets), (2) Shape rolling (I-beams, rails), (3) Ring rolling (rings), (4) Thread rolling (threads). Advantages: high production rate, good surface finish (cold), strain hardening.
**Push:** Why is cold rolling used for sheet metal? -> Cold rolling gives better surface finish, tighter tolerances, and strain hardening (increased strength) compared to hot rolling.
**Trap:** Saying hot rolling is always better - hot rolling has rough surface and looser tolerances.
**What they're really testing:** Whether you understand rolling processes and can select hot vs cold rolling.

### Q13. Extrusion: direct vs indirect. [H]
**A:** Extrusion: metal is forced through a die to produce long shapes with constant cross-section. Direct (forward) extrusion: ram pushes billet through die, friction between billet and container. Indirect (backward) extrusion: die moves into stationary billet, no friction between billet and container. Advantages: complex cross-sections, good surface finish, high production rate. Used for: aluminium profiles, pipes, rods, window frames.
**Push:** Why is indirect extrusion used for high-strength materials? -> Because there is no friction between billet and container, so lower force is required and die life is longer.
**Trap:** Confusing direct and indirect extrusion - direct has friction, indirect doesn't.
**What they're really testing:** Whether you can distinguish direct and indirect extrusion.

### Q14. Drawing process: wire and tube. [M]
**A:** Drawing: metal is pulled through a die to reduce cross-section. Wire drawing: multiple dies in series, used for wires, rods. Tube drawing: tube is pulled over a mandrel, used for seamless tubes. Advantages: excellent surface finish, tight tolerances, strain hardening. Disadvantages: limited reduction per pass (20-40%), requires annealing between passes for large reductions.
**Push:** What is the maximum reduction per pass in wire drawing? -> Typically 20-40% area reduction. Larger reductions cause fracture or excessive die wear.
**Trap:** Trying to reduce too much in one pass - causes fracture or poor surface finish.
**What they're really testing:** Whether you understand drawing processes and their limitations.

### Q15. Machining: turning, milling, drilling, grinding. [H]
**A:** Turning: single-point tool removes material from rotating workpiece (lathe). Milling: multi-point tool removes material from workpiece (milling machine). Drilling: rotating drill bit creates holes. Grinding: abrasive wheel removes material for finishing. Selection based on: part geometry, material, tolerance, surface finish, production volume. Turning for cylindrical parts, milling for flat/complex surfaces, drilling for holes, grinding for precision finishing.
**Push:** When would you use grinding instead of turning? -> When tolerance is very tight (IT 5-6) or surface finish is critical (Ra < 0.8 microns). Turning is faster but less precise.
**Trap:** Using grinding for roughing - grinding is slow and expensive, only for finishing.
**What they're really testing:** Whether you can select the right machining process for given requirements.

### Q16. Machining parameters: speed, feed, depth of cut. [H]
**A:** Cutting speed V = pi*D*N/1000 (m/min) where D is workpiece diameter (mm), N is RPM. Feed f = distance tool advances per revolution (mm/rev). Depth of cut d = radial distance removed (mm). Material removal rate MRR = V*f*d (mm3/min). Tool life depends on V, f, d, tool material, and workpiece material. Taylor's tool life equation: V*T^n = C, where T is tool life (min), n and C are constants.
**Push:** If you double cutting speed, what happens to tool life? -> Tool life decreases significantly. From Taylor's equation: if n=0.2, doubling V reduces T by factor of 2^(1/0.2) = 32. Tool life drops 32 times.
**Trap:** Confusing cutting speed with spindle speed - cutting speed is surface speed (m/min), spindle speed is RPM.
**What they're really testing:** Whether you can calculate machining parameters and understand tool life.

### Q17. Tool wear and tool life. [M]
**A:** Tool wear types: (1) Flank wear (gradual wear on flank face), (2) Crater wear (wear on rake face due to chip flow), (3) Notch wear (at depth of cut line), (4) Chipping (breakage of cutting edge). Tool life: time until tool fails or reaches wear limit. Factors affecting tool life: cutting speed (most significant), feed, depth of cut, tool material, workpiece material, coolant. Tool materials: HSS (high speed steel), carbide, ceramic, CBN, diamond.
**Push:** What is the most common tool failure mode? -> Flank wear - gradual wear on the flank face that increases cutting force and temperature, eventually causing dimensional inaccuracy or surface finish degradation.
**Trap:** Thinking tool wear is always gradual - sudden failure can occur due to chipping, thermal shock, or built-up edge.
**What they're really testing:** Whether you understand tool wear mechanisms and tool life factors.

### Q18. CNC machining. [M]
**A:** CNC (Computer Numerical Control): machine tool controlled by computer program (G-code). Advantages: high precision, repeatability, complex shapes, automation, reduced setup time. Types: CNC lathe (turning), CNC mill (milling), CNC router, CNC plasma cutter. Key components: CNC controller, servo motors, ball screws, linear guides. Programming: G-code (geometric commands), M-code (miscellaneous commands).
**Push:** What is the difference between CNC and NC? -> NC (Numerical Control) uses punched tape for program storage. CNC uses computer for program storage and editing, with more flexibility and features.
**Trap:** Saying CNC eliminates need for skilled operators - CNC still requires programming, setup, and monitoring skills.
**What they're really testing:** Whether you understand CNC machining and its advantages.

### Q19. Heat treatment: annealing, normalizing, hardening, tempering. [H]
**A:** Annealing: heat to high temperature, slow cool in furnace - softens, relieves stress, improves ductility. Normalizing: heat to high temperature, cool in air - refines grain, improves strength. Hardening: heat to austenitizing temperature, quench in water/oil - increases hardness. Tempering: reheat hardened steel to 150-650 deg C - reduces brittleness, improves toughness. Sequence: anneal -> machine -> harden -> temper.
**Push:** Why is tempering needed after hardening? -> Hardening makes steel very hard but brittle. Tempering reduces brittleness by precipitating carbides and relieving residual stresses, improving toughness.
**Trap:** Saying tempering softens the steel - it reduces hardness slightly but primarily improves toughness and ductility.
**What they're really testing:** Whether you understand heat treatment processes and their purposes.

### Q20. Heat treatment: case hardening. [M]
**A:** Case hardening: harden surface only, keep core tough. Methods: (1) Carburizing - add carbon to surface (850-950 deg C), then quench. (2) Nitriding - add nitrogen (500-550 deg C), no quench needed. (3) Cyaniding - carbon + nitrogen (800-870 deg C). (4) Induction hardening - surface heated by induction, then quenched. Used for: gears, shafts, bearings, cams - parts needing wear resistance on surface and toughness in core.
**Push:** What is the difference between carburizing and nitriding? -> Carburizing adds carbon, requires quenching, higher temperature. Nitriding adds nitrogen, no quench needed, lower temperature, less distortion.
**Trap:** Thinking case hardening hardens the entire part - only the surface (case) is hardened, core remains tough.
**What they're really testing:** Whether you understand case hardening methods and applications.

## 3. Welding - 15 questions

### Q21. Welding processes: SMAW, GMAW, GTAW, SAW. [H]
**A:** SMAW (Shielded Metal Arc Welding): electrode with flux coating, manual, versatile, portable. GMAW (Gas Metal Arc Welding/MIG): continuous wire electrode with shielding gas, semi-automatic, high deposition. GTAW (Gas Tungsten Arc Welding/TIG): non-consumable tungsten electrode with shielding gas, precise, clean, for thin materials and exotic alloys. SAW (Submerged Arc Welding): granular flux covers arc, high deposition, automatic, for thick plates. Selection based on: material, thickness, position, quality requirement, production volume.
**Push:** When would you use TIG instead of MIG? -> For thin materials, exotic alloys (stainless, aluminium, titanium), and when highest quality is needed. MIG is faster for thicker materials and production work.
**Trap:** Saying MIG is always better than TIG - MIG is faster but TIG gives better quality and control.
**What they're really testing:** Whether you know welding processes and can select the right one.

### Q22. Welding defects. [H]
**A:** Common welding defects: (1) Porosity (gas pockets), (2) Slag inclusions (trapped flux), (3) Lack of fusion (incomplete bonding), (4) Lack of penetration (insufficient depth), (5) Undercut (groove at weld toe), (6) Cracks (hot or cold), (7) Distortion (warping), (8) Spatter (molten metal droplets). Causes: improper technique, wrong parameters, poor preparation, contamination. Prevention: proper WPS (Welding Procedure Specification), qualified welders, preheat, post-weld heat treatment.
**Push:** What is the difference between hot cracking and cold cracking? -> Hot cracking: occurs at high temperature during solidification (intergranular). Cold cracking: occurs after cooling, in HAZ, due to hydrogen and stress.
**Trap:** Saying all cracks are the same - hot and cold cracking have different causes and prevention methods.
**What they're really testing:** Whether you can identify welding defects and their causes.

### Q23. Heat affected zone (HAZ). [H]
**A:** HAZ is the region of base metal that is heated but not melted during welding. Microstructure changes due to thermal cycle: (1) Grain growth (high temperature), (2) Phase transformation (austenite formation in steel), (3) Hardening (if quenched by surrounding cold metal). HAZ properties: often harder and more brittle than base metal. Can cause: (a) HAZ cracking, (b) reduced toughness, (c) residual stresses. Mitigation: preheat, control heat input, PWHT.
**Push:** Why is HAZ a concern in welding? -> HAZ can be harder and more brittle than base metal, leading to cracking under load or residual stress.
**Trap:** Thinking HAZ is part of the weld metal - HAZ is base metal that was heated, not melted.
**What they're really testing:** Whether you understand HAZ and its effects on weld quality.

### Q24. Welding parameters: voltage, current, speed, travel angle. [M]
**A:** Welding parameters: (1) Current (A) - higher current = more heat, deeper penetration. (2) Voltage (V) - higher voltage = wider arc, wider bead. (3) Travel speed (mm/min) - slower = more heat input, wider bead. (4) Heat input = (V*I*60)/(speed*1000) kJ/mm. (5) Travel angle - push (forehand) for shallow penetration, drag (backhand) for deep penetration. (6) Contact tip to work distance (CTWD) - affects current in GMAW.
**Push:** What is heat input and why does it matter? -> Heat input = V*I/speed. It determines cooling rate, which affects microstructure and mechanical properties. Too high = coarse grains, low toughness. Too low = lack of fusion.
**Trap:** Thinking higher current always means better weld - excessive current causes burn-through and distortion.
**What they're really testing:** Whether you can control welding parameters and understand heat input.

### Q25. Preheat and post-weld heat treatment (PWHT). [M]
**A:** Preheat: heating base metal before welding. Purpose: (1) Slow cooling rate (prevents hard HAZ), (2) Reduce residual stress, (3) Drive off moisture (prevents hydrogen cracking). Temperature depends on: material, thickness, hydrogen content. PWHT: heating after welding. Purpose: (1) Relieve residual stresses, (2) Temper hard HAZ (improve toughness), (3) Reduce hydrogen content. Common PWHT: stress relief at 600-650 deg C for carbon steel.
**Push:** When is preheat required? -> For thick sections, high carbon/hydrogen content, low ambient temperature, and high-strength steels. Prevents cold cracking.
**Trap:** Skipping preheat on thick high-carbon steel - leads to cold cracking in HAZ.
**What they're really testing:** Whether you understand preheat and PWHT and when to apply them.

### Q26. Welding positions: 1G, 2G, 3G, 4G. [M]
**A:** Welding positions: (1) Flat (1G) - easiest, highest deposition. (2) Horizontal (2G) - moderate difficulty. (3) Vertical (3G) - challenging, requires technique. (4) Overhead (4G) - most difficult, highest skill. Position affects: penetration, bead shape, defect likelihood. Qualification tests are done in specific positions - a welder qualified in 3G can weld in all positions.
**Push:** Why is overhead welding the most difficult? -> Gravity pulls molten metal down, making it hard to control bead shape and avoid sagging/dripping.
**Trap:** Thinking position doesn't matter - overhead welding has much higher defect rates than flat welding.
**What they're really testing:** Whether you know welding positions and their difficulty levels.

### Q27. Welding inspection and qualification. [M]
**A:** Welding inspection: (1) Visual inspection (VT) - surface defects, dimensions. (2) NDT - RT, UT, MT, PT for internal defects. (3) Destructive testing - tensile, bend, impact, macro/micro examination. Qualification: WPS (Welding Procedure Specification) - procedure qualification record (PQR) validates WPS. Welder qualification: welder performance qualification (WPQ) - welder demonstrates skill in specific process, position, and material.
**Push:** What is the difference between WPS and PQR? -> WPS is the written procedure for welding. PQR is the record of actual test results that validate the WPS.
**Trap:** Confusing WPS with welder qualification - WPS qualifies the procedure, WPQ qualifies the welder.
**What they're really testing:** Whether you understand welding qualification and inspection.

### Q28. Welding of stainless steel. [M]
**A:** Stainless steel welding: (1) Use low heat input to minimize HAZ and sensitization. (2) Use correct filler metal (matching or over-alloyed). (3) Control interpass temperature (< 150 deg C for austenitic). (4) Avoid contamination (clean tools, separate from carbon steel). (5) Post-weld cleaning (remove heat tint, passivation). Sensitization: chromium carbide precipitation in HAZ at 450-850 deg C reduces corrosion resistance. Prevention: low carbon (304L, 316L) or stabilized grades (321, 347).
**Push:** What is sensitization in stainless steel welding? -> Chromium carbide precipitates at grain boundaries in HAZ, depleting chromium and reducing corrosion resistance. Occurs at 450-850 deg C.
**Trap:** Welding stainless steel with carbon steel tools - causes contamination and reduces corrosion resistance.
**What they're really testing:** Whether you understand stainless steel welding challenges.

### Q29. Welding of aluminium. [M]
**A:** Aluminium welding: (1) High thermal conductivity - needs higher heat input. (2) Oxide layer (Al2O3) - must be removed (wire brush, chemical). (3) Low melting point - risk of burn-through. (4) High thermal expansion - distortion risk. (5) No color change - hard to judge temperature. Process: GTAW (TIG) preferred for thin sections, GMAW (MIG) for thicker. Filler: 4043 or 5356. Shielding gas: argon (or argon-helium mix).
**Push:** Why is aluminium welding more difficult than steel? -> Aluminium has high thermal conductivity (heat dissipates quickly), oxide layer (high melting point, must be removed), and no color change (can't judge temperature by eye).
**Trap:** Not removing oxide layer before welding - causes lack of fusion and porosity.
**What they're really testing:** Whether you understand aluminium welding challenges.

### Q30. Submerged arc welding (SAW) advantages. [M]
**A:** SAW advantages: (1) High deposition rate (2-10x SMAW), (2) Deep penetration, (3) No spatter, (4) No arc radiation (flux covers arc), (5) Automatic (less skill required), (6) Excellent for thick plates. Disadvantages: (1) Only flat/horizontal position, (2) Flux handling required, (3) Not for thin materials (< 5 mm), (4) Slag removal needed. Used for: pressure vessels, shipbuilding, structural steel, pipe welding.
**Push:** Why is SAW limited to flat/horizontal position? -> The granular flux would fall off in vertical/overhead positions, exposing the arc and causing defects.
**Trap:** Using SAW for thin materials or out-of-position welding - causes burn-through and flux loss.
**What they're really testing:** Whether you know SAW advantages and limitations.

### Q31. Friction stir welding. [M]
**A:** Friction stir welding (FSW): solid-state welding where a rotating tool (shoulder + pin) is plunged into joint and traversed. Heat from friction plasticizes metal, tool stirs and consolidates it. Advantages: no melting (no solidification defects), low distortion, excellent mechanical properties, can weld dissimilar metals. Used for: aluminium alloys, especially in aerospace and automotive.
**Push:** Why is FSW good for aluminium? -> Aluminium has high thermal conductivity and oxide layer, making fusion welding difficult. FSW is solid-state, avoiding these issues.
**Trap:** Thinking FSW uses filler metal - it's a solid-state process, no filler or shielding gas needed.
**What they're really testing:** Whether you understand FSW as a solid-state welding process.

### Q32. Welding residual stresses and distortion. [M]
**A:** Welding residual stresses: tensile in weld and HAZ, compressive in base metal. Caused by: thermal expansion/contraction, phase transformation. Distortion: (1) Longitudinal shrinkage (along weld), (2) Transverse shrinkage (perpendicular to weld), (3) Angular distortion (rotation of parts). Mitigation: (1) Preheat, (2) Balanced welding (weld both sides), (3) Clamping/fixtures, (4) Peening (compressive surface stress), (5) PWHT.
**Push:** Why does welding cause distortion? -> Metal expands when heated and contracts when cooled. The weld and HAZ contract more than the base metal, pulling the part out of shape.
**Trap:** Saying distortion is unavoidable - proper technique and fixtures can minimize it significantly.
**What they're really testing:** Whether you understand welding residual stresses and distortion.

### Q33. Welding of cast iron. [L]
**A:** Cast iron welding: (1) Preheat (300-600 deg C) to slow cooling and prevent cracking. (2) Use nickel-based filler (Ni-Fe or pure Ni) - matches cast iron properties. (3) Low heat input, short welds. (4) Post-weld slow cooling (cover with insulation). (5) May need PWHT. Challenges: high carbon content (hard, brittle HAZ), graphite flakes (weak), thermal shock. Grey cast iron is easier to weld than white cast iron.
**Push:** Why is cast iron difficult to weld? -> High carbon content causes hard, brittle HAZ that cracks easily. Graphite flakes act as stress concentrators.
**Trap:** Welding cast iron without preheat - causes cracking in HAZ.
**What they're really testing:** Whether you understand cast iron welding challenges.

### Q34. Welding dissimilar metals. [M]
**A:** Dissimilar metal welding: (1) Select filler metal compatible with both base metals. (2) Consider melting point difference - weld the lower melting point metal first. (3) Control dilution - limit base metal mixing in weld. (4) Consider thermal expansion mismatch - can cause cracking. (5) Use buttering - deposit compatible layer on one base metal before welding to the other. Common: steel to stainless (use 309 filler), steel to aluminium (not directly weldable, use mechanical fastening or transition inserts).
**Push:** Can you weld steel directly to aluminium? -> No, they form brittle intermetallics. Use mechanical fastening, brazing, or transition inserts (explosion-bonded Al-steel).
**Trap:** Attempting to fusion weld steel to aluminium - creates brittle intermetallic compounds.
**What they're really testing:** Whether you understand dissimilar metal welding challenges.

### Q35. Brazing and soldering. [M]
**A:** Brazing: joining with filler metal (brass, silver) that melts above 450 deg C but below base metal melting point. Capillary action draws filler into joint. Advantages: joins dissimilar metals, less distortion, good for thin sections. Soldering: filler metal (tin-lead, lead-free) melts below 450 deg C. Used for electronics, plumbing. Both are not fusion welding - base metal doesn't melt.
**Push:** What is the difference between brazing and soldering? -> Temperature: brazing > 450 deg C, soldering < 450 deg C. Brazing uses brass/silver filler, soldering uses tin-lead/lead-free filler.
**Trap:** Calling brazing a type of welding - brazing doesn't melt base metal, welding does.
**What they're really testing:** Whether you can distinguish brazing, soldering, and welding.

## 4. NDT - 10 questions

### Q36. NDT methods overview. [H]
**A:** NDT (Non-Destructive Testing) methods: (1) Visual Testing (VT) - surface defects, cheapest. (2) Liquid Penetrant Testing (PT) - surface defects in non-porous materials. (3) Magnetic Particle Testing (MT) - surface/subsurface defects in ferromagnetic materials. (4) Radiographic Testing (RT) - internal defects, uses X-rays/gamma rays. (5) Ultrasonic Testing (UT) - internal defects, uses sound waves. (6) Eddy Current Testing (ET) - surface/near-surface defects in conductive materials. Selection based on: material, defect type, location, geometry, cost.
**Push:** Which NDT method is best for internal defects in steel? -> RT or UT. RT gives permanent record (radiograph), UT is faster and can detect smaller defects.
**Trap:** Thinking NDT can detect all defects - each method has limitations in material, defect type, and location.
**What they're really testing:** Whether you know NDT methods and can select the right one.

### Q37. Liquid penetrant testing (PT). [H]
**A:** PT (dye penetrant): (1) Clean surface, (2) Apply penetrant (dye or fluorescent), (3) Dwell time (capillary action draws penetrant into defects), (4) Remove excess penetrant, (5) Apply developer (draws penetrant out of defects, making them visible), (6) Inspect. Detects: surface-breaking defects (cracks, porosity, laps). Materials: non-porous (metals, ceramics, plastics). Not for: porous materials (cast iron with porosity), very rough surfaces.
**Push:** Why can't PT be used on porous materials? -> Porous materials absorb penetrant, causing false indications and making defect detection impossible.
**Trap:** Applying PT to cast iron - porosity causes false indications; use MT instead.
**What they're really testing:** Whether you understand PT principle and limitations.

### Q38. Magnetic particle testing (MT). [H]
**A:** MT: (1) Magnetize part, (2) Apply magnetic particles (iron powder, wet or dry), (3) Particles accumulate at defect locations (flux leakage), (4) Inspect under UV light (fluorescent) or white light (visible). Detects: surface and near-surface defects in ferromagnetic materials (iron, steel, nickel, cobalt). Not for: non-ferromagnetic materials (aluminium, copper, austenitic stainless).
**Push:** Why is MT limited to ferromagnetic materials? -> MT relies on magnetic flux leakage at defects, which only occurs in ferromagnetic materials.
**Trap:** Using MT on austenitic stainless steel - it's non-ferromagnetic, so MT won't work.
**What they're really testing:** Whether you understand MT principle and limitations.

### Q39. Radiographic testing (RT). [H]
**A:** RT: X-rays or gamma rays pass through material, defects absorb less radiation (appear darker on film). Detects: internal defects (porosity, inclusions, cracks, lack of fusion). Advantages: permanent record, can inspect complex shapes, detects volumetric defects. Disadvantages: radiation hazard, requires access to both sides, poor for planar defects (cracks parallel to beam), expensive. Sensitivity: depends on defect size and orientation.
**Push:** Why is RT poor at detecting cracks parallel to the radiation beam? -> Cracks parallel to beam have minimal thickness in the radiation path, so they absorb little radiation and are invisible on the radiograph.
**Trap:** Thinking RT can detect all defects - planar defects parallel to beam are nearly invisible.
**What they're really testing:** Whether you understand RT principle and limitations.

### Q40. Ultrasonic testing (UT). [H]
**A:** UT: high-frequency sound waves (1-25 MHz) transmitted into material, reflected from defects and back wall. Detects: internal defects (cracks, inclusions, porosity). Advantages: high sensitivity, can detect small defects, portable, no radiation hazard. Disadvantages: requires skilled operator, surface must be accessible, complex geometry difficult, no permanent record (unless phased array). Types: (1) Pulse-echo (single transducer), (2) Through-transmission (two transducers), (3) Phased array (multiple elements, beam steering).
**Push:** What is the difference between pulse-echo and through-transmission UT? -> Pulse-echo: single transducer sends and receives, detects defects by echo timing. Through-transmission: two transducers on opposite sides, detects defects by signal attenuation.
**Trap:** Saying UT can detect all defects - surface roughness, complex geometry, and coarse-grained materials can limit UT effectiveness.
**What they're really testing:** Whether you understand UT principle and can compare it to RT.

### Q41. Eddy current testing (ET). [M]
**A:** ET: alternating current in coil induces eddy currents in conductive material. Defects disrupt eddy currents, changing coil impedance. Detects: surface and near-surface defects (cracks, corrosion, thickness loss). Advantages: fast, no contact needed, can inspect through coatings, automated. Disadvantages: only conductive materials, limited depth (skin effect), sensitive to lift-off and material properties. Used for: aircraft inspection, tube inspection, weld inspection.
**Push:** What is the skin effect in eddy current testing? -> Eddy currents concentrate near the surface. Higher frequency = shallower penetration. Lower frequency = deeper penetration but lower sensitivity.
**Trap:** Using ET on non-conductive materials - ET requires electrical conductivity.
**What they're really testing:** Whether you understand ET principle and the skin effect.

### Q42. Acoustic emission testing (AE). [M]
**A:** AE: detects elastic waves (acoustic emission) generated by rapid release of energy in material (crack growth, phase transformation, plastic deformation). Passive NDT - monitors during loading or operation. Advantages: real-time monitoring, can detect active defects, covers large areas. Disadvantages: requires loading, can't detect static defects, complex signal analysis. Used for: pressure vessel monitoring, bridge inspection, composite structures.
**Push:** What is the difference between AE and UT? -> UT is active (transmits sound waves), AE is passive (listens for emissions). UT finds defects; AE finds active defect growth.
**Trap:** Thinking AE can find all defects - it only detects active defects under stress, not static defects.
**What they're really testing:** Whether you understand AE as a passive monitoring technique.

### Q43. Visual testing (VT). [M]
**A:** VT: visual examination of surface for defects, dimensions, and condition. Tools: naked eye, magnifying glass, borescope, fiberscope. Advantages: cheapest, fastest, no equipment needed. Limitations: only surface defects, depends on inspector skill, lighting conditions. Standard: requires adequate lighting (min 500 lux for general, 1000 lux for critical). VT is always the first NDT method applied.
**Push:** Why is VT always the first NDT method? -> It's the cheapest and fastest. Many defects are visible on surface, so VT can eliminate need for other NDT methods.
**Trap:** Skipping VT and going straight to expensive NDT - VT might find the defect without needing other methods.
**What they're really testing:** Whether you understand the role of visual testing in NDT.

### Q44. NDT selection for different materials. [M]
**A:** Material-based NDT selection: (1) Ferromagnetic steel: VT, PT, MT, RT, UT. (2) Non-ferromagnetic (Al, Cu, austenitic SS): VT, PT, RT, UT, ET. (3) Ceramics: VT, PT, RT. (4) Composites: VT, UT, AE, thermography. (5) Welds: VT, PT, MT/ET, RT, UT. Selection also depends on: defect type (surface vs internal), geometry, access, cost, and required sensitivity.
**Push:** How do you select NDT for a welded steel pressure vessel? -> VT (surface), RT or UT (internal), PT/MT (surface cracks). RT for volumetric defects, UT for planar defects.
**Trap:** Using only one NDT method - different methods detect different defect types; use complementary methods.
**What they're really testing:** Whether you can select appropriate NDT methods for given materials and applications.

### Q45. NDT for welds. [M]
**A:** Weld NDT: (1) VT - surface defects, dimensions, weld profile. (2) PT/MT - surface cracks (PT for all materials, MT for ferromagnetic). (3) RT - internal volumetric defects (porosity, inclusions). (4) UT - internal planar defects (cracks, lack of fusion). (5) PAUT (Phased Array UT) - advanced, beam steering, better coverage. (6) TOFD (Time of Flight Diffraction) - high sensitivity for cracks. Code requirements: ASME, AWS, ISO specify acceptance criteria.
**Push:** Why is UT preferred over RT for detecting lack of fusion? -> Lack of fusion is a planar defect parallel to the weld, which RT struggles to detect. UT can detect it regardless of orientation (with proper scanning).
**Trap:** Relying only on RT for weld inspection - planar defects like lack of fusion can be missed.
**What they're really testing:** Whether you can select NDT methods for weld inspection.

## 5. Metrology and Tolerances - 5 questions

### Q46. GD&T: form tolerances. [H]
**A:** Form tolerances control the shape of a feature: (1) Straightness - line element straight. (2) Flatness - surface flat. (3) Circularity (roundness) - circular cross-section. (4) Cylindricity - cylindrical surface. Form tolerances are applied to individual features, not relative to datums. They are the most fundamental level of geometric control.
**Push:** What is the difference between flatness and parallelism? -> Flatness controls a single surface's flatness. Parallelism controls the relationship between two surfaces (one relative to a datum).
**Trap:** Using form tolerances when you need location tolerances - form tolerances don't control position or orientation.
**What they're really testing:** Whether you understand form tolerances in GD&T.

### Q47. GD&T: orientation and location tolerances. [H]
**A:** Orientation tolerances: (1) Angularity - angle relative to datum. (2) Perpendicularity - 90 deg to datum. (3) Parallelism - parallel to datum. Location tolerances: (1) Position - location of features (holes, pins) relative to datums. (2) Concentricity - axis of feature relative to datum axis. (3) Symmetry - center plane relative to datum. Position tolerance is the most commonly used location tolerance.
**Push:** What is the difference between position and concentricity? -> Position controls the location of a feature's axis/center point. Concentricity controls the relationship between axes of two features.
**Trap:** Using concentricity when position is sufficient - concentricity is harder to measure and rarely needed.
**What they're really testing:** Whether you understand orientation and location tolerances.

### Q48. MMC and LMC concepts. [H]
**A:** MMC (Maximum Material Condition): state where feature has most material (largest pin, smallest hole). LMC (Least Material Condition): state where feature has least material (smallest pin, largest hole). RFS (Regardless of Feature Size): tolerance applies regardless of feature size. Bonus tolerance: when feature departs from MMC, additional tolerance is allowed (only for MMC-modified tolerances). Used in: functional gauging, interchangeability.
**Push:** Why is MMC used for position tolerance of holes? -> Because at MMC (smallest hole), the hole has least clearance for the mating pin. If the hole is larger (departing from MMC), more tolerance is allowed (bonus tolerance).
**Trap:** Confusing MMC with LMC - MMC = most material, LMC = least material. For a hole, MMC is smallest diameter.
**What they're really testing:** Whether you understand MMC, LMC, and bonus tolerance.

### Q49. Tolerance stack-up analysis. [M]
**A:** Tolerance stack-up: summing tolerances in an assembly to ensure fit and function. Methods: (1) Worst-case: sum of all tolerances (conservative, guarantees fit). (2) Statistical (RSS): sqrt(sum of squares) - less conservative, assumes normal distribution. (3) Monte Carlo: simulation with random variation. Worst-case for safety-critical, RSS for high-volume production, Monte Carlo for complex assemblies.
**Push:** When would you use worst-case vs RSS? -> Worst-case for safety-critical or low-volume. RSS for high-volume where statistical variation applies. RSS gives tighter tolerances (less cost).
**Trap:** Using RSS for safety-critical assemblies - RSS allows some assemblies to fail; worst-case guarantees all fit.
**What they're really testing:** Whether you can perform tolerance stack-up analysis.

### Q50. Surface finish and roughness parameters. [M]
**A:** Surface finish: (1) Ra (arithmetic average roughness) - most common. (2) Rz (average maximum height) - peak-to-valley. (3) Rq (RMS roughness). (4) Rt (total height). Measurement: (1) Contact (stylus profilometer), (2) Non-contact (optical, interferometric). Surface finish affects: friction, wear, sealing, fatigue, corrosion. Typical values: machined surfaces Ra 0.8-6.3 microns, ground surfaces Ra 0.1-0.8 microns, polished Ra < 0.1 microns.
**Push:** What is the difference between Ra and Rz? -> Ra is the arithmetic average of absolute deviations from mean line. Rz is the average of five highest peaks and five lowest valleys. Rz is more sensitive to occasional large peaks/valleys.
**Trap:** Specifying Ra when Rz is more appropriate - Ra can hide occasional large defects that Rz would catch.
**What they're really testing:** Whether you understand surface finish parameters and can specify them.

## File Statistics

**Total questions: 50**

**By tag:**
- [H] High-yield: ~18 questions
- [M] Medium-yield: ~28 questions
- [L] Occasional: ~4 questions

**By section:**
- Casting: 10 questions
- Forming and machining: 10 questions
- Welding: 15 questions
- NDT: 10 questions
- Metrology and tolerances: 5 questions

**Standard values used consistently:** g=9.81, pi=3.1416, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers Manufacturing, Welding, and NDT - essential for automobiles, petrochem, and construction interviews.