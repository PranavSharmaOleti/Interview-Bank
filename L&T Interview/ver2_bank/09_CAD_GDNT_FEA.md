# CAD, GD&T, and FEA - Core Interview Bank

**Part 9 of 10 | 50 questions | CAD fundamentals, GD&T characteristics, datums, MMC/LMC/RFS, tolerance stack-up, FEA workflow, element types, boundary conditions, stress interpretation**

*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. CAD Fundamentals - 10 questions

### Q1. Parametric vs direct modeling. [H]
**A:** Parametric (history-based): features are defined by parameters and relationships, changes propagate through the model. Direct modeling: geometry is edited directly without feature history. Parametric is better for design iteration and family of parts. Direct is faster for simple edits and imported geometry. Modern CAD (Creo, SolidWorks, CATIA) supports both.
**Push:** When would you use direct modeling? -> For quick edits to imported geometry, or when you don't need parametric relationships (e.g., modifying a supplier's part).
**Trap:** Saying parametric is always better - direct modeling is faster for simple edits and doesn't require understanding the feature tree.
**What they're really testing:** Whether you understand CAD modeling approaches and can select the right one.

### Q2. Solid modeling vs surface modeling. [H]
**A:** Solid modeling: represents volume (mass, weight, inertia). Surface modeling: represents only surfaces (no volume). Solid for mechanical parts (shafts, brackets, housings). Surface for complex shapes (car bodies, aircraft, consumer products). Solid can be converted to surface (extract faces), but surface to solid requires closing all gaps (stitching).
**Push:** Why use surface modeling for car bodies? -> Because car bodies have complex, free-form shapes that are easier to create with surfaces than with solid features.
**Trap:** Thinking surface models can calculate mass properties - they can't; you need a solid model for mass, weight, and inertia.
**What they're really testing:** Whether you can distinguish solid and surface modeling and know when to use each.

### Q3. Feature-based modeling: extrude, revolve, sweep, loft. [H]
**A:** Extrude: linear extrusion of a sketch along a direction. Revolve: rotation of a sketch about an axis. Sweep: profile swept along a path. Loft: blend between multiple profiles. Extrude for prismatic parts, revolve for axisymmetric parts (shafts, vessels), sweep for pipes and wires, loft for complex transitions (turbine blades, ducts).
**Push:** When would you use loft instead of sweep? -> When you need to blend between different cross-sections (e.g., circular to rectangular transition in a duct).
**Trap:** Using extrude for a part that needs a curved feature - extrude only creates straight features.
**What they're really testing:** Whether you can select the right feature type for given geometry.

### Q4. Assembly modeling: constraints, mates, degrees of freedom. [H]
**A:** Assembly constraints (mates) define how parts fit together: (1) Coincident (faces touch), (2) Concentric (axes align), (3) Distance (offset between faces), (4) Angle (angle between faces), (5) Parallel, (6) Perpendicular. Each mate removes degrees of freedom. A fully constrained part has 0 DOF. Over-constraining causes conflicts; under-constraining allows unwanted motion.
**Push:** How many DOF does a part have in 3D space? -> 6 DOF (3 translational + 3 rotational). Each mate removes 1 or more DOF.
**Trap:** Over-constraining an assembly - leads to conflicts and unstable models.
**What they're really testing:** Whether you understand assembly constraints and DOF.

### Q5. Drawings: views, dimensions, tolerances. [H]
**A:** Engineering drawing: (1) Views (orthographic: front, top, side; isometric for visualization). (2) Dimensions (size and location). (3) Tolerances (acceptable variation). (4) Notes (material, finish, heat treatment). (5) Title block (part name, number, scale, date). Standards: ASME Y14.5 (GD&T), ISO 128 (drawing), ISO 2768 (general tolerances).
**Push:** What is the difference between a detail drawing and an assembly drawing? -> Detail drawing shows one part with all dimensions. Assembly drawing shows how parts fit together, with balloons and BOM.
**Trap:** Putting too many dimensions on a drawing - leads to over-constraining and conflicting tolerances.
**What they're really testing:** Whether you understand engineering drawing standards and content.

### Q6. CAD file formats: native vs neutral. [M]
**A:** Native formats: .sldprt (SolidWorks), .prt (Creo), .CATPart (CATIA) - preserve full feature history. Neutral formats: STEP (.stp), IGES (.igs), STL (.stl) - geometry only, no feature history. STEP is the most common neutral format for solid geometry. STL is for 3D printing (triangulated surface). Use STEP for data exchange, native for design work.
**Push:** Why use STEP instead of native format for data exchange? -> STEP is vendor-neutral and can be read by any CAD system. Native formats require the same software.
**Trap:** Sending native CAD files to a supplier using different software - they can't open them.
**What they're really testing:** Whether you know CAD file formats and when to use each.

### Q7. Top-down vs bottom-up assembly design. [M]
**A:** Bottom-up: design parts independently, then assemble. Top-down: design assembly first, then create parts in context (in-place features). Top-down is better for complex assemblies where part geometry depends on assembly constraints. Bottom-up is better for standard parts and purchased components.
**Push:** When would you use top-down design? -> When part geometry depends on assembly constraints (e.g., a bracket that must fit between two existing parts).
**Trap:** Always using bottom-up - top-down is essential for complex, interdependent assemblies.
**What they're really testing:** Whether you understand assembly design approaches.

### Q8. Configuration management in CAD. [M]
**A:** Configuration: multiple variations of a part/assembly in one file (e.g., different sizes, materials, or features). Uses: (1) Design tables (Excel-driven), (2) Family tables (Creo), (3) Configurations (SolidWorks). Advantages: single file for variants, easy comparison, reduced file count. Used for: standard parts with sizes, assemblies with optional components.
**Push:** What is a design table? -> An Excel spreadsheet that drives part/assembly configurations by changing parameters (dimensions, features) for each row.
**Trap:** Creating separate files for each variant - configurations are more efficient and maintainable.
**What they're really testing:** Whether you understand CAD configuration management.

### Q9. CAD data management: PDM/PLM. [M]
**A:** PDM (Product Data Management): manages CAD files, versions, and revisions. PLM (Product Lifecycle Management): broader, manages entire product lifecycle (design, manufacturing, service). Features: version control, check-in/check-out, BOM management, change orders. Examples: Windchill (PTC), Teamcenter (Siemens), 3DEXPERIENCE (Dassault). Prevents: lost files, version conflicts, unauthorized changes.
**Push:** Why is PDM essential for engineering teams? -> It prevents version conflicts, ensures everyone uses the latest design, and maintains audit trail of changes.
**Trap:** Using shared network drives instead of PDM - leads to version conflicts and lost work.
**What they're really testing:** Whether you understand CAD data management.

### Q10. 3D printing: technologies and applications. [M]
**A:** 3D printing (additive manufacturing): builds parts layer by layer. Technologies: (1) FDM (Fused Deposition Modeling) - thermoplastic filament, cheapest. (2) SLA (Stereolithography) - photopolymer resin, high resolution. (3) SLS (Selective Laser Sintering) - powder, no support needed. (4) Metal (SLM, DMLS) - metal powder, for functional parts. Applications: prototyping, tooling, end-use parts, medical implants, aerospace components.
**Push:** When would you use 3D printing instead of machining? -> For complex geometries (internal channels, lattice structures), low volume, rapid prototyping, or when tooling cost is prohibitive.
**Trap:** Thinking 3D printing replaces all manufacturing - it's best for complex, low-volume parts; machining is better for simple, high-volume parts.
**What they're really testing:** Whether you understand 3D printing technologies and applications.

## 2. GD&T - 15 questions

### Q11. GD&T overview and purpose. [H]
**A:** GD&T (Geometric Dimensioning and Tolerancing): ASME Y14.5 standard for defining and communicating engineering tolerances. Purpose: (1) Ensure fit and function, (2) Allow more tolerance where possible (reduce cost), (3) Provide clear, unambiguous tolerance specification. Uses feature control frames (FCF) with symbols, datums, and tolerance values. Replaces older coordinate dimensioning (plus/minus tolerancing).
**Push:** Why is GD&T better than plus/minus tolerancing? -> GD&T defines the tolerance zone (not just size), allows bonus tolerance (MMC), and relates features to datums (functional relationships).
**Trap:** Thinking GD&T is just another way to specify tolerances - it fundamentally changes how tolerances are interpreted and applied.
**What they're really testing:** Whether you understand GD&T purpose and advantages.

### Q12. Datums: definition and selection. [H]
**A:** Datum: theoretically exact point, axis, or plane used as reference for tolerance specification. Datum selection: (1) Functional surfaces (mating surfaces, bearing surfaces), (2) Stable, repeatable features, (3) Avoid small or flexible features. Datum hierarchy: primary (3 point contact), secondary (2 point contact), tertiary (1 point contact). Datum reference frame: 3-2-1 principle (3 points on primary, 2 on secondary, 1 on tertiary).
**Push:** What is the 3-2-1 principle? -> Primary datum: 3 points (constrains 3 DOF), secondary: 2 points (constrains 2 DOF), tertiary: 1 point (constrains 1 DOF). Total 6 DOF constrained.
**Trap:** Selecting datums based on manufacturing convenience instead of function - leads to wrong tolerance interpretation.
**What they're really testing:** Whether you understand datum selection and the 3-2-1 principle.

### Q13. Form tolerances: straightness, flatness, circularity, cylindricity. [H]
**A:** Form tolerances (no datum required): (1) Straightness - line element must lie within tolerance zone (two parallel lines). (2) Flatness - surface must lie within two parallel planes. (3) Circularity (roundness) - circular cross-section must lie within two concentric circles. (4) Cylindricity - cylindrical surface must lie within two concentric cylinders. These control shape only, not size or location.
**Push:** What is the difference between circularity and cylindricity? -> Circularity controls a single cross-section (2D). Cylindricity controls the entire cylindrical surface (3D).
**Trap:** Applying form tolerances when location tolerances are needed - form tolerances don't control position.
**What they're really testing:** Whether you know form tolerances and their application.

### Q14. Orientation tolerances: angularity, perpendicularity, parallelism. [H]
**A:** Orientation tolerances (require datum): (1) Angularity - feature must be within tolerance zone at specified angle to datum. (2) Perpendicularity - feature must be within tolerance zone perpendicular to datum (90 deg). (3) Parallelism - feature must be within tolerance zone parallel to datum. Tolerance zone: two parallel planes (for surfaces) or cylindrical zone (for axes).
**Push:** What is the difference between perpendicularity and angularity? -> Perpendicularity is a special case of angularity at 90 deg. Both use the same tolerance zone concept.
**Trap:** Using orientation tolerances without a datum - orientation tolerances always require a datum reference.
**What they're really testing:** Whether you understand orientation tolerances.

### Q15. Location tolerances: position, concentricity, symmetry. [H]
**A:** Location tolerances (require datum): (1) Position - feature (hole, pin) must lie within tolerance zone relative to datums. Most common and useful location tolerance. (2) Concentricity - axis of feature must coincide with datum axis (rarely used, hard to measure). (3) Symmetry - center plane of feature must coincide with datum center plane. Position tolerance is preferred over concentricity for most applications.
**Push:** Why is position preferred over concentricity? -> Position controls both location and size (with MMC), is easier to measure, and better represents functional requirements.
**Trap:** Using concentricity when position is sufficient - concentricity is harder to measure and rarely needed.
**What they're really testing:** Whether you understand location tolerances and when to use each.

### Q16. Profile tolerances: profile of a line, profile of a surface. [M]
**A:** Profile tolerances (can use datum or not): (1) Profile of a line - 2D cross-section must lie within tolerance zone. (2) Profile of a surface - 3D surface must lie within tolerance zone. Can be bilateral (equal on both sides) or unilateral (all on one side). Used for: complex curves, airfoils, cam profiles, free-form surfaces. Most versatile GD&T tolerance.
**Push:** When would you use profile of a surface? -> For complex 3D surfaces (car bodies, turbine blades) where traditional tolerances (flatness, position) don't apply.
**Trap:** Thinking profile tolerances are only for 2D - profile of a surface controls 3D geometry.
**What they're really testing:** Whether you understand profile tolerances for complex geometry.

### Q17. Runout tolerances: circular runout, total runout. [M]
**A:** Runout tolerances (require datum axis): (1) Circular runout - single circular cross-section must stay within tolerance zone as part rotates 360 deg. (2) Total runout - entire surface must stay within tolerance zone as part rotates 360 deg. Detects: eccentricity, out-of-roundness, taper, wobble. Used for: rotating parts (shafts, gears, wheels) where runout affects vibration and balance.
**Push:** What is the difference between circular and total runout? -> Circular runout checks one cross-section at a time. Total runout checks the entire surface (accumulates all errors).
**Trap:** Using circular runout when total runout is needed - circular runout can miss axial errors (taper, wobble).
**What they're really testing:** Whether you understand runout tolerances for rotating parts.

### Q18. MMC, LMC, RFS modifiers. [H]
**A:** Modifiers: (1) MMC (Maximum Material Condition) - tolerance applies at MMC, bonus tolerance allowed as feature departs from MMC. (2) LMC (Least Material Condition) - tolerance applies at LMC, bonus tolerance allowed as feature departs from LMC. (3) RFS (Regardless of Feature Size) - tolerance applies regardless of feature size (no bonus tolerance). Default for position tolerance is MMC. Default for form tolerances is RFS.
**Push:** When would you use LMC instead of MMC? -> For internal features (holes) where minimum wall thickness is critical, or for features where maximum material removal is needed.
**Trap:** Applying MMC to form tolerances - form tolerances are always RFS (no bonus tolerance).
**What they're really testing:** Whether you understand modifiers and their application.

### Q19. Bonus tolerance. [H]
**A:** Bonus tolerance: additional tolerance allowed when a feature departs from MMC (or LMC). For a hole with position tolerance at MMC: if hole is larger than MMC (more clearance), position tolerance increases by the difference. Example: hole MMC = 10.0 mm, actual = 10.2 mm, position tolerance = 0.1 + 0.2 = 0.3 mm. Bonus tolerance allows functional gauging and reduces manufacturing cost.
**Push:** How is bonus tolerance calculated? -> Bonus = |actual size - MMC size|. Total tolerance = specified tolerance + bonus tolerance.
**Trap:** Applying bonus tolerance to RFS tolerances - RFS means no bonus tolerance regardless of size.
**What they're really testing:** Whether you can calculate bonus tolerance.

### Q20. Virtual condition and resultant condition. [M]
**A:** Virtual condition: worst-case boundary of a feature, used for gauging. For external feature (pin): virtual condition = MMC size + geometric tolerance. For internal feature (hole): virtual condition = MMC size - geometric tolerance. Resultant condition: opposite boundary (LMC + tolerance for external, LMC - tolerance for internal). Used for: functional gauging, ensuring assembly.
**Push:** What is the purpose of virtual condition? -> It defines the worst-case boundary that a mating part must clear. Used to design functional gauges.
**Trap:** Confusing virtual condition with actual feature size - virtual condition is a theoretical boundary, not a measurement.
**What they're really testing:** Whether you understand virtual condition for functional gauging.

### Q21. Tolerance stack-up: worst-case vs statistical. [M]
**A:** Worst-case stack-up: sum of all tolerances (max possible variation). Guarantees 100% fit but may be too conservative. Statistical (RSS) stack-up: sqrt(sum of squares) - assumes normal distribution, 99.73% fit (3 sigma). Monte Carlo: simulation with random variation for complex assemblies. Use worst-case for safety-critical, RSS for high-volume, Monte Carlo for complex.
**Push:** When would you use RSS instead of worst-case? -> For high-volume production where statistical variation applies and cost reduction is important. RSS gives tighter tolerances.
**Trap:** Using RSS for safety-critical assemblies - RSS allows some assemblies to fail; worst-case guarantees all fit.
**What they're really testing:** Whether you can perform tolerance stack-up analysis.

### Q22. GD&T for threaded features. [M]
**A:** Threaded features: pitch diameter is the controlling element. GD&T applied to: (1) Pitch diameter (position, concentricity), (2) Major/minor diameter (size tolerance). Thread form tolerance: (1) Lead (cumulative pitch error), (2) Flank angle, (3) Major/minor diameter. Standards: ASME B1.13M for metric threads, B1.1 for unified threads. Functional gauging: go/no-go gauges.
**Push:** What is the difference between pitch diameter and major diameter? -> Pitch diameter is the effective diameter for thread engagement. Major diameter is the outer diameter of external thread (or inner diameter of internal thread).
**Trap:** Applying GD&T to major diameter instead of pitch diameter - pitch diameter controls thread function.
**What they're really testing:** Whether you understand GD&T for threaded features.

### Q23. GD&T for gears. [M]
**A:** Gear GD&T: (1) Pitch diameter (runout, concentricity), (2) Tooth profile (profile tolerance), (3) Lead (helix angle tolerance for helical gears), (4) Index (spacing between teeth), (5) Backlash (clearance between mating teeth). Standards: AGMA 2015 for gear accuracy. Measurement: gear checker, CMM. Runout of pitch diameter is critical for noise and vibration.
**Push:** Why is pitch diameter runout important for gears? -> Pitch diameter runout causes variation in tooth engagement, leading to noise, vibration, and uneven wear.
**Trap:** Ignoring gear GD&T and relying only on size tolerances - gear function depends on geometric accuracy.
**What they're really testing:** Whether you understand GD&T for gears.

### Q24. GD&T for bearings and shafts. [M]
**A:** Bearing/shaft GD&T: (1) Diameter (size tolerance), (2) Roundness (circularity), (3) Cylindricity, (4) Runout (for rotating shafts), (5) Straightness (for shafts), (6) Perpendicularity (for shoulders). Bearing fit: (1) Clearance fit (shaft smaller than hole), (2) Interference fit (shaft larger than hole), (3) Transition fit. Fit selection based on: load, speed, temperature, mounting.
**Push:** What is the difference between clearance fit and interference fit? -> Clearance fit: shaft < hole (free rotation). Interference fit: shaft > hole (press fit, no movement).
**Trap:** Using interference fit for rotating shafts - causes seizure; use clearance fit with bearings.
**What they're really testing:** Whether you understand GD&T for bearings and shafts.

### Q25. GD&T inspection methods. [M]
**A:** GD&T inspection: (1) CMM (Coordinate Measuring Machine) - most versatile, can measure all geometric tolerances. (2) Functional gauges (go/no-go) - fast, for production. (3) Optical comparators - for 2D profiles. (4) Form testers (roundness, flatness machines) - for specific form tolerances. (5) Vision systems - for automated inspection. CMM is the gold standard for GD&T verification.
**Push:** Why is CMM preferred for GD&T inspection? -> CMM can measure all geometric tolerances (form, orientation, location, profile, runout) with high accuracy.
**Trap:** Using only size measurement (calipers, micrometers) for GD&T - size alone doesn't verify geometric tolerances.
**What they're really testing:** Whether you know GD&T inspection methods.

## 3. FEA - 15 questions

### Q26. FEA workflow. [H]
**A:** FEA workflow: (1) Pre-processing: geometry cleanup, meshing, material properties, boundary conditions, loads. (2) Solving: matrix assembly, equation solving, convergence check. (3) Post-processing: stress/strain/displacement plots, reaction forces, animation. Key steps: geometry simplification, mesh quality check, boundary condition verification, result validation.
**Push:** What is the most common source of FEA errors? -> Incorrect boundary conditions or loads, not mesh quality. Garbage in, garbage out.
**Trap:** Running FEA without verifying boundary conditions - leads to wrong results even with fine mesh.
**What they're really testing:** Whether you understand the FEA workflow and common pitfalls.

### Q27. Element types: 1D, 2D, 3D. [H]
**A:** 1D elements: beams, trusses, springs - for slender structures. 2D elements: shells, plates, membranes - for thin-walled structures (pressure vessels, car bodies). 3D elements: tetrahedra, hexahedra - for solid parts (brackets, housings). Selection based on: geometry (slender -> 1D, thin -> 2D, bulky -> 3D), accuracy required, and computational cost.
**Push:** When would you use 2D shell elements instead of 3D solid elements? -> For thin-walled structures (t < 10 mm) where through-thickness stress is negligible. Shells are faster and more accurate for thin parts.
**Trap:** Using 3D solids for thin plates - wastes computation and may give poor results (shear locking).
**What they're really testing:** Whether you can select the right element type for given geometry.

### Q28. Mesh quality: aspect ratio, skewness, Jacobian. [H]
**A:** Mesh quality metrics: (1) Aspect ratio - ratio of longest to shortest edge (should be < 5 for good quality). (2) Skewness - deviation from ideal shape (should be < 0.8). (3) Jacobian - measures element distortion (should be > 0.7). Poor mesh quality leads to: inaccurate results, convergence problems, artificial stiffness. Refine mesh where stress gradients are high (notches, holes).
**Push:** What happens if mesh has high aspect ratio? -> Element becomes too stiff in one direction, leading to inaccurate stress results (especially shear stress).
**Trap:** Making mesh uniformly fine - wastes computation; refine only where needed (stress concentrations).
**What they're really testing:** Whether you understand mesh quality and can improve it.

### Q29. Boundary conditions: fixed, pinned, roller, symmetry. [H]
**A:** Boundary conditions: (1) Fixed (encastre) - all 6 DOF constrained. (2) Pinned - translation constrained, rotation free. (3) Roller - one translation constrained, others free. (4) Symmetry - normal displacement = 0, in-plane rotations = 0. (5) Remote load - load applied at a point, transferred to surface. Proper BC selection is critical - wrong BC gives wrong results.
**Push:** When would you use symmetry boundary conditions? -> When geometry and loads are symmetric. Reduces model size by 50% (or more for multiple symmetries) and improves accuracy.
**Trap:** Applying fixed BC to a surface that should be free to rotate - over-constrains the model, giving artificially high stresses.
**What they're really testing:** Whether you can select and apply appropriate boundary conditions.

### Q30. Loads: point, pressure, thermal, inertia. [H]
**A:** Load types: (1) Point load - concentrated force at a point. (2) Pressure - distributed force on a surface. (3) Thermal - temperature change causing expansion/contraction. (4) Inertia - gravity, centrifugal, acceleration. (5) Remote load - load at a point, transferred to surface. Load application: (a) magnitude, (b) direction, (c) distribution. Always check reaction forces sum to applied loads.
**Push:** What is a remote load in FEA? -> A force/moment applied at a point (remote from the model), transferred to the surface through rigid or flexible connections. Used for bolted joints, lifting points.
**Trap:** Applying point load where pressure is more appropriate - point loads create stress singularities.
**What they're really testing:** Whether you can apply different load types correctly.

### Q31. Stress singularities. [H]
**A:** Stress singularity: stress approaches infinity at a point (sharp corner, point load, constraint point). In FEA, stress at singularity depends on mesh size - finer mesh gives higher stress. Not a real physical phenomenon - real materials have finite strength. Solutions: (1) Add fillet (radius), (2) Use average stress over a small area, (3) Use strain energy or force-based criteria instead of peak stress.
**Push:** Why does stress increase with mesh refinement at a sharp corner? -> Because the theoretical stress concentration factor is infinite at a sharp corner. Finer mesh approaches this theoretical value.
**Trap:** Reporting peak stress at a singularity as the design stress - it's mesh-dependent and not meaningful.
**What they're really testing:** Whether you understand stress singularities and how to handle them.

### Q32. Convergence: h-refinement vs p-refinement. [M]
**A:** Convergence: as mesh is refined, results approach the exact solution. h-refinement: reduce element size (h) while keeping element order same. p-refinement: increase element order (p) while keeping mesh same. h-refinement is more common and easier. Convergence check: compare results with different mesh sizes; if difference < 5%, mesh is adequate.
**Push:** How do you know when mesh is converged? -> Compare key results (max stress, displacement) between two mesh levels. If difference < 5%, mesh is converged.
**Trap:** Assuming finer mesh always gives better results - if boundary conditions are wrong, finer mesh gives wrong results faster.
**What they're really testing:** Whether you understand convergence and can verify mesh adequacy.

### Q33. Linear vs nonlinear FEA. [M]
**A:** Linear FEA: (1) Linear material (Hooke's law), (2) Small displacements (geometry doesn't change), (3) Linear contact (no separation). Nonlinear FEA: (1) Nonlinear material (plasticity, hyperelasticity), (2) Large displacements (geometry changes significantly), (3) Contact (separation, sliding, friction). Nonlinear requires iterative solving and is more computationally expensive.
**Push:** When do you need nonlinear FEA? -> When: (1) Material yields (plastic deformation), (2) Large displacements (buckling, rubber parts), (3) Contact between parts (bolted joints, gears).
**Trap:** Using linear FEA for large displacement problems - gives wrong results (stiffness changes with deformation).
**What they're really testing:** Whether you can distinguish linear and nonlinear FEA.

### Q34. Contact analysis. [M]
**A:** Contact in FEA: interaction between surfaces. Types: (1) Bonded - surfaces glued together (no separation). (2) No-separation - surfaces can slide but not separate. (3) Frictionless - surfaces can separate and slide without friction. (4) Frictional - surfaces can separate and slide with friction. Contact formulation: (a) Penalty method (springs between surfaces), (b) Lagrange multiplier (exact constraint). Convergence can be difficult with contact.
**Push:** Why is contact analysis difficult in FEA? -> Because contact status (open/closed, sliding/sticking) changes during loading, requiring iterative solving and small load steps.
**Trap:** Using bonded contact for parts that should separate - gives artificially stiff results.
**What they're really testing:** Whether you understand contact analysis in FEA.

### Q35. Modal analysis. [M]
**A:** Modal analysis: finds natural frequencies and mode shapes of a structure. Output: (1) Natural frequencies (Hz), (2) Mode shapes (deformation patterns), (3) Modal mass participation. Used for: vibration analysis, avoiding resonance, dynamic design. Does not include damping or external loads. Pre-stress (from static analysis) can affect natural frequencies.
**Push:** What is modal mass participation? -> Fraction of total mass participating in each mode. Sum of all modal mass participations = 100% (for complete model).
**Trap:** Thinking modal analysis includes damping - it doesn't; damping is added in harmonic or transient analysis.
**What they're really testing:** Whether you understand modal analysis and its output.

### Q36. Harmonic analysis. [M]
**A:** Harmonic analysis: finds steady-state response to sinusoidal loading at various frequencies. Output: (1) Displacement/velocity/acceleration vs frequency, (2) Stress vs frequency. Used for: (1) Identifying resonance (peak response), (2) Designing vibration isolation, (3) Fatigue assessment under cyclic loading. Requires damping input (critical for peak response).
**Push:** What is the difference between modal and harmonic analysis? -> Modal finds natural frequencies (no loading). Harmonic finds response to cyclic loading (includes damping and load amplitude).
**Trap:** Running harmonic analysis without damping - peak response at resonance will be infinite (or very high).
**What they're really testing:** Whether you understand harmonic analysis and its application.

### Q37. Transient dynamic analysis. [M]
**A:** Transient dynamic analysis: finds time-history response to time-varying loads. Output: (1) Displacement/velocity/acceleration vs time, (2) Stress vs time. Used for: (1) Impact/shock loading, (2) Seismic analysis, (3) Drop tests. Requires: (a) Time step selection (small enough to capture response), (b) Damping, (c) Initial conditions. More computationally expensive than static or modal.
**Push:** When would you use transient instead of harmonic analysis? -> When loading is not sinusoidal (impact, shock, seismic, arbitrary time history).
**Trap:** Using too large time step - misses peak response and high-frequency content.
**What they're really testing:** Whether you understand transient dynamic analysis.

### Q38. Buckling analysis. [M]
**A:** Buckling analysis: finds critical load at which structure becomes unstable. Linear buckling: eigenvalue analysis, finds buckling load factor and mode shape. Nonlinear buckling: includes large displacements and material nonlinearity, more accurate. Linear buckling is conservative (overestimates capacity). Used for: columns, thin-walled structures, pressure vessels. Buckling load factor = critical load / applied load.
**Push:** What is the difference between linear and nonlinear buckling? -> Linear: eigenvalue analysis, assumes small displacements, overestimates capacity. Nonlinear: includes large displacements, more accurate, captures post-buckling behavior.
**Trap:** Using linear buckling for structures with large imperfections - linear buckling is too optimistic.
**What they're really testing:** Whether you understand buckling analysis.

### Q39. Fatigue analysis in FEA. [M]
**A:** FEA fatigue: (1) Calculate stress history from FEA (static or transient). (2) Extract stress components at critical locations. (3) Apply fatigue criteria (Goodman, Gerber, Soderberg). (4) Calculate cycles to failure using S-N curve. (5) For variable amplitude, use Miner's rule. Tools: nCode, FEMFAT, ANSYS Fatigue. Key: stress concentration factor (Kf) for notches.
**Push:** What is the difference between stress-life and strain-life fatigue? -> Stress-life (S-N) for high-cycle fatigue (> 10^4 cycles). Strain-life (epsilon-N) for low-cycle fatigue (< 10^4 cycles) where plastic deformation occurs.
**Trap:** Using S-N curve for low-cycle fatigue - plastic deformation invalidates stress-life approach.
**What they're really testing:** Whether you can perform fatigue analysis using FEA results.

### Q40. Thermal analysis in FEA. [M]
**A:** Thermal FEA: (1) Steady-state: temperature distribution, heat flux. (2) Transient: temperature vs time. Boundary conditions: (a) Temperature (fixed), (b) Heat flux (specified), (c) Convection (h, T_inf), (d) Radiation (emissivity, T_surroundings). Coupled thermal-structural: temperature distribution from thermal analysis used as load in structural analysis (thermal stress).
**Push:** What is coupled thermal-structural analysis? -> Temperature distribution from thermal analysis is applied as a load in structural analysis to calculate thermal stress. Used for: engines, heat exchangers, brake discs.
**Trap:** Ignoring thermal stress in FEA - thermal expansion can cause significant stress in constrained structures.
**What they're really testing:** Whether you understand thermal FEA and coupled analysis.

## 4. FEA Validation and Best Practices - 10 questions

### Q41. FEA result validation. [H]
**A:** FEA validation: (1) Check reaction forces sum to applied loads. (2) Compare with hand calculations (simple cases). (3) Check stress/displacement magnitudes are reasonable. (4) Verify boundary conditions are correctly applied. (5) Check mesh convergence. (6) Compare with test data (if available). (7) Check for stress singularities. Never trust FEA results without validation.
**Push:** What is the first check after running FEA? -> Reaction forces - they must sum to applied loads. If not, boundary conditions or loads are wrong.
**Trap:** Accepting FEA results without validation - FEA is only as good as the inputs and assumptions.
**What they're really testing:** Whether you validate FEA results properly.

### Q42. FEA for bolted joints. [M]
**A:** Bolted joint FEA: (1) Model bolt as beam or solid (beam is faster, solid is more accurate). (2) Apply preload (tension) to bolt. (3) Model contact between flanges (frictional or bonded). (4) Apply external load. (5) Check: (a) Bolt stress, (b) Flange separation (gap), (c) Contact pressure. Simplified: use bolt load (preload + external load fraction) from hand calculation.
**Push:** What is the most common simplification in bolted joint FEA? -> Modeling bolt as a beam element instead of solid - much faster, acceptable for preliminary design.
**Trap:** Forgetting to apply bolt preload - without preload, the joint behavior is completely wrong.
**What they're really testing:** Whether you can model bolted joints in FEA.

### Q43. FEA for pressure vessels. [M]
**A:** Pressure vessel FEA: (1) Model as axisymmetric (2D) or 3D. (2) Apply internal pressure. (3) Check: (a) Hoop stress, (b) Longitudinal stress, (c) Von Mises stress, (d) Displacement. (4) Check nozzle stresses (stress concentration). (5) Check flange stresses. Standards: ASME VIII requires FEA for non-standard geometries. Use thin-shell elements for vessel wall.
**Push:** When is FEA required for pressure vessels? -> For non-standard geometries (non-circular, large nozzles, complex supports) that are not covered by ASME VIII Division 1 rules.
**Trap:** Using FEA to replace code calculations - FEA supplements but doesn't replace code requirements.
**What they're really testing:** Whether you can perform FEA for pressure vessels.

### Q44. FEA for rotating machinery. [M]
**A:** Rotating machinery FEA: (1) Static analysis: stress due to centrifugal force (rotating reference frame). (2) Modal analysis: natural frequencies (critical speeds). (3) Harmonic analysis: response to unbalance. (4) Transient: startup/shutdown. Key: (a) Include centrifugal stiffening, (b) Check critical speeds, (c) Check stress at blade roots, (d) Check bearing loads. Use cyclic symmetry for bladed disks.
**Push:** What is cyclic symmetry in FEA? -> For bladed disks (turbines, compressors), model one sector and apply cyclic symmetry boundary conditions. Reduces model size significantly.
**Trap:** Ignoring centrifugal stiffening - rotating structures are stiffer due to centrifugal tension.
**What they're really testing:** Whether you can perform FEA for rotating machinery.

### Q45. FEA for composite materials. [M]
**A:** Composite FEA: (1) Material properties vary by direction (orthotropic/anisotropic). (2) Layered shell elements (for laminates). (3) Failure criteria: (a) Tsai-Wu, (b) Tsai-Hill, (c) Hashin. (4) Interlaminar stress (delamination). (5) Progressive damage (ply failure). Challenges: (a) Many material constants, (b) Complex failure modes, (c) Manufacturing defects (voids, fiber waviness).
**Push:** What is the difference between orthotropic and anisotropic? -> Orthotropic: properties differ in 3 perpendicular directions (fiber composites). Anisotropic: properties differ in all directions (general case).
**Trap:** Using isotropic material properties for composites - gives wrong stress distribution and failure prediction.
**What they're really testing:** Whether you understand composite FEA.

### Q46. FEA mesh refinement strategies. [M]
**A:** Mesh refinement: (1) h-refinement: reduce element size. (2) p-refinement: increase element order. (3) r-refinement: relocate nodes to high-gradient areas. (4) Adaptive meshing: automatic refinement based on error estimates. Strategy: (a) Start with coarse mesh, (b) Refine in high-stress areas, (c) Check convergence, (d) Don't over-refine (diminishing returns).
**Push:** What is adaptive meshing? -> Automatic mesh refinement based on error estimates. The solver refines elements where error is high and coarsens where error is low.
**Trap:** Refining mesh everywhere - wastes computation; refine only where stress gradients are high.
**What they're really testing:** Whether you can refine mesh effectively.

### Q47. FEA for welds. [M]
**A:** Weld FEA: (1) Model weld as solid elements (detailed) or beam elements (simplified). (2) Include HAZ (different material properties). (3) Apply weld residual stresses (from welding simulation). (4) Check: (a) Weld throat stress, (b) HAZ stress, (c) Fatigue at weld toe. (5) Use submodeling for detailed weld toe stress. Standards: IIW (International Institute of Welding) fatigue design.
**Push:** What is submodeling in FEA? -> Create a coarse global model, then create a fine local model (submodel) of the critical region with boundary conditions from global model. Saves computation while getting detailed results.
**Trap:** Modeling weld as a single material - ignores HAZ and residual stresses, giving wrong fatigue life.
**What they're really testing:** Whether you can model welds in FEA.

### Q48. FEA for springs. [L]
**A:** Spring FEA: (1) Model spring as solid (detailed) or beam (simplified). (2) Include contact between coils (for compression springs). (3) Apply load. (4) Check: (a) Stress distribution, (b) Deflection, (c) Buckling (for compression springs). (5) Fatigue: check stress amplitude at coil inner surface. Challenges: (a) Contact between coils, (b) Large deformation, (c) Nonlinear geometry.
**Push:** Why is spring FEA nonlinear? -> Because of contact between coils (as spring compresses, coils touch) and large deformation (spring wire bends significantly).
**Trap:** Using linear FEA for compression springs - misses coil contact and gives wrong stiffness.
**What they're really testing:** Whether you can model springs in FEA.

### Q49. FEA for gears. [M]
**A:** Gear FEA: (1) Model gear tooth as 3D solid. (2) Apply torque to gear. (3) Contact between teeth (frictional). (4) Check: (a) Tooth root stress (bending), (b) Contact stress (Hertzian), (c) Deflection. (5) Use cyclic symmetry for gear (one tooth sector). Standards: AGMA for gear stress. Key: (a) Mesh refinement at tooth root and contact point, (b) Include friction in contact.
**Push:** Why is gear FEA challenging? -> Because of: (1) Contact between teeth (nonlinear), (2) Stress concentration at tooth root, (3) Need for fine mesh in small regions.
**Trap:** Using coarse mesh for gear teeth - misses stress concentration at tooth root.
**What they're really testing:** Whether you can perform FEA for gears.

### Q50. FEA best practices summary. [H]
**A:** FEA best practices: (1) Simplify geometry (remove small features that don't affect results). (2) Use appropriate element type. (3) Mesh refinement in high-gradient areas. (4) Verify boundary conditions and loads. (5) Check reaction forces. (6) Convergence study. (7) Validate with hand calculations. (8) Report results with assumptions and limitations. (9) Don't over-trust FEA - it's a tool, not an oracle.
**Push:** What is the golden rule of FEA? -> Garbage in, garbage out. FEA results are only as good as the inputs, assumptions, and validation.
**Trap:** Treating FEA as a black box - you must understand the physics, not just push buttons.
**What they're really testing:** Whether you follow FEA best practices and understand its limitations.

## File Statistics

**Total questions: 50**

**By tag:**
- [H] High-yield: ~20 questions
- [M] Medium-yield: ~27 questions
- [L] Occasional: ~3 questions

**By section:**
- CAD fundamentals: 10 questions
- GD&T: 15 questions
- FEA: 15 questions
- FEA validation and best practices: 10 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers CAD, GD&T, and FEA - essential for automobiles, petrochem, and construction interviews.