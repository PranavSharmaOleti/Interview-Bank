# Machine Design - Core Interview Bank

**Part 5 of 10 | 50 questions | Shafts, keys, couplings, belts, gears, bearings, springs, fasteners, design process**
*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Design Process and Philosophy - 8 questions

### Q1. Design process from requirement to finished drawing. [H]
**A:** Design engineer converts a requirement into a drawing that someone can make and that survives its duty. Sequence: (1) fix requirements - function, load, environment, life, cost, standards; (2) estimate loads - static, dynamic, fatigue, worst credible case; (3) choose material from strength, corrosion, heat, wear; (4) preliminary size from simple stress or stiffness relations; (5) detailed analysis - hand calculation with stress concentration and deflection, or FEA; (6) fix factor of safety and check every likely failure mode; (7) consider manufacture - machining, welding, standard stock; (8) issue drawing with tolerances, fits, surface finish; (9) prototype; (10) test and prove it, then modify.
**Push:** Where do standard parts fit into this? -> At steps 3 to 7 you check whether an off-the-shelf bearing, fastener, coupling or motor already does the job, because using it cuts cost, lead time and risk.
**Trap:** "The last step is submitting the drawing." A design that was never prototyped and tested is not a finished design.
**What they're really testing:** Whether you treat design as a sequence with decisions and trade-offs.

### Q2. Stress-based vs strain-based design. [H]
**A:** In stress-based design the working stress must stay below an allowable stress, which is the material strength divided by a factor of safety, and that is what most codes use. In strain-based design you check the actual stress and strain against the real stress-strain curve with a limit on each, so the material is used far more efficiently and the failure mode can be predicted. ASME Section VIII Division 1 is the allowable-stress route for ordinary pressure vessels, Division 2 is the strain-based route used for higher pressures, complex shapes, fatigue or creep.
**Push:** When would you use Division 2? -> For higher allowable stress, complex geometry or where you need fatigue and creep analysis to exploit the material.
**Trap:** Calling allowable stress the same as yield strength. It is yield (or ultimate for brittle) divided by the code factor of safety.
**What they're really testing:** Whether you know different design philosophies and when each is appropriate.

### Q3. Factor of safety, how choose for a real part. [H]
**A:** No, it's not always 3. The FoS covers uncertainty in the loads, in the material properties and in manufacturing, and it depends on how bad the failure would be. For a ductile steel bracket under static load, 2 to 3 is normal; for a casting, a weldment or anything with a sharp stress raiser, go higher, 3 to 4; for pressure parts the code fixes it, 3.5 on yield in ASME VIII Division 1. Brittle material needs more because it fails without warning. For fatigue you do not use one factor on the strength - you take an allowable amplitude from the S-N curve with roughly 1.5 to 2 on top.
**Push:** How is the FoS different for a crane hook and for a pressure vessel? -> Pressure vessel gets code value because leak can kill people and loads are well characterised; crane hook gets more because load range and shock are less predictable.
**Trap:** Quoting one universal value of 3. The interviewer wants to hear that it is a judgement about consequences, load uncertainty and material uniformity.
**What they're really testing:** Whether you treat FoS as a judgement, not a universal constant.

### Q4. Design for manufacturability and wear. [M]
**A:** For manufacturability you design to the process and to the shop: use standard stock sizes and standard tolerances, keep the geometry simple and machinable, avoid deep pockets, small holes and thin webs, make sure the part can be fixtured and inspected, and specify tolerances the process can actually hold. Against wear the levers are the material pair, the hardness difference between the two surfaces, the clearance, lubrication and cleanliness, the surface finish, and where the duty is severe a wear-resistant facing or a proper bearing material instead of metal on metal. And you prefer a standard part wherever the duty allows - an ISO bolt, a catalogue bearing, a standard coupling - because it is cheaper, arrives faster, is already proved, and comes with published ratings.
**Push:** When would you still design something custom? -> When no standard exists, when a custom part saves a lot of assembly time or space, or when a standard part has itself caused a failure.
**Trap:** Drawing something custom when a standard would do. The custom part is the one that gets drawn, machined, inspected and then fails at 3 am because nobody stocked a spare.
**What they're really testing:** Whether design for the real world - the shop floor, the wear environment and the spares inventory - is part of engineering.

### Q5. Design for static loading. [H]
**A:** For static loading, design stress = allowable stress = yield stress (or UTS for brittle) / FoS. FoS covers uncertainty in loads, material properties, manufacturing. Typical values: ductile steel under static load: 2-3; casting or weldment: 3-4; pressure parts: code value (3.5 on yield per ASME VIII Div 1). Brittle materials need higher FoS because they fail without warning. For fatigue, use S-N curve with 1.5-2 on top.
**Push:** How is the FoS different for a crane hook and for a pressure vessel? -> Pressure vessel gets code value because leak can kill people and loads are well characterised; crane hook gets more because load range and shock are less predictable.
**Trap:** Quoting one universal value of 3. The interviewer wants to hear that it is a judgement about consequences, load uncertainty and material uniformity.
**What they're really testing:** Whether you treat FoS as a judgement, not a universal constant.

### Q7. Design of bolted joints. [H]
**A:** A bolted joint works by preload, the clamp force generated when the bolt is tightened. The joint separates only when the external separating load exceeds the preload, and the preload also stops the joint slipping and prevents fatigue at the interface. Preload is set by torque through the thread friction: T = K F d, where K is the nut factor, about 0.2 for a clean lubricated steel bolt, F is the preload and d the nominal diameter. So a large fraction of what you apply with a wrench is lost to thread friction rather than going into stretching the bolt - which is why you always tighten to the same specified torque with the same lubrication. If you overtighten, the bolt can yield and then fail in fatigue, the thread can strip, or the clamped part can be crushed.
**Push:** How is the preload calculated or verified? -> The torque method is the everyday one, but the better methods are the turn-of-nut method, a defined fraction of an extra turn after snug tight, and the direct tension method, measuring the bolt stretch with a strain gauge or by ultrasound.
**Trap:** Believing tightening harder always clamps better. Beyond a point you only reduce the margin against fatigue failure of the bolt.
**What they're really testing:** Whether you know that the torque you apply and the tension in the bolt are not the same thing, and that the preload does most of the work.

### Q8. Design of threaded fasteners for tensile and shear. [M]
**A:** You keep the threads in tension and the shank in shear clearly separated. In tension you use the tensile stress area, about 0.79 d^2 for an ISO metric coarse thread, not the shank area, and the limit is either the proof strength of the bolt or thread stripping in the tapped material if that is the weaker one. In shear you use the shank area pi d^2/4 and the shear strength of the bolt, commonly taken as about 0.6 times the tensile strength, with the proviso that if the threads lie in the shear plane you must use the tensile stress area instead. A typical static safety factor is 3 to 4 on the ultimate strength in ordinary practice, and for fatigue you use an endurance approach with a much lower allowable and a stress concentration factor of about 3 for the thread root.
**Push:** What is the load the bolt actually sees in a preloaded joint? -> Only a fraction of the external load. The external load first relieves the clamp force, and only the balance goes into stretching the bolt, so with a typical joint stiffness ratio the bolt sees roughly 20 to 30 percent of the applied separating load.
**Trap:** Using the shank area for the tensile check. The thread root is smaller, and that is where the bolt would actually break.
**What they're really testing:** Whether you know that the torque you apply and the tension in the bolt are not the same thing, and that the preload does most of the work.

---

## 2. Shaft Design - 8 questions

### Q9. Design a shaft, what you're checking. [H]
**A:** Three things: Strength, from combined bending and torsion, using an equivalent twisting moment with the bending term weighted by about 0.75 for a fluctuating bending load. Stiffness, because a shaft that deflects too much ruins alignment, changes bearing preload and sets up vibration. And fatigue, since a running shaft sees fluctuating bending at the surface even if the load is steady. You start from stiffness to get a rough diameter, then check strength, then fatigue. Common materials are EN8 for general shafts, EN24 (like AISI 4140/4340) for high strength, 20MnCr5 carburised for gear shafts, nitrided steel for wear and corrosion-resistant grades where the environment is aggressive.
**Push:** Why size a shaft on stiffness first? -> Because deflection is often what actually ends the service - it causes coupling misalignment, bearing preload changes and vibration - and it is less sensitive to the load assumptions than strength is.
**Trap:** Designing on strength alone and producing a shaft that is strong but floppy and vibrating.
**What they're really testing:** Whether you can combine loads on a real shaft and know why the diameter relation is cubic, not linear.

### Q10. Shaft with bending moment M and torque T, size it. [H]
**A:** The classic route is an equivalent twisting moment, T_eq = sqrt(T^2 + (0.75 M)^2) when the bending is fluctuating or fully reversed, and sqrt(T^2 + M^2) for steady bending; the design shear stress is then tau = 16 T_eq / (pi d^3). The ASME form (B31.1 and B31.3) writes the allowable bending moment directly as M_allow = (tau_allow pi d^3) / (16 K_b), with the allowable shear stress from the code and K_b the stress concentration factor - I would confirm the exact coefficient against the code edition, but the shape of the calculation is what matters. In both cases the diameter goes as the cube root of the load, so a 10 percent load increase needs only about 3 percent more diameter.
**Push:** And where does the ASME form come from? -> It comes from the same beam and torsion relations, rearranged so that instead of finding the stress for a given moment you find the moment the section can carry. Because the pipe or shaft diameter enters as d^3 for strength and d^4 for deflection, a slightly larger diameter buys a lot.
**Trap:** Using the d^3 strength relation for deflection or the d^4 relation for stress. Deflection is much more sensitive to diameter, which is why stiffness often governs.
**What they're really testing:** Whether you can combine loads on a real shaft and know why the diameter relation is cubic, not linear.

### Q11. Key types, sizing, failure modes. [H]
**A:** The common types are the saddle key, the flat (sunk or Gib-head) key, the round key and the spline. The saddle key is the weakest - it has deep engagement but a thin section, so it crushes and wears quickly. The flat key is the standard choice because it gives a large contact area while keeping the key seat shallow. The round key is used on a tapered shaft. Splines are the strongest. You size a key by taking the shaft diameter to the standard table, which fixes the width b and height h, and then you check two failures: shearing of the key, tau = F/(b l) with the shear plane at mid-length, and crushing of the key or the hub, sigma_c = 2F/(h l) using the half of the key height that bears on the hub.
**Push:** Why is there clearance between the key and the shaft? -> So the key can be slid in and out for assembly and replacement and the hub can be positioned axially; an interference fit would need broaching after assembly. It also lets the shaft be made slightly undersize at the keyway, and remember that the keyway itself weakens the shaft, so the shaft is often stepped up by roughly 5 to 10 percent at the keyway or the reduced section is used in the fatigue check.
**Trap:** Saying a saddle key is the strongest because it sits deepest. Depth without section area gives crushing and wear, not strength.
**What they're really testing:** Whether you know the standard ways of transmitting torque and locking parts axially.

### Q12. Splines, pins and cotters. [M]
**A:** A spline is a many-toothed connection used where a key cannot carry the torque or where accurate angular positioning is needed - machine tool spindles, gear shafts, the piston rod of a hydraulic cylinder. It gives the highest torque capacity and the best angular location of the three; it is made either by milling with a cutter (flank generation) or by broaching (form generation, which is more accurate). Pins and cotters are used to lock parts axially against each other on a shaft: a taper pin is wedged in to lock two parts, and a split tapered pin called a cotter with a castellated nut is the classic way to stop a nut working loose. A taper pin fails in shear or bending, and a cotter fails by working loose or by bending, so it needs periodic checking.
**Push:** Spline or key - how do you choose? -> Splines when the torque is high, the hub must be located accurately, or the hub must slide along the shaft; a key when the torque is modest, the cost matters and axial sliding is needed.
**Trap:** Confusing a pin and a cotter with a dowel. A dowel resists shear between two parts; a pin or cotter resists axial movement of a part on a shaft.
**What they're really testing:** Whether you know the standard ways of transmitting torque and locking parts axially, and can say why each is chosen.

### Q13. Couplings: types and misalignment. [H]
**A:** Three families. Rigid couplings - flange or sleeve type - connect two shafts and take no misalignment at all; they are cheap, stiff and backlash-free, so they suit well-aligned, low-speed shafts. Flexible couplings take up misalignment: pin and bush takes angular and parallel misalignment, jaw takes angular only, grid and coil-spring take parallel misalignment, chain takes parallel and angular plus shock, and the flexible disc or double cardan takes angular, parallel and axial plus torsion. Universal couplings - Hooke's joint and the CV joint - take large angular misalignment between intersecting axes. The rule to remember: a rigid coupling takes nothing; a pin-bush or chain coupling takes angular and parallel but not much axial; only a flexible disc coupling takes all three plus twist.
**Push:** Why does a rigid coupling still fail in service? -> Misalignment. Even a small angle puts bending into the bolts and the shaft ends, and that bending is not in anyone's calculation; it is what actually cracks couplings and wears bearings.
**Trap:** Fitting a rigid flange coupling between shafts that are not perfectly aligned, or assuming a Hooke's joint is a constant-velocity joint like a CV.
**What they're really testing:** Whether you match the coupling to the misalignment you actually have, and know that rigid is not the same as good.

### Q14. Belt and chain drives: selection. [H]
**A:** Flat belt is used where pulley must be wide, where machine has to handle reverse running or act as slipping clutch, and where drive is small and cheap. V-belt transmits much more power in same space because it wedges in the pulley groove. The wedge multiplies the normal force on the belt, so effective coefficient of friction is mu / sin(alpha/2) - about 3 times mu for a 40 deg groove. V-belt can carry roughly 2 to 3 times the power of a flat belt of same width, at higher speed. Chain drives preferred in dirty, dusty or oily plant conditions because chain does not slip, can be enclosed and lubricated, and carries high torque at low speed over small centre distance.
**Push:** What is the biggest limitation of a belt drive? -> It must be kept tensioned, its life is short compared with a gear, it needs a guard, and slip means the speed ratio is never exact.
**Trap:** Using a belt where the plant atmosphere is dusty and oily - a belt slips and glazes, and the drive will not hold its ratio.
**What they're really testing:** Whether you can pick between belt and chain on the basis of the working environment.

---

## 3. Bearings and Lubrication - 10 questions

### Q25. Bearing types, load capacity, applications. [H]
**A:** Deep groove ball - general-purpose; takes radial load and moderate axial load; very low friction; speed limit ~12000-15000 rpm; used in motors, gearboxes, small machines. Cylindrical roller - higher radial capacity than ball bearing of same size, almost no axial capacity; used for heavy radial loads. Tapered roller - combined radial and axial load, mounted in pairs; used in wheel hubs and machine tool spindles. Angular contact ball - axial load in one direction, so also goes in pairs, higher speeds; used where real axial thrust exists. Spherical roller - self-aligning, heavy radial plus moderate axial, tolerant of shaft deflection and misalignment; used in conveyors and crushers. Thrust ball and thrust roller - axial load only; used in clutches, screw jacks and vertical shafts. Plain or journal bearing - sliding bearing with oil film; used for large slow heavy shafts and where shock loads are high.
**Push:** Why use a roller bearing instead of a ball bearing of the same bore? -> The roller carries more load because the line contact is much smaller than the ball contact, so the contact stress and therefore the capacity per size is higher; the price is more sliding friction and a lower limiting speed.
**Trap:** Fitting a deep groove ball bearing alone where a large axial thrust exists. It will carry some, but the axial capacity is limited and it should be paired with an angular contact or tapered roller bearing.
**What they're really testing:** Whether you can select the right bearing type for given load conditions.

### Q26. Bearing life, L10 life calculation. [H]
**A:** The catalogue life L10 is the number of revolutions, or hours at a given speed, that 90 percent of a statistically identical batch of bearings will exceed under a constant load before the first sign of metal-to-metal contact. The basic rating life is L10 = (C/P)^p, where C is the dynamic load rating - the constant load that gives one million revolutions - P is the equivalent dynamic load, and p is 3 for ball bearings and 10/3 for roller bearings. Life therefore scales with the cube of the load ratio: double P and the ball bearing life falls by a factor of 8. The modified rating life is L_nm = a1 (C/P)^p, where a1 is the reliability factor - about 1 for 90 percent reliability and higher for 95 or 99 percent.
**Push:** What is the equivalent dynamic load P? -> When a bearing carries both radial and axial load, P = X Fr + Y Fa, with X and Y taken from the catalogue for the Fa/Fr ratio and the e value. If the load is constant, P is simply that load; if it varies, you use the equivalent load with the load factors from the catalogue.
**Trap:** Using p = 3 for a roller bearing or p = 10/3 for a ball bearing. Also forgetting that L10 is a life for 90 percent of bearings, not for every bearing.
**What they're really testing:** Whether you can calculate bearing life correctly and understand what L10 means.

### Q27. Bearing mounting: rules and locating/floating arrangement. [M]
**A:** A ball or roller bearing is a hardened, thin-walled ring with raceways only a few millimetres thick, and the rolling elements are hard. Driving it on with a hammer, or pressing it on the wrong ring, sends the installation force through the rolling elements instead of through the ring, and it dents the raceway and the rollers. The damage may not show until the bearing fails in service, and it is not a warranty claim. The rules are: apply the force only to the ring being fitted - the inner ring onto the shaft, the outer ring into the housing - always through a close-fitting sleeve or a proper puller, never through the rolling elements; use induction heating for the inner ring and a cooling shrink fit for the outer ring; and check the shaft and housing fit, the shoulder height and the axial locking. On a long shaft you fix the shaft axially at one end with a locating bearing (deep groove or angular contact) and let the other bearing float (cylindrical roller, or a deep groove on a loose fit), so thermal expansion cannot over-constrain the shaft and squeeze out the internal clearance.
**Push:** What is a locating and floating bearing arrangement? -> On a long shaft you fix the shaft axially at one end with a locating bearing (deep groove or angular contact) and let the other bearing float (cylindrical roller, or a deep groove on a loose fit), so thermal expansion cannot over-constrain the shaft and squeeze out the internal clearance.
**Trap:** Assuming a bearing that goes in easily is fine. The installation damage is invisible until it fails.
**What they're really testing:** Whether you respect the bearing as a precision component - correct life calculation, correct load direction, and correct installation.

### Q28. Lubrication regimes and Sommerfeld number. [M]
**A:** Three regimes. Boundary lubrication - the surfaces are so close that the load is carried by the adsorbed molecular film and partly by the surface asperities; this is the start-up condition and the regime in a plain bearing with a marginal oil. Mixed lubrication - a partial film with some asperity contact, and this is where most machine bearings actually live. Hydrodynamic or full-film lubrication - a continuous film of oil separates the surfaces completely and the load is carried by the pressure in the film. The Sommerfeld number S = (mu/p)(r/c)^2 measures how well the film is established, and full film needs S above about 1. Journal bearings use Babbitt - tin-lead-copper-antimony - because it is soft enough to embed dust and to conform to a slightly oval or deflected journal, and it is a good anti-seizure running surface against a hardened steel shaft.
**Push:** What does the hydrodynamic film depend on? -> On a converging wedge, which needs relative motion and a converging geometry; on the viscosity of the lubricant; and on the ratio of load to clearance. Speed and viscosity build the film, load and clearance destroy it, and the whole picture is the Stribeck curve of friction against the Sommerfeld number.
**Trap:** Believing full-film lubrication means no friction. Even in the full-film regime there is shear in the oil, so the friction is lowest but not zero.
**What they're really testing:** Whether you can name the three regimes and explain the hydrodynamic film from wedge, viscosity and clearance.

### Q29. Spring types and sizing. [M]
**A:** Helical compression spring - takes a compressive load between two surfaces; the commonest spring, used in clutches, valves and suspensions. Helical extension spring - takes a tensile load, with hooks or eyes at the ends. Leaf spring - takes a bending load; the simple leaf for light duty and the laminated leaf, a stack of graduated leaves with a master leaf, for vehicles and heavy equipment, where the leaves can be combined for different loads. Belleville or disc spring - a conical dished washer taking a compressive load, used where a high load must be carried in a small space and for near-constant-force applications. Torsion spring - takes a torque, used on hinges, clutches and garage doors. The spring rate of a helical compression spring is k = G d^4 / (8 n D^3), with G the shear modulus, about 80 GPa for steel, d the wire diameter, D the mean coil diameter and n the number of active coils.
**Push:** What are the Wahl factor and surge? -> The Wahl factor K = (4C - 1)/(4C - 4) + 0.615/C, with C = D/d, corrects the simple direct-shear formula for the curvature of the wire and for the incomplete end coils. Surge is the axial resonance of a close-coiled spring when the number of active coils is small; you avoid it by increasing the active coils, by using plain or ground ends, or by keeping the helix angle low.
**Trap:** Forgetting the d^4 in the spring rate - a small change in wire diameter changes the rate drastically, which is why the wire size, not the coil diameter, is the sensitive variable.
**What they're really testing:** Whether you know the spring families and their loads, and can connect the geometry of a leaf pack to the force-deflection behaviour.

### Q30. Leaf spring eye and vehicle arrangement. [L]
**A:** The eye locates the spring in a shackle or hanger and lets the spring pack be removed without disturbing the rest; it also lets the pack change its length slightly under load so the leaves can slide against each other. In a semi-elliptic spring the leaves are curved and both ends are fixed to the chassis - a full-elliptic spring has an eye at each end and shares the load better. The leaves are stacked with the longest leaf, the master leaf, in the middle or on top and the shorter ones above and below, all clamped by a centre bolt, and the graduated lengths give progressive springing: as the spring deflects, the shorter leaves come into contact one by one, so the rate increases. That gives a soft ride under light load and a firm rate under heavy load in one component.
**Push:** Why is the master leaf given a greater thickness? -> It is the leaf that carries the load when the spring is nearly flat, and it is the one that takes the full deflection, so it is thicker and it is the one that can break and can be replaced.
**Trap:** Believing a leaf spring carries a constant force. The load rises as it deflects because the leaves engage progressively.
**What they're really testing:** Whether you know the spring families and their loads, and can connect the geometry of a leaf pack to the force-deflection behaviour.

---

## 4. Fasteners and Preloading - 6 questions

### Q31. Why tighten a bolt to specified torque. [H]
**A:** A bolted joint works by preload, the clamp force generated when the bolt is tightened. The joint separates only when the external separating load exceeds the preload, and the preload also stops the joint slipping and prevents fatigue at the interface. Preload is set by torque through the thread friction: T = K F d, where K is the nut factor, about 0.2 for a clean lubricated steel bolt, F is the preload and d the nominal diameter. So a large fraction of what you apply with a wrench is lost to thread friction rather than going into stretching the bolt - which is why you always tighten to the same specified torque with the same lubrication. If you overtighten, the bolt can yield and then fail in fatigue, the thread can strip, or the clamped part can be crushed; because the torque-to-preload relation is so uncertain, the rule is to tighten to the specified value and never exceed it.
**Push:** How is the preload calculated or verified? -> The torque method is the everyday one, but the better methods are the turn-of-nut method, a defined fraction of an extra turn after snug tight, and the direct tension method, measuring the bolt stretch with a strain gauge or by ultrasound. For a preloaded bolt the target is typically around 70 to 90 percent of the proof strength times the tensile stress area, and you would use the code value for the bolt class.
**Trap:** Believing tightening harder always clamps better. Beyond a point you only reduce the margin against fatigue failure of the bolt.
**What they're really testing:** Whether you know that the torque you apply and the tension in the bolt are not the same thing, and that the preload does most of the work.

### Q32. Threaded fastener design for tensile and shear. [M]
**A:** You keep the threads in tension and the shank in shear clearly separated. In tension you use the tensile stress area, about 0.79 d^2 for an ISO metric coarse thread, not the shank area, and the limit is either the proof strength of the bolt or thread stripping in the tapped material if that is the weaker one. In shear you use the shank area pi d^2/4 and the shear strength of the bolt, commonly taken as about 0.6 times the tensile strength, with the proviso that if the threads lie in the shear plane you must use the tensile stress area instead. A typical static safety factor is 3 to 4 on the ultimate strength in ordinary practice, and for fatigue you use an endurance approach with a much lower allowable and a stress concentration factor of about 3 for the thread root.
**Push:** What is the load the bolt actually sees in a preloaded joint? -> Only a fraction of the external load. The external load first relieves the clamp force, and only the balance goes into stretching the bolt, so with a typical joint stiffness ratio the bolt sees roughly 20 to 30 percent of the applied separating load.
**Trap:** Using the shank area for the tensile check. The thread root is smaller, and that is where the bolt would actually break.
**What they're really testing:** Whether you know that the torque you apply and the tension in the bolt are not the same thing, and that the preload does most of the work.

### Q33. Bolt grade and material selection. [M]
**A:** Bolt grades: Class 4.6 (low strength), 8.8 (medium-high, common for structural), 10.9 (high strength), 12.9 (very high strength). The first number is tensile strength/100 (e.g., 8.8 = 800 MPa tensile), the second is yield/tensile ratio (0.8 = 80% yield). Material selection: carbon steel for general use, alloy steel for high strength, stainless for corrosion resistance, brass for electrical conductivity. Corrosion protection: galvanising, cadmium plating, stainless steel.
**Push:** What does bolt grade 8.8 mean? -> 800 MPa ultimate tensile strength, 0.8 yield ratio (640 MPa yield). Common for structural bolts in steel construction.
**Trap:** Saying higher grade is always better - higher grade bolts are more brittle and require more careful installation.
**What they're really testing:** Whether you can read bolt grades and select appropriate material for the application.

### Q34. Riveted joints: types and efficiency. [L]
**A:** Riveted joints: permanent joints using rivets. Types: lap joint (plates overlap, single or double riveted), butt joint (plates butted, cover plates on one or both sides). Efficiency = strength of joint / strength of solid plate. Double riveted lap joint efficiency ~70%, single riveted ~50%. Rivets are being replaced by welding and bolting but still used in aircraft (aluminium rivets) and shipbuilding.
**Push:** Why are rivets being replaced? -> Welding and bolting are faster, cheaper, and easier to inspect. Riveting requires access to both sides and skilled labour.
**Trap:** Saying riveted joints are as strong as welded joints - riveted joints have lower efficiency due to holes weakening the plate.
**What they're really testing:** Whether you know riveted joint types and can compare them to welding and bolting.

### Q35. Welded joints: types and design. [M]
**A:** Welded joints: permanent joints using fusion welding. Types: butt weld (plates aligned, weld across thickness), fillet weld (triangular cross-section, weld along edges), lap weld (plates overlap, weld along edges). Design: butt weld strength = weld area * allowable stress. Fillet weld strength = throat area * allowable shear stress (throat = 0.707 * leg size for 45 deg fillet). Welded joints are more efficient than riveted (no holes) but have residual stresses and heat affected zone.
**Push:** What is the throat of a fillet weld? -> The shortest distance from the root to the face of the weld. For a 45 deg fillet with leg size 'a', throat = 0.707*a.
**Trap:** Designing fillet weld by leg size instead of throat area - the throat is the critical section.
**What they're really testing:** Whether you can design welded joints and understand the strength calculation.

---

## 5. Shaft, Coupling, and Belt Design - 10 questions

### Q36. Shaft diameter from combined bending and torsion. [H]
**A:** Design shaft using equivalent torque: T_eq = sqrt(T^2 + (K_b*M)^2) where K_b = 1.5-2.0 for fluctuating bending. Then d = (16*T_eq/(pi*tau_allow))^(1/3). Or use ASME code: tau_allow = 0.3*sigma_y or 0.18*UTS (whichever is lower) for shafts without keyways; reduce by 25% for keyways. Check deflection: theta = T*L/(G*J) < 0.5 deg/m for precision shafts.
**Push:** Why reduce allowable stress for keyways? -> Keyway creates stress concentration (Kt ~ 2-2.5) at the shaft surface, reducing fatigue strength.
**Trap:** Designing on strength alone - deflection often governs for long shafts.
**What they're really testing:** Whether you can design a shaft for combined loading.

### Q37. Key design: shear and crushing. [H]
**A:** Key transmits torque between shaft and hub. Design checks: (1) Shear: tau = 2*T/(d*L*b) <= tau_allow (shear plane through key mid-height). (2) Crushing: sigma_c = 4*T/(d*L*h) <= sigma_allow (crushing on key sides). Key dimensions from standard tables based on shaft diameter. Common types: (1) Sunk key (rectangular), (2) Gib-head key (tapered, for easy removal), (3) Woodruff key (semicircular, for tapered shafts).
**Push:** What is the standard key width for a 50 mm shaft? -> Typically 14 mm wide x 9 mm high (from IS 2048 / ASME B17.1 tables).
**Trap:** Checking only shear - crushing often governs for short keys.
**What they're really testing:** Whether you can design keys for torque transmission.

### Q38. Coupling selection for different conditions. [H]
**A:** Selection criteria: (1) Rigid coupling (flange, sleeve) - for perfect alignment, no misalignment. (2) Flexible coupling (pin-bush, jaw, grid) - for angular/parallel misalignment. (3) Universal joint (Hooke's) - for large angular misalignment. (4) CV joint - for constant velocity at large angles. (5) Fluid coupling - for smooth start, overload protection. Consider: torque, speed, misalignment, shock, environment, maintenance access.
**Push:** When would you use a fluid coupling? -> For smooth acceleration, overload protection, and isolating torsional vibrations. Common in conveyors, crushers, and marine drives.
**Trap:** Using rigid coupling with misaligned shafts - causes bearing failure and coupling cracking.
**What they're really testing:** Whether you can select the right coupling for given conditions.

### Q39. Belt drive: power transmission calculation. [H]
**A:** Belt power: P = (T1 - T2) * v, where T1 = tight side tension, T2 = slack side tension, v = belt velocity. Tension ratio: T1/T2 = e^(mu*theta). Maximum tension: T1 = sigma_allow * A (belt cross-section). Centrifugal tension: Tc = rho * A * v^2. Design: (1) Select belt type (V-belt for compact, flat belt for high speed), (2) Calculate tensions, (3) Check belt life, (4) Select pulley diameters (minimum bend radius).
**Push:** Why is V-belt preferred over flat belt? -> V-belt wedges in groove, multiplying normal force and friction. Transmits 2-3x more power in same space.
**Trap:** Ignoring centrifugal tension - at high speeds, Tc can exceed T1, causing belt to lift off pulley.
**What they're really testing:** Whether you can design a belt drive for power transmission.

### Q40. Bearing selection: load, speed, life. [H]
**A:** Selection: (1) Deep groove ball - general purpose, moderate load, high speed. (2) Cylindrical roller - high radial load, no axial. (3) Tapered roller - combined radial+axial, wheel hubs. (4) Angular contact ball - high axial, high speed. (5) Spherical roller - self-aligning, heavy load. (6) Needle roller - compact, oscillating. L10 life = (C/P)^p million revs (p=3 ball, 10/3 roller). Consider: (a) Load type (radial/axial), (b) Speed, (c) Life requirement, (d) Space constraints, (e) Cost.
**Push:** How do you calculate equivalent dynamic load P? -> P = X*Fr + Y*Fa, where X, Y from bearing catalogue based on Fa/Fr ratio and e value.
**Trap:** Selecting bearing based only on bore size - must consider load type, speed, and life.
**What they're really testing:** Whether you can select bearings for given load conditions.

### Q41. Spring design: helical compression spring. [H]
**A:** Spring rate: k = G*d^4/(8*n*D^3). Stress: tau = K*8*F*D/(pi*d^3), where K = Wahl factor = (4C-1)/(4C-4) + 0.615/C, C = D/d. Design: (1) Select wire diameter d from stress, (2) Calculate coils n from rate, (3) Check buckling (L/D < 4 for compression springs), (4) Select end type (plain, ground, squared). Material: music wire (small, high stress), oil-tempered (general), chrome-silicon (high fatigue).
**Push:** What is the Wahl factor and why is it needed? -> Corrects for curvature stress and direct shear in helical springs. Without it, stress is underestimated by 10-30%.
**Trap:** Forgetting the d^4 in spring rate - small change in wire diameter drastically changes stiffness.
**What they're really testing:** Whether you can design a helical spring.

### Q42. Leaf spring design for vehicles. [M]
**A:** Leaf spring: laminated spring with graduated leaves. Design: (1) Master leaf (longest, thickest) carries full load at small deflection. (2) Shorter leaves engage progressively as deflection increases (progressive springing). (3) Bending stress: sigma = 6*M/(b*t^2) where M = F*L/4 (for semi-elliptic). (4) Camber provides initial clearance. (5) Eye at ends for mounting. (6) Centre bolt clamps leaves, U-bolts attach to axle.
**Push:** Why is progressive springing desirable in vehicles? -> Soft ride under light load (comfort), firm rate under heavy load (handling and ground clearance).
**Trap:** Treating leaf spring as linear - rate increases with deflection due to progressive engagement.
**What they're really testing:** Whether you understand leaf spring design and progressive springing.

### Q43. Belleville (disc) spring applications. [M]
**A:** Belleville spring: conical dished washer, high spring rate in small space. Characteristics: (1) Non-linear force-deflection (nearly constant force over large deflection range). (2) Can be stacked in series (more deflection) or parallel (more load). (3) Used for: bolt preload maintenance, clutch springs, valve springs, safety valves. (4) Load: F = (4*E*t^3/(D^2*(1-nu^2))) * (h - delta) * (h - delta/2) * delta / (D^2).
**Push:** Why is Belleville spring ideal for bolt preload? -> Nearly constant force over large deflection range, so bolt relaxation doesn't significantly reduce clamping force.
**Trap:** Thinking Belleville spring has linear rate like helical spring - it has complex non-linear characteristic.
**What they're really testing:** Whether you understand Belleville spring characteristics.

### Q44. Fastener preload and joint stiffness. [H]
**A:** Preloaded bolted joint: external load first reduces clamp force, then stretches bolt. Bolt load = preload + (external load * bolt stiffness / (bolt + joint stiffness)). Typical joint stiffness ratio: bolt sees 20-30% of external load. Preload target: 70-90% of proof strength. If external load exceeds preload, joint separates (failure). Preload prevents: (1) Joint separation, (2) Slipping, (3) Fatigue (no alternating stress if preload > external load).
**Push:** Why does preload prevent fatigue failure? -> If preload exceeds external load, bolt stress doesn't alternate - fatigue requires alternating stress. Preload keeps bolt in tension always.
**Trap:** Thinking tightening harder always helps - over-tightening yields bolt, reducing fatigue life.
**What they're really testing:** Whether you understand bolted joint mechanics and preload.

### Q45. Welded joint design: fillet and butt welds. [M]
**A:** Fillet weld: triangular cross-section, strength based on throat area. Throat = 0.707 * leg (for 45 deg). Shear stress = F / (throat * length). Butt weld: strength = weld area * allowable stress (full penetration) or throat area (partial penetration). Design: (1) Match weld strength to base metal, (2) Avoid stress concentration (smooth transitions), (3) Consider fatigue (weld toe is stress riser). Weld size selection based on: plate thickness, load, and code requirements.
**Push:** What is the minimum fillet weld size for a 10 mm plate? -> Typically 3-5 mm for thin plates, increasing with thickness. AWS D1.1 specifies minimum sizes.
**Trap:** Designing fillet weld by leg size instead of throat - throat is the critical section.
**What they're really testing:** Whether you can design welded joints.

---

## 6. Springs - 6 questions

## 6. Springs - 6 questions

### Q48. Belleville (disc) spring. [M]
**A:** Belleville spring is a conical dished washer that takes compressive load. It provides very high spring rate in a small space. Used in clutches, valves, and where high load in limited space is needed. Spring rate is non-linear - nearly constant force over large deflection range (ideal for maintaining preload in bolted joints). Can be stacked in series (for more deflection) or parallel (for more load).
**Push:** Why is Belleville spring good for maintaining bolt preload? -> Because its force-deflection curve is nearly flat over a large range, so even if the bolt relaxes slightly, the spring force stays nearly constant.
**Trap:** Thinking Belleville spring has linear spring rate like a helical spring - it has a complex non-linear characteristic.
**What they're really testing:** Whether you understand Belleville spring characteristics and applications.

### Q49. Torsion spring. [M]
**A:** Torsion spring takes torque, used on hinges, clutches and garage doors. Spring rate k = E*d^4/(384*D*N) for rectangular wire, or k = G*d^4/(64*N*D) for round wire (where N = number of active coils, D = mean diameter). Torque T = k*theta (angle of twist in radians). End configurations: hooks, loops, straight ends. Must be designed for bending stress in the wire, not torsion.
**Push:** What is the failure mode of a torsion spring? -> The wire fails in bending at the point of maximum bending stress, usually near the end where the load is applied.
**Trap:** Designing a torsion spring for torsional stress - it fails in bending, so bending stress is the design criterion.
**What they're really testing:** Whether you understand torsion spring design and failure mode.

### Q50. Spring material selection. [M]
**A:** Spring materials: music wire (high strength, good for small springs, ASTM A228), oil-tempered (medium strength, general purpose, ASTM A229), chrome-vanadium (high strength, high temperature, ASTM A231), chrome-silicon (very high strength, fatigue resistance, ASTM A401), stainless (corrosion resistance, lower strength). Selection based on: strength requirement, fatigue life, temperature, corrosion environment, cost. Music wire for small, high-stress springs; oil-tempered for general purpose; chrome-silicon for high-cycle fatigue.
**Push:** Why is music wire not used for high-temperature springs? -> Music wire loses strength above ~120 deg C. Chrome-silicon or chrome-vanadium are used for high-temperature applications.
**Trap:** Using music wire for high-temperature or corrosive environments - it has excellent fatigue strength but poor temperature and corrosion resistance.
**What they're really testing:** Whether you can select spring material based on application requirements.

---

## File Statistics

**Total questions: 37**

**By tag:**
- [H] High-yield: ~22 questions
- [M] Medium-yield: ~22 questions
- [L] Occasional: ~6 questions

**By section:**
- Design process and philosophy: 8 questions
- Shaft design: 8 questions
- Gears and gear trains: 10 questions
- Bearings and lubrication: 10 questions
- Fasteners and preloading: 6 questions
- Springs: 6 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, G=80 GPa, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers Machine Design - essential for automobiles, petrochem, and construction interviews.