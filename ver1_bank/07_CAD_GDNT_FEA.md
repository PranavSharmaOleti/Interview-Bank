# CAD, Engineering Drawing, GD&T and FEA - L&T GET technical interview bank

**Part 7 of 8 | 32 questions | CAD and engineering drawing, geometric dimensioning and tolerancing, and finite element analysis**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly, [L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing recall, they are testing whether you can reason out loud.*

## 1. CAD and Engineering Drawing - 13 questions

### Q1. What is CAD, and what is it actually used for in an engineering organisation? [H]

**A:** CAD is software for computer-aided design where a part is built as a precise 3D model with dimensions attached, not just as a picture. Its real value is that it stores design intent: every feature is linked to a dimension or a relation, so a change updates the model, the drawing and the BOM. In an engineering organisation this means the drawing on the shop floor and the model used for CAM can never disagree, and the same data feeds simulation (FEA/CFD), costing and procurement. CAD is fundamentally a parametric database that makes design changes cheap and eliminates contradictions.

**Push:** Design intent means that when you say "the bolt holes are at 60 degrees on a 120 mm pitch circle", you store both the diameter and the pattern, not typed coordinates. Changing the pitch updates all holes automatically.

**Trap:** Saying CAD is just "faster drawing" or "better pictures". It is a parametric definition of the part, not a visual representation.

### Q2. Explain parametric modelling: sketches, features, the feature tree, and what happens when you change a parameter. [H]

**A:** In parametric modelling you first sketch a profile with constraints, then add features (extrude, fillet, hole, cut) that each reference that sketch. Every feature is a node in a tree and each one depends on the ones below it, so changing the sketch dimension regenerates the whole tree automatically. A parametric model beats a static or "dumb solid" because the design intent stays alive, variants are cheap and mistakes are recoverable. The feature tree is also the manufacturing data for CNC and other downstream processes.

**Push:** What happens if the change makes a feature fail to rebuild? The software reports an error and you must resolve the dependency, usually by editing the sketch, reordering the features or using a soft reference.

**Trap:** Believing that changing a dimension just scales the model. In a parametric model the change propagates through the feature tree, updating everything that depends on it.

### Q3. What constraints do you use in a sketch, and what happens in an over-constrained sketch? [H]

**A:** Sketches have two types of constraints: dimensional (the numbers like distance, diameter, angle) and geometric (the way elements relate - horizontal, vertical, coincident, parallel, perpendicular, tangent, equal, symmetric). A sketch is fully defined when every degree of freedom is removed exactly once. Over-constrained means more constraints than needed, for example a horizontal constraint plus a dimension that forces the same horizontal distance, so the solver either rejects the sketch or silently drops one constraint, and the geometry moves in a direction you did not intend.

**Push:** How do you tell if a sketch is fully defined? Most packages grey out the sketch when it is fully defined and show the remaining DOF. If the sketch is not fully defined it stays blue and you can drag it.

**Trap:** Thinking that more constraints always mean more control. Redundant constraints are the most common cause of a sketch that will not solve.

### Q4. Walk me through an assembly in CAD - components, mates, fixing a component, sub-assemblies, and the assembly tree. [H]

**A:** An assembly brings together components as references to their part files. Position is controlled by mates such as coincident (faces or points touching), concentric (axes sharing a line), parallel, perpendicular, tangent, distance, angle and others. The first component inserted is fixed (grounded) to the origin; all other components are positioned relative to it. A floating or under-defined component triggers a warning. Sub-assemblies are assemblies used as components inside a larger assembly, and the tree shows the hierarchy from part to sub-assembly to top assembly, which is also what drives the BOM.

**Push:** Why do we only fix one component? Mates are all relative, so one absolute reference is enough to set the whole tree. Fixing a second component gives two independent references, and the assembly will fight you.

**Trap:** Saying "fix everything". Over-constrained assemblies have mates fighting each other; instead you should fully define each component by its mates and a single ground component.

### Q5. First angle or third angle projection - which is used where and why? [H]

**A:** First angle has the object between the observer and the projection plane, so the view from the right is placed on the left of the front view. Third angle has the plane between the observer and the object, so the right-side view appears on the right. India, the UK, Europe and ISO practice use first angle; the USA uses third angle. Every drawing declares the convention in the title block with a symbol - a truncated cone drawn in two views - so before you read any view you check that symbol.

**Push:** How do you identify the convention quickly? Look at a familiar part - a shaft with a shoulder: in third angle the shoulder view is on the right of the shaft; in first angle it's on the left.

**Trap:** Assuming the projection method from the shape of the views without reading the title block symbol.

### Q6. What are the rules for dimensioning a drawing? [H]

**A:** Dimension only what you need to manufacture and inspect: sizes of features, locations and angles - everything else is derived. Never dimension a dimension, never give the same dimension twice, and never give more dimensions than needed. Size dimensions (diameter, width, thickness, radius) give the size of the feature itself; location dimensions (from a datum to a centre or a face) fix where it sits - you need both, and they are different kinds of information. A chain of dimensions, where each references the previous one, is the chain method; errors accumulate along the chain. The baseline method measures everything from one common datum, so errors do not accumulate but one datum dimension must be the tightest. Above all, one dimension should appear only once and be clearly interpretable.

**Push:** Why not dimension from the view instead of a datum? Because the view is only a picture; the dimension must survive the part being rotated and it must be measurable with the part in a fixed position.

**Trap:** Giving the same dimension in two places so the drawing "looks complete" - it creates a contradiction that the inspector finds.

### Q7. Explain sectional views — why do we use them, and what are full/half, revolved and removed sections? [H]

**A:** A sectional view cuts the object with a cutting plane and shows what lies behind it, with the cut surface hatched. We use sections to expose internal features — bores, ribs, webs, holes — that hidden lines cannot show clearly, and because a hidden-line drawing gets unreadable and ambiguous. The common types are a full section, where the cutting plane passes right through the part and you view in the arrow direction, and a half section for symmetrical parts. A revolved section is the cross-section drawn directly on the view, as if the part were rotated 90° about the cutting plane; a removed section is the cross-section drawn elsewhere on the sheet, useful for small features on one part.

**Push:** Why are ribs and webs hatched differently (unhatched) when cut lengthwise? Because the cutting plane passes along the rib or web, there is no solid material to show, so standard practice is to leave them unhatched to avoid implying thickness.

**Trap:** Hatching a rib or a shaft cut lengthwise, or using the same 45° hatch for two adjacent parts, which makes them look like one continuous solid body.

### Q8. What are the conventions for conventional representation: centre lines, hatching, threads, knurling, surface finish, radius and chamfer callouts? [M]

**A:** Centre lines are thin chain lines marking axes and centres, drawn extending slightly beyond the feature. Hatching on a section uses thin, evenly spaced 45° lines, with adjacent parts at different angles or spacing. Threads are shown schematically: the minor diameter as a thin line inside the major diameter, with a partial view of the thread at the end of the stud. Knurling is shown as a criss-cross pattern with the pitch noted. The surface finish symbol is the check-mark-like symbol with the roughness value (Ra) written on the stem; a bar across the symbol means material removal required, a circle means as-cast. Radii and chamfers are called out as R and C values with an arrow to the arc or corner.

**Push:** What does the roughness number mean? Ra is the average roughness in micrometres; 1.6 means a fine machined finish, 12.5 means a rough cast finish. The shop picks the process (turning, grinding, milling) that can hold that value.

**Trap:** Leaving off the radius or chamfer callout on a corner. Then the shop can legally supply a sharp corner or a different radius, and the part may not assemble.

### Q9. What is a bill of material, and how does a drawing become a manufacturable part? [M]

**A:** A BOM is the structured list of the parts in an assembly - part number, description, quantity, material - arranged in levels, so a sub-assembly is one line in the parent assembly. It is the contract between design and procurement/finance: it drives RFQs, purchase orders, costing and stores issue. For a part to become manufacturable you need: a drawing with all dimensions, tolerances, GD&T, material and surface finish; a BOM that tells you what to buy; a route card/process plan that says rough machine, finish machine, heat treat, inspect; and raw material in the required size. Every dimension on the drawing must be manufacturable and inspectable; the drawing is the frozen document that the shop works from.

**Push:** Why do we avoid dimensioning from the CAD model directly? The model can change without the drawing being updated, and the shop needs a frozen, signed document with a revision.

**Trap:** Believing a drawing plus a BOM is enough. You also need material grade, general tolerances, heat treatment, surface finish, and quantity - otherwise the part arrives wrong.

### Q10. Explain parametric modelling: sketches, features, feature tree, and changing a parameter. [M]

**A:** A parametric model builds a part in a history tree: a 2D sketch is created with constraints and dimensions, then features (extrude, fillet, hole, cut, pattern) are added that reference the sketch. Each feature remembers its dependencies and its parameters. Changing a dimension in the sketch causes the model to regenerate, updating all downstream features that depend on it. This is better than a static model because design intent is preserved, variants are cheap and the model can be edited later.

**Push:** What happens if a change makes a feature fail to rebuild? The software flags it, usually due to an invalid dimension, over-constrained sketch or missing feature; you resolve the dependency, reorder or suppress features.

**Trap:** Thinking changing a dimension just scales the model. In a parametric model the change propagates through the feature tree, updating everything that depends on it.

### Q11. How do you get interference checks and mass properties / centre of mass from a CAD model? [M]

**A:** An interference check takes every solid in the assembly and tests whether any two occupy the same space. It catches clashes before release, and for a moulding or assembly study it tells you which parts need clearance. Mass properties are computed from the solid model: volume, surface area, centre of mass (centroid) and moments of inertia. Centre of mass is needed for handling and for rotating machinery in FEA or CFD; moments of inertia are needed for rotational dynamics.

**Push:** What about clearance checks? These are the complement of interference - they give the minimum gap between parts. Use them for moving assemblies where you need a specific clearance.

**Trap:** Assuming the CAD centroid equals the real centre of mass. They coincide only for a uniform-density part; a part with a heavy boss or a weld region shifts the centre of mass.

### Q12. What is the difference between CAD and CAM, and what does a CAM programmer actually do? [H]

**A:** CAD is design - geometry, dimensions, assemblies, drawings. CAM is manufacturing - turning that geometry into machine instructions. A CAM programmer selects the machine (3-axis mill, lathe, EDM), sets up the stock and fixtures, chooses the tools, defines operations (roughing, semi-finishing, finishing, drilling, tapping, milling, turning), sets speeds/feeds and depth of cut, picks toolpaths and post-processes the result into NC code (G-code) for the machine controller. The part does not change, the process does; and the loop goes back to the designer, because manufacturing constraints (tool radius, minimum internal corner radius, clamping) feed back to the design.

**Push:** How do manufacturing constraints feed back to design? For example, the internal corner radius must be at least as large as the cutter radius, so the model must show a fillet of that size, or you use a smaller tool and pay more.

**Trap:** Saying CAM is just "CAD with G-code attached". CAM is process planning and tooling, not geometry.

### Q13. SolidWorks, Creo, NX, CATIA and Inventor - what is each strong at, and which would you pick? [M]

**A:** SolidWorks is mid-range and quick to learn, strong on everyday machine design - brackets, manifolds, sheet metal - and popular with small and mid-size manufacturers; Inventor is similar in class with a lower-cost Autodesk ecosystem and good sheet metal and standard part libraries; Creo (parametric) is used for detailed product design in automotive, consumer electronics and general engineering, and is common in Indian industry; NX (Siemens) has the best integrated CAD/CAM, so it is standard in aerospace, automotive and tooling; CATIA is for aerospace and automotive styling and systems engineering - Boeing and Airbus use it. For a general mechanical GET I would pick Creo or SolidWorks for learning and for a plant job - the skill that matters is parametric discipline, and the CAD interface changes less than people think.

**Push:** How do you evaluate a new CAD system? The criteria are: does it support the modelling you need (parametric, surface), does it integrate with downstream processes (CAM, simulation), what is the cost, what is the learning curve, and what support does the company provide.

**Trap:** Answering with a brand name as if it were the skill. Say what each is good at and pick one with a reason.

**What they're really testing:** Whether you understand CAD as a parametric, data-driven engineering process rather than a drawing program — can you explain what happens inside the model when something changes, and connect the model to the drawing, the BOM and the shop floor.

## 2. Geometric Dimensioning and Tolerancing (GD&T) - 11 questions

### Q14. Why does GD&T exist? What is ASME Y14.5 and why does it exist?

**A:** Traditional plus/minus dimensioning says only what size a feature is and says nothing about its shape, orientation or true position. So two parts can both be Ø20 ± 0.1 and one can be a squashed, tilted 20mm hole while the other is a perfect one - both pass. GD&T adds the missing information: it tells the shop what the function of the feature needs, not just its size. ASME Y14.5 is the US standard; the international equivalent is ISO 1101 and the two are nearly identical in content, with slightly different symbol shapes. GD&T does not replace dimensioning - you still dimension the sizes and the basic (theoretically exact) location values; GD&T adds control of form, orientation, location and runout.

**Push:** What is the practical benefit in a plant? Inspectors can use functional gauges and the drawing is unambiguous, so disputes between design and shop about "is this part good" disappear.

**Trap:** Saying GD&T is only for aerospace or only for high-volume automotive. It is used whenever function depends on more than size.

### Q15. What is a datum? How do you establish a datum reference frame? What is a datum simulator, and why must a datum be theoretically exact?

**A:** A datum is a theoretically exact plane, axis or point that a feature of size is taken to establish — the "ideal" version of a real feature. On the drawing you mark the datum feature with a boxed letter attached to a triangle, for example A on the bottom face. When you set up the part in the shop, the machine table and the fixture imitate that datum — that is the datum simulator, and the machine literally uses the real surface as the reference. A datum reference frame (DRF) is the set of datums you have selected: A primary, B secondary, C tertiary, fixing the part in 3D. The rule is that the primary datum establishes translation and the secondary and tertiary establish rotation, and the order matters because a poor primary datum makes the whole measurement unstable.

**Push:** Why must the primary datum be a broad, flat surface? A large flat surface is the only one that reliably locates the part - a small boss or a single hole will let the part rock and the measurement will scatter.

**Trap:** Treating the datum as the actual surface with its roughness. It is the theoretically exact plane; the real surface is only allowed to deviate from it within the flatness or perpendicularity tolerance.

### Q16. The 14 geometric characteristics: what does each control? (grouped form, orientation, location, profile, runout)

**A:** They fall into five families. Form (no datum needed): straightness (of a surface or of a line of sight), flatness (the whole surface is flat), circularity (each cross-section of a cylinder is a true circle within two concentric circles) and cylindricity (the whole cylindrical surface lies between two coaxial cylinders). Orientation (one datum): angularity, perpendicularity, parallelism. Location (two or more datums): position, concentricity, symmetry. Profile (any number of datums): profile of a line and profile of a surface. Runout (any datums): circular runout and total runout.

**Push:** Which do you use most? Position for hole patterns, profile for curved outlines, perpendicularity and parallelism for machined faces, runout for shafts and rotating parts.

**Trap:** Mixing up circularity and cylindricity. Circularity is a 2D cross-section check; cylindricity covers the whole surface at once.

### Q17. Position tolerance versus a plus/minus diameter dimension — what's the difference? [H]

**A:** A plus/minus tolerance on a dimension gives only size control; the axis can wander anywhere within the cylinder formed by the size limits - a "worst case" is that a hole can be at its largest size AND at the limit at the same time. Worse, a plus/minus on a position gives a zone of two parallel planes in one direction only, and it does not fix the true centre. A position tolerance gives you a cylindrical zone of a stated diameter centred on the true position (derived from boxed basic dimensions) and oriented to the datums. Crucially, when position tolerance is applied to a feature of size and with MMC (or LMC) it also controls the size, so size and position are two sides of the same integrated requirement. That is why a position callout can replace both the size dimension and a separate location dimension.

**Push:** What is the virtual condition and why does it matter? It is the MMC size minus the position tolerance (for internal features) or plus (for external) — it is the functional gauge size. A part that passes the gauge will assemble; the virtual condition is what inspection uses to test interchangeability.

**Trap:** Calling a hole "position tolerant" when it has only a plus/minus dimension. A plus/minus dimension only controls size, not position.

### Q18. How do you read a feature control frame? [H]

**A:** Read it left to right: the geometric characteristic symbol, then the tolerance value (with a diameter symbol if the zone is cylindrical), then any modifier (M, L, S), then the datum references (primary A, secondary B, tertiary C). For example, a position symbol, 0.2 dia, then A, then B, then the MMC symbol after the tolerance value means: the axis of this feature must lie within a cylinder of diameter 0.2 mm, located at the true position from datums A and B, and 0.2 is the tolerance available at maximum material condition. The basic dimensions that fix true position are boxed on the drawing.

**Push:** Where does the material condition modifier go? It goes after the tolerance value for the controlled feature, not after the datum letters. After a datum letter it applies to that datum.

**Trap:** Misreading the frame as a recipe list. The frame is a compact description of what the feature must satisfy, with clear order: characteristic -> tolerance -> datums.

### Q19. What do MMC, LMC and RFS mean, and how do they change the tolerance? [H]

**A:** MMC is maximum material condition - for a hole the smallest allowed diameter, for a shaft the largest - the most material in the part, so the least tolerance is available and the zone is at its tightest. At MMC the tolerance in the frame is exactly the stated value. If the actual size departs from MMC (hole gets larger, shaft gets smaller), the part has gained material, so bonus tolerance is added equal to how much it departed from MMC. LMC is the opposite - a hole at its largest, a shaft at its smallest - the most tolerance, where the tolerance is greatest. RFS, regardless of feature size, means the tolerance stays exactly as stated no matter what the actual size is; no bonus, no loss. Some Indian textbooks write this as PMC (maybe "plus/minus condition") and use it the same way: the tolerance does not change with actual size.

**Push:** Why does bonus tolerance exist? It protects function - a hole slightly oversize is still acceptable if the position error is within the enlarged zone; the tolerance grows to match reality instead of rejecting good parts.

**Trap:** Thinking MMC gives the part more tolerance. It gives the least tolerance at MMC; the bonus appears as you move away from it.

### Q20. Rule 1 vs Rule 2 - the envelope requirement in short. [M]

**A:** ASME Y14.5-2009 introduced two rules: Rule #1 (independence) says size, form and orientation are independent, and a feature at MMC may still have form error; Rule #2 (envelope) says that when you invoke it (circled E after tolerance value) a feature of size at MMC must lie inside a perfect-form envelope sized at MMC plus the geometric tolerance, so form and size are not independent, giving a functional gauge at the virtual condition. Y14.5-2018 restructured: Rule #1 is now the default independent principle, and the envelope requirement is an option invoked explicitly, and ISO 1101:2017 made the maximum material requirement default - note the difference.

**Push:** Which one lets you use an envelope gauge? Rule 2 (envelope) — invoked explicitly with the symbol.

**Trap:** Assuming Rule 1 is the envelope. In the current ASME, Rule 1 is the independent principle; the envelope is Rule 2 (if invoked).

### Q21. What is a tolerance stack-up, and what are the worst case and RSS methods? [M]

**A:** A stack-up is the accumulation of tolerances through a chain of dimensions. Worst case (arithmetic) assumes every part is at its worst limit at the same time, T_total = sum(T_i). It is conservative and used for safety-critical chains. Statistical (RSS) uses the root of the sum of the squares: T_total = sqrt(T1^2 + T2^2 + ...). RSS assumes errors are independent and random; actual stack is usually much smaller. RSS is realistic for many parts in volume; worst case for hand-fitted or critical.

**Push:** When would you use worst case? In safety-critical parts, single-shot assembly where the number of contributors is small.

**Trap:** Using RSS where the tolerances are correlated and not independent - e.g., a single part with a measurement that affects multiple dimensions.

### Q22. Fits and tolerances — ISO system, hole basis and shaft basis, clearance/transition/interference fits with an example of each, IT grades. [H]

**A:** ISO system separates the tolerance grade (IT) which fixes the size of the tolerance zone, and the fundamental deviation (a letter) which fixes its position relative to nominal. IT grades IT01 to IT18; IT1-IT3 fine, IT4-IT6 fine, IT7-IT8 medium, IT9-IT11 coarse, IT12-IT18 very coarse. In hole basis the hole always has H (lower deviation zero, hole above nominal), shaft gets the letter. In shaft basis it is reversed. Three fit types: clearance (hole always > shaft), transition (zones overlap, can be clearance or interference), interference (shaft always > hole). Example: for 20 mm nominal, H7 hole is 20.000-20.021 (IT7 = 21 µm for 18-30 mm step), g6 shaft is 19.981-19.994 (es = -6, IT6 = 13). H8/f7 clearance example: H8 = 20.000-20.033 (IT8 = 33 µm), f7 = 19.959-20.001 (es = -20). H7/p6 interference example: p = +28 µm deviation, p6 = 20.028-20.041 (es = +28, ei = +28-13 = +15).

**Push:** What is the fit for a bolt hole? H7/g6 is the standard loose running fit; H8/f7 is a clearance fit used when clearance is important.

**Trap:** Confusing the fundamental deviation letter with the fit — the letter sets where the zone sits, the IT grade sets its size.

### Q23. What is surface finish, and how is it communicated on the drawing? [M]

**A:** Surface finish is the roughness of a surface, normally quoted as Ra in micrometres. Typical machined values: 0.2-0.8 for precision ground, 1.6-6.3 for general turning, 12.5-25 for rough casting. The drawing carries the surface finish as a symbol - the check-mark shape with a value; a bar means material removal required, a circle means as-cast. Roughness tolerance is separate from dimensional tolerance and applies to every surface unless a specific symbol overrides it.

**Push:** Why does surface finish matter functionally? It controls fit and wear - a bearing journal and a sliding shaft need a specified finish; it also affects fatigue strength, since a rough surface is a stress raiser.

**Trap:** Assuming the symbol tells the shop the process. Unless a specific process symbol is used, the shop chooses the process that can hit the Ra value.

### Q24. What does a manufacturing engineer check when a drawing arrives, and how is GD&T read on the shop floor? [L]

**A:** Before release the engineer checks the title block and revision, material grade, heat treatment, surface finish, general tolerances, completeness of dimensions, GD&T consistency, manufacturability (draft, machining access, tolerances achievable), quantity and process planning. On the floor the drawing is read with a datum simulator - the physical surface that stands in for the datum - and a functional gauge at the virtual condition, or a CMM that reports the actual form/orientation/location errors relative to the datum reference frame.

**Push:** How do you set up a datum? Mount the part on a fixture that mimics the datum feature; the fixture becomes the datum simulator.

**Trap:** Treating the datum feature as a surface with roughness. The datum is ideal; the real surface is allowed to deviate within its own form tolerance.

**What they're really testing:** Whether you understand that GD&T is the language that links the drawing to function and to inspection — datums, tolerance zones, material conditions — rather than a list of symbols to memorise.

## 3. Finite Element Analysis (FEA) - 9 questions

### Q25. What is FEA and what is it legitimately for (and what it is not)? [H]

**A:** Finite element analysis divides a structure into many small elements (a mesh), solves the governing equations (equilibrium, compatibility, material law) for each element to get displacements and stresses. Legitimate uses: sizing, design variant comparison, finding stress concentrations, deflection, fatigue, thermal, vibration, impact. Not for: certifying safety on its own (needs test data and a code check), proving the load is right, getting accurate results from a bad mesh, handling contact/physics beyond scope (e.g., CFD, crack growth). FEA does not tell you the load is right.

**Push:** What is the biggest risk in an FEA study? The boundary conditions and the contact assumptions, not the solver.

**Trap:** Treating the solver output as a validated answer. Need verification (hand calc, convergence) and validation (test data).

### Q26. Walk me through the FEA workflow from geometry to a result someone can trust. [H]

**A:** Define the objective and the load case. Simplify the geometry: remove cosmetic fillets, use symmetry, replace thin parts by shells/beams. Apply the material - E, Poisson's ratio, density, yield. Mesh, choosing element type and size. Apply constraints and loads (supports, symmetry, contact, forces). Solve, linear or non-linear. Post-process: displacements, stresses, reactions, check the result. Validate: compare against a hand calculation or test data, and check convergence.

**Push:** How do you decide when to use a beam instead of a solid for a shaft? When you only need stress and deflection and the cross-section is constant or nearly so - it is orders of magnitude cheaper.

**Trap:** Starting with meshing. If the objective and the load path are not clear, you will mesh, solve and produce a beautiful plot of the wrong thing.

### Q27. What element types can you use, and how do you choose? [H]

**A:** 1D beam elements for slender members (shafts, brackets), where you need bending and axial stiffness. 2D shell elements for thin-walled parts like a gearbox cover or thin plate. 3D solid elements for bulky or complex local geometry like bosses, holes, fillets. Axisymmetric elements for a body of revolution under axisymmetric loading (a pressure vessel, a pulley). The choice is driven by the part shape, thickness-to-span ratio and accuracy required. Element order: linear (4-node tet, 8-node hex) is cheaper but stiffer in bending; quadratic (10-node tet, 20-node hex) captures curvature and bending much better, at higher cost.

**Push:** When do you refine, and why? At stress concentrations - holes, notches, load application, contact patches, sharp corners. The elements must be small enough that the stress gradient is resolved — at least two or three elements across a fillet radius, at least three across a bending thickness.

**Trap:** Refining everywhere uniformly. It costs solver time without improving the answer where it matters.

### Q28. How do you idealise boundary conditions - supports, bolted joints and contacts? [H]

**A:** A support must be realistic about which degrees of freedom it removes and how stiff it is. A pinned support removes translation but allows rotation; a fixed support removes all six. A bolted joint can be modelled as a rigid connection (over-constraining) or with a bolt element with pretension, or using a bolt/connector with tension and shear stiffness. Contact must be specified: bonded, no separation, frictional with mu, or general contact. Wrong boundary conditions give wrong stress fields and deflection.

**Push:** Why does a rigidly bonded bolted joint give a different answer? It removes the joint flexibility and the bolt pretension, so the joint becomes infinitely stiff — the loads flow differently and local stresses are overpredicted.

**Trap:** Fixing every face of a part as if welded. That removes the real load path; the part in the model is stiffer than reality.

### Q29. Results interpretation: von Mises, principal stress, max shear, displacement, reaction force, and what a stress plot does NOT tell you. [H]

**A:** Von Mises (equivalent) combines the three principal stresses into a scalar that matches ductile yielding; it is not a real stress. Principal stresses are the max/min normal stresses on any orientation - the max principal stress governs brittle failure; max shear is half the difference between max and min principal. Displacement shows deformation; if implausibly large, model or constraints are wrong. Reaction force is the best sanity check - sum of reactions must equal applied load. What a stress plot does NOT tell you: whether the peak is real or a singularity, whether the load case is right, whether the mesh is fine enough, whether the material is strong enough (strength not in the plot), and no fatigue life.

**Push:** Why is von Mises not the right criterion for cast iron? Cast iron is brittle, fails in tension on the max principal stress, so use max principal.

**Trap:** Reporting the peak von Mises value without saying where it is, whether it converged, and whether it is above yield.

### Q30. What is a stress singularity and how do you deal with it? [H]

**A:** At a sharp re-entrant corner, a point load, or a fully fixed edge, the geometry makes the stress unbounded - refining the mesh just pushes the number higher. That is an artefact, not a physical stress. Handle by: putting a realistic fillet radius in the model and meshing it finely; if you cannot change geometry, report the stress at a distance from the corner and apply a stress concentration factor from a handbook; replace a point load with a distributed load over the bolt head; use quarter-point extraction; or treat as a hot-spot approach.

**Push:** How do you tell a singularity from a real peak? A singularity keeps climbing as you refine; a real peak converges with refinement.

**Trap:** Taking the maximum stress in the plot at face value for a strength check. If it is at a sharp corner, it is meaningless.

### Q31. Verification vs validation: hand calculation check, test data, and why an FEA without a hand check is not evidence. [H]

**A:** Verification: did we solve the equations correctly? Check with analytical solution, mesh convergence, reaction balance. Validation: did we solve the right problem? Compare against test data, strain gauge reading, load-deflection curve from a rig. An FEA without a hand check is just a number from a model; if BCs are wrong, the solver gives you a confident, wrong answer.

**Push:** How do you present this in a report? State objective, geometry simplifications and why, material data and source, element type, mesh size with convergence evidence, BCs with justification, loads, results as numbers with location, criterion used, verification evidence, limitations, clear recommendation.

**Trap:** Delivering just colour plots without analysis. The deliverable is a number with a location, argument, and honest statement of assumptions.

### Q32. Failure criteria: von Mises vs max principal stress vs Tsai-Hill for composites, and which to use. [M]

**A:** Von Mises for ductile metals (distortion energy) — steel, aluminium. Max principal stress for brittle materials (cast iron, concrete, ceramics). Maximum shear (Tresca) conservative for ductile. For composites, Tsai-Hill for a unidirectional lamina because strength differs along and across fibres.

**Push:** Why is von Mises wrong for cast iron? Cast iron fails by tensile cracking on the max principal stress; von Mises under-predicts risk.

**Trap:** Applying von Mises everywhere because it is default in the software. Choice matters for material and failure mode.

### Q33. Fatigue: stress-life vs strain-life, and when is S-N data not enough. [M]
**A:** Stress-life (S-N, Basquin) is for high-cycle fatigue: elastic strain, many cycles (>10^4-10^5), stress amplitude vs cycles to failure. Strain-life (Coffin-Manson) is for low-cycle fatigue: plastic strain involved, fewer cycles, and includes elastic and plastic components (in elastoplastic regime). S-N is not enough when local plasticity occurs, when loading is variable amplitude (need rainflow counting + Miner's rule), when mean stress is significant (need Goodman/Gerber correction), when multiaxial loading, or when notches/welds (need fatigue notch factor + local stress).

**Push:** Why does FEA matter for fatigue? FEA gives local stress for strain-life and local stress amplitude for S-N, especially at notches.

**Trap:** Using S-N for a component that sees plasticity. That underestimates damage; need strain-life.

What they're really testing: Understanding FEA and fatigue as tools for design, and knowing when each model is appropriate, recognising limitations, and presenting actionable results.
