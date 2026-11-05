# Machine Design - L&T GET technical interview bank

**Part 5 of 8 | 30 questions | Design process, fatigue, shafts, keys, couplings, belts, chains, gears, bearings, lubrication, springs, fasteners**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly,
[L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you
cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing
recall, they are testing whether you can reason out loud.*

---

## 1. Design philosophy and the design process - 3 questions

### Q1. Walk me through how you actually design a component, from the requirement to the finished drawing. [H]

**A:** A design engineer converts a requirement into a drawing that someone can make and that survives its duty. The sequence is: (1) fix the requirements - function, load, environment, life, cost, applicable standards; (2) estimate the loads, static, dynamic, fatigue and the worst credible case; (3) choose the material from strength, corrosion, heat and wear; (4) get a preliminary size from simple stress or stiffness relations; (5) do the detailed analysis, hand calculation with stress concentration and deflection, or FEA; (6) fix the factor of safety and check every likely failure mode; (7) consider manufacture - machining, welding, standard stock; (8) issue the drawing with tolerances, fits and surface finish; (9) prototype; (10) test and prove it, then modify.

**Push:** "Where do standard parts fit into this?" - At steps 3 to 7 you check whether an off-the-shelf bearing, fastener, coupling or motor already does the job, because using it cuts cost, lead time and risk.

**Trap:** "The last step is submitting the drawing." A design that was never prototyped and tested is not a finished design; proving it is part of the job.

### Q2. What is the difference between stress-based and strain-based design? And what exactly is an allowable stress? [H]

**A:** In stress-based design the working stress must stay below an allowable stress, which is the material strength divided by a factor of safety, and that is what most codes use. In strain-based design you check the actual stress and strain against the real stress-strain curve with a limit on each, so the material is used far more efficiently and the failure mode can be predicted. ASME Section VIII Division 1 is the allowable-stress route for ordinary pressure vessels, Division 2 is the strain-based route used for higher pressures, complex shapes, fatigue or creep. An allowable stress is simply the limiting stress you may not exceed.

**Push:** "When would you use Division 2?" - For higher allowable stress, complex geometry or where you need fatigue and creep analysis to exploit the material; you pay with much heavier analysis and fabrication control, so Division 1 stays the default.

**Trap:** Calling allowable stress the same as yield strength. It is yield (or ultimate for a brittle material) divided by the code factor of safety - 3.5 on yield in ASME VIII Division 1, which you confirm against the edition you are using.

### Q3. How do you choose the factor of safety for a real part? Is it always 3? [H]

**A:** No. The factor of safety covers uncertainty in the loads, in the material properties and in manufacturing, and it depends on how bad the failure would be. For a ductile steel bracket under static load, 2 to 3 is normal; for a casting, a weldment or anything with a sharp stress raiser, go higher, 3 to 4; for pressure parts the code fixes it, 3.5 on yield in ASME VIII Division 1. Brittle material needs more because it fails without warning. For fatigue you do not use one factor on the strength - you take an allowable amplitude from the S-N curve with roughly 1.5 to 2 on top.

**Push:** "How is the factor of safety different for a crane hook and for a pressure vessel?" - A pressure vessel gets the code value because a leak can kill people and the loads are well characterised; a crane hook gets more because the load range and shock are less predictable and the material must be very clean.

**Trap:** Quoting one universal value of 3. The interviewer wants to hear that it is a judgement about consequences, load uncertainty and material uniformity.

**What they're really testing:** Whether you treat design as a sequence with decisions and trade-offs, or as a formula you apply at the end.

---

## 2. Fatigue and the S-N curve - 4 questions

### Q4. Explain the S-N curve and the endurance limit. [H]

**A:** The S-N or Wohler curve plots stress amplitude S against the number of cycles N to failure, usually on log-log axes, for a small polished test specimen. For steels the curve bends over and flattens into a horizontal line - the endurance limit or fatigue strength - below which the material survives unlimited cycles. A rule of thumb for steel is about half the ultimate tensile strength in MPa, roughly 450 MPa for a 900 MPa steel, but you take the real value from the handbook for the actual material. Aluminium and most other non-ferrous metals have no true endurance limit, so you state a design life and read the curve at that life.

**Push:** "How do you get from the laboratory endurance limit to the real part?" - You apply the Marin factors - size, surface finish, load, temperature and reliability - which multiply down to the actual endurance limit of the component.

**Trap:** Using the laboratory endurance limit directly for the real part. The real part always has a lower value, and aluminium has no endurance limit at all.

### Q5. In which situations can you not use the endurance limit? [H]

**A:** Four important ones. Welded joints - the weld toe is a notch with high residual tensile stress, so fatigue cracks start there at stresses well below the parent metal's endurance limit, and you use a fatigue category from the welding code instead. Low-cycle fatigue, below roughly 10^4 to 10^5 cycles, where local yielding occurs at the notch and you need a strain-life (Coffin-Manson) approach. High temperature, where creep and oxidation govern rather than fatigue, and you check against allowable stress at temperature and creep rupture. And corrosive or erosive service, where the endurance limit does not exist because the curve keeps falling with life.

**Push:** "Which of these dominates on a power plant site?" - Combined corrosion and fatigue in humid or coastal plants, and creep in steam lines and boilers at high temperature.

**Trap:** Assuming the S-N curve is valid for welded joints and for anything running at 500 deg C.

### Q6. What is the difference between the theoretical stress concentration factor Kt and the fatigue stress concentration factor Kf? [M]

**A:** Kt is purely geometric - the ratio of peak elastic stress at a notch to the nominal stress - and depends only on the notch shape. For static failure, or ductile yielding, the material redistributes and you use Kt (or Neuber's rule for local yielding). In fatigue only part of the notch is actually felt, so you use the fatigue stress concentration factor Kf = 1 + q(Kt - 1), where q is the notch sensitivity between 0 and 1. You apply Kf to the nominal alternating stress when you build the S-N picture, and you get q from a chart of notch sensitivity against notch radius and material strength.

**Push:** "How do you reduce Kt in practice?" - Increase the fillet radius, avoid sharp internal corners, add a relief groove, and use radii that are generous relative to the section. A large fillet radius is the cheapest fatigue improvement available.

**Trap:** Treating Kt and Kf as the same number, or using Kt for a fatigue calculation.

### Q7. What is the mean stress effect? Explain the Goodman and Gerber diagrams and when you use each. [M]

**A:** A component under fluctuating load has a mean stress part and an alternating part, and a tensile mean stress shortens fatigue life while a compressive mean stress can lengthen it. The Goodman diagram plots allowable alternating stress against mean stress for a specified life, with a straight line joining the yield intercept and the endurance-limit intercept - the safe region is below that line and the method is conservative. The Gerber parabola is fitted through the same two intercepts but bulges outward, so it predicts more life and is less pessimistic. Goodman is the standard conservative choice; Gerber is used when you have good fatigue data and want a less pessimistic answer.

**Push:** "Which do you use for a rotating shaft with fully reversed bending?" - Fully reversed means zero mean stress, so both give the same allowable amplitude; the mean-stress correction only matters when the load is not symmetric.

**Trap:** Thinking the Gerber parabola is the conservative one. It is the optimistic one; Goodman is conservative.

**What they're really testing:** Whether you know that fatigue is a life problem, not a strength problem, and can quantify the two corrections that make a real component different from a lab specimen.

---

## 3. Shaft design - 2 questions

### Q8. How do you design a shaft? What exactly are you checking? [H]

**A:** Three things. Strength, from combined bending and torsion, using an equivalent twisting moment with the bending term weighted by about 0.75 for a fluctuating bending load. Stiffness, because a shaft that deflects too much ruins alignment, changes bearing preload and sets up vibration. And fatigue, since a running shaft sees fluctuating bending at the surface even if the load is steady. You start from stiffness to get a rough diameter, then check strength, then fatigue. Common materials are EN8 for general shafts, EN24 (like AISI 4140/4340) for high strength, 20MnCr5 carburised for gear shafts, nitrided steel for wear and corrosion-resistant grades where the environment is aggressive.

**Push:** "Why size a shaft on stiffness first?" - Because deflection is often what actually ends the service - it causes coupling misalignment, bearing preload changes and vibration - and it is less sensitive to the load assumptions than strength is.

**Trap:** Designing on strength alone and producing a shaft that is strong but floppy and vibrating.

### Q9. A shaft carries a bending moment M and a torque T. How do you size it, and what does the ASME code form look like? [H]

**A:** The classic route is an equivalent twisting moment, T_eq = sqrt(T^2 + (0.75 M)^2) when the bending is fluctuating or fully reversed, and sqrt(T^2 + M^2) for steady bending; the design shear stress is then tau = 16 T_eq / (pi d^3). The ASME form (B31.1 and B31.3) writes the allowable bending moment directly as M_allow = (tau_allow pi d^3) / (16 K_b), with the allowable shear stress from the code and K_b the stress concentration factor - I would confirm the exact coefficient against the code edition, but the shape of the calculation is what matters. In both cases the diameter goes as the cube root of the load, so a 10 percent load increase needs only about 3 percent more diameter.

**Push:** "And where does the ASME form come from?" - It comes from the same beam and torsion relations, rearranged so that instead of finding the stress for a given moment you find the moment the section can carry. Because the pipe or shaft diameter enters as d^3 for strength and d^4 for deflection, a slightly larger diameter buys a lot.

**Trap:** Using the d^3 strength relation for deflection or the d^4 relation for stress. Deflection is much more sensitive to diameter, which is why stiffness often governs.

**What they're really testing:** Whether you can combine loads on a real shaft and know why the diameter relation is cubic, not linear.

---

## 4. Keys, splines, pins and cotters - 2 questions

### Q10. What types of keys are there, which is strongest, how do you size one, and how does a key fail? [H]

**A:** The common types are the saddle key, the flat (sunk or Gib-head) key, the round key and the spline. The saddle key is the weakest - it has deep engagement but a thin section, so it crushes and wears quickly. The flat key is the standard choice because it gives a large contact area while keeping the key seat shallow. The round key is used on a tapered shaft. Splines are the strongest. You size a key by taking the shaft diameter to the standard table, which fixes the width b and height h, and then you check two failures: shearing of the key, tau = F/(b l) with the shear plane at mid-length, and crushing of the key or the hub, sigma_c = 2F/(h l) using the half of the key height that bears on the hub. Some handbooks write the double-shear forms 2F/(b l) and 4F/(h l) - the geometry decides, and you state your assumption.

**Push:** "Why is there a clearance between the key and the shaft?" - So the key can be slid in and out for assembly and replacement and the hub can be positioned axially; an interference fit would need broaching after assembly. It also lets the shaft be made slightly undersize at the keyway, and remember that the keyway itself weakens the shaft, so the shaft is often stepped up by roughly 5 to 10 percent at the keyway or the reduced section is used in the fatigue check.

**Trap:** Saying a saddle key is the strongest because it sits deepest. Depth without section area gives crushing and wear, not strength.

### Q11. What are splines, pins and cotters used for, and how do they fail? [M]

**A:** A spline is a many-toothed connection used where a key cannot carry the torque or where accurate angular positioning is needed - machine tool spindles, gear shafts, the piston rod of a hydraulic cylinder. It gives the highest torque capacity and the best angular location of the three; it is made either by milling with a cutter (flank generation) or by broaching (form generation, which is more accurate). Pins and cotters are used to lock parts axially against each other on a shaft: a taper pin is wedged in to lock two parts, and a split tapered pin called a cotter with a castellated nut is the classic way to stop a nut working loose. A taper pin fails in shear or bending, and a cotter fails by working loose or by bending, so it needs periodic checking.

**Push:** "Spline or key - how do you choose?" - Splines when the torque is high, the hub must be located accurately, or the hub must slide along the shaft; a key when the torque is modest, the cost matters and axial sliding is needed.

**Trap:** Confusing a pin and a cottter with a dowel. A dowel resists shear between two parts; a pin or cotter resists axial movement of a part on a shaft.

**What they're really testing:** Whether you know the standard ways of transmitting torque and locking parts axially, and can say why each is chosen.

---

## 5. Couplings - 1 question

### Q12. What types of couplings are there, what does each one handle, and which ones must never be misaligned? [H]

**A:** Three families. Rigid couplings - flange or sleeve type - connect two shafts and take no misalignment at all; they are cheap, stiff and backlash-free, so they suit well-aligned, low-speed shafts. Flexible couplings take up misalignment: pin and bush takes angular and parallel misalignment, jaw takes angular only, grid and coil-spring take parallel misalignment, chain takes parallel and angular plus shock, and the flexible disc or double cardan takes angular, parallel and axial plus torsion. Universal couplings - Hooke's joint and the CV joint - take large angular misalignment between intersecting axes. The rule to remember: a rigid coupling takes nothing; a pin-bush or chain coupling takes angular and parallel but not much axial; only a flexible disc coupling takes all three plus twist.

**Push:** "Why does a rigid coupling still fail in service?" - Misalignment. Even a small angle puts bending into the bolts and the shaft ends, and that bending is not in anyone's calculation; it is what actually cracks couplings and wears bearings. Also, a Hooke's joint gives a velocity fluctuation at high speed and is limited to small angles, while the CV joint runs at constant velocity and handles larger angles.

**Trap:** Fitting a rigid flange coupling between shafts that are not perfectly aligned, or assuming a Hooke's joint is a constant-velocity joint like a CV.

**What they're really testing:** Whether you match the coupling to the misalignment you actually have, and know that rigid is not the same as good.

---

## 6. Belt and chain drives - 3 questions

### Q13. Flat belt versus V-belt - why has the V-belt replaced the flat belt, and when would you still use a flat belt? [H]

**A:** A V-belt transmits much more power in the same space because it wedges in the pulley groove. The wedge multiplies the normal force on the belt, so the effective coefficient of friction is mu / sin(alpha/2) - about 3 times mu for a 40 deg groove - and a V-belt can carry roughly 2 to 3 times the power of a flat belt of the same width, at higher speed, because it sits deeper and will not creep off the pulley. A flat belt is still used where the pulley must be wide, where the machine has to handle reverse running or act as a slipping clutch, and where the drive is small and cheap. Both have the same weakness: they need tensioning and they slip.

**Push:** "What is the biggest limitation of a belt drive?" - It must be kept tensioned, its life is short compared with a gear, it needs a guard, and slip means the speed ratio is never exact.

**Trap:** Saying the V-belt works by friction on the bottom of the belt. The bottom is not in contact - it is the side faces of the V that wedge.

### Q14. Explain open, crossed and quartered belt drives. What are velocity ratio, slip and creep, and how do you calculate the belt length? [M]

**A:** In an open drive both pulleys rotate the same way and the belt is a few percent shorter; in a crossed drive the belt crosses over so the pulleys rotate in opposite ways, but the crossed belt is longer, needs more tension and wears faster; in a quartered drive the pulleys rotate in opposite ways with the belt twisted through a quarter turn, used when the shafts must be moved apart, at the cost of rapid belt wear. Velocity ratio = N1/N2 = D2/D1. Slip is the ratio error from insufficient friction, around 2 to 5 percent, and creep is the elastic stretch of the belt around the pulley, which gives only about 0.1 to 0.2 percent error on the small pulley. Belt length is L = 2C + (pi/2)(D + d) + (D - d)^2/(4C), with C the centre distance and D and d the pulley diameters.

**Push:** "How do you set the belt tension?" - By the sag rule: a belt should sag about 1 to 2 percent of the span, or you use a tension gauge and check the force on the slack side after a run-in period. The correct tension is the minimum that will not slip, and too much tension is just as bad because it wears the belt and the bearings.

**Trap:** Believing creep is the same as slip. Slip is a friction loss that is avoidable, creep is elastic and unavoidable.

### Q15. Tell me about roller chain drives - pitch, sprocket, lubrication - and when do you prefer a chain to a belt? [M]

**A:** A roller chain is identified by its pitch: 08B-1 has a pitch of 12.7 mm and ANSI 40 chain has the same half-inch pitch, and the sprocket teeth are cut to match, with pitch circle diameter D = p / sin(180/Z). The chain pull comes from the power - the standard textbook relation is T1 - T2 = 1025 P newtons with P in kW, so 5 kW needs about 5.1 kN across the chain. Lubrication depends on chain speed: grease below about 1.5 m/s, drip oil up to about 6 m/s, and an oil bath or spray above that. You prefer a chain to a belt in dirty, dusty or oily plant conditions, because the chain does not slip, can be enclosed and lubricated, and carries high torque at low speed over a small centre distance. The price is noise, weight, sprocket wear and the need for lubrication.

**Push:** "How does a silent chain differ from a roller chain?" - A silent or block chain has the teeth engaging in the pockets of a nearly continuous plate, so it is quieter, runs faster and needs less lubrication, but it is heavier and costlier.

**Trap:** Using a belt where the plant atmosphere is dusty and oily - a belt slips and glazes, and the drive will not hold its ratio.

**What they're really testing:** Whether you can pick between belt and chain on the basis of the working environment, and whether you know the numbers that drive the choice.

---

## 7. Gears: types, geometry and ratios - 3 questions

### Q16. What types of gears do you know, and where is each one used? [H]

**A:** Spur gear - straight teeth on a cylindrical shaft with parallel axes; the simplest and cheapest, used for low speed and general duty. Helical gear - teeth inclined to the axis, parallel axes; smoother, quieter and higher capacity because more teeth share the load, but it generates axial thrust that needs a thrust bearing, so it is used in high-speed gearboxes and in vehicle gearboxes. Bevel gear - conical, for shafts that intersect, typically at 90 deg. Worm - a screw driving a wheel, for very high ratios in a compact package, self-locking, but low efficiency and it generates heat. Planetary - sun, planets and ring, all coaxial, a very high ratio in one stage, used in automatic transmissions and in coaxial reduction boxes. Rack and pinion - converts rotation to linear motion, used in machine tools and actuators.

**Push:** "Why do helical gears generate axial thrust?" - Because the tooth force has a component along the axis, proportional to the helix angle; you must support that with a thrust bearing or a properly preloaded pair.

**Trap:** Believing helical gears are always more efficient than spur. They are smoother and quieter, but the axial thrust and the extra sliding loss mean they are not automatically more efficient.

### Q17. Explain module, pressure angle, pitch circle, addendum and dedendum. What is the relation between module and pitch diameter? [H]

**A:** The module m is the tooth size and it is the thing you actually specify, since the pitch diameter comes out of it: m = d/Z, so d = m Z. Two meshing gears must have the same module, and that plus the tooth numbers fixes the centre distance a = m(Z1 + Z2)/2. The pressure angle is the angle between the line of action and the common tangent at the pitch point; 20 deg is the standard because it gives a good balance between tooth force and bearing force. The pitch circle is the imaginary circle of radius d/2 whose circumference carries the circular pitch pi m. The addendum is the tooth height above the pitch circle, normally 1.0 m, and the dedendum is the depth below it, normally 1.25 m, so the whole depth is about 2.25 m.

**Push:** "Why 20 deg and not 25 deg?" - A higher pressure angle reduces the tooth force for the same torque, which reduces bearing load, but it increases the contact ratio and makes the teeth thinner at the root, so the tooth root becomes weaker and more sensitive to root stress. 20 deg is the compromise that suits most general machinery.

**Trap:** Trying to design a gear by choosing a pitch diameter. You choose the module and the number of teeth.

### Q18. What is the gear ratio? Explain direction of rotation and torque multiplication. [H]

**A:** The gear ratio is i = N1/N2 = Z2/Z1 = d2/d1, the speed of the driver over the speed of the driven. If the driver has fewer teeth than the driven, the driven turns slower and the torque is multiplied; power is conserved, so T2 = T1 times i ignoring losses, and every multiplication of speed or torque is paid for in efficiency. Each external mesh reverses the direction, so an idler between two gears gives back the original direction; an internal gear keeps the same direction, and in a planetary the direction depends on which member is held. Unlike a belt, the gear ratio is exact - there is no slip, so speed and position are repeatable.

**Push:** "Then how do you get a reduction of 20:1?" - You cannot do it in one pair without a very small pinion; you use a compound train so the overall ratio is the product of two or more pair ratios, or a worm, or a planetary.

**Trap:** Confusing gear ratio with the ratio of diameters only and forgetting the tooth numbers, or assuming the torque increase is free.

**What they're really testing:** Whether you can size a drive from the ratio and the torque without losing the direction of rotation or the power balance.

---

## 8. Gear design: tooth strength and special gears - 2 questions

### Q19. How do you calculate the bending stress in a gear tooth? Explain the Lewis equation. [H]

**A:** The Lewis equation estimates the bending stress at the tooth root: sigma = Wt K Ks Kv Kg / (b m Y), where Wt is the tangential load, b the face width, m the module, Y the Lewis form factor and K a set of dynamic and load-distribution factors. The steps are: get the tangential load from the torque, Wt = 2T/d; find the form factor Y from the number of teeth and the pressure angle - for 20 deg full-depth teeth Y is about 0.154 - 0.912/Z; apply the dynamic factor Kv and, if the tooth is not across the full face width, the load-distribution factor; then divide by the face width times the module. The form factor accounts for the fact that the weakest section of the tooth is at the root, and it grows with more teeth and with a higher pressure angle.

**Push:** "How do you protect the gear against wear as well as bending?" - Bending is handled by the Lewis check and the module. Wear is a Hertzian contact problem: you compare the contact pressure at the flank from the normal load with the allowable contact stress of the material, which for steel scales roughly with the square root of the Brinell hardness. So the design levers are a harder, tougher pinion (case-hardened or nitrided, in the 30 to 40 HRC range) with a slightly larger module and a wider face, and picking the module large enough that neither the bending stress nor the contact stress exceeds its allowable.

**Trap:** Applying the Lewis equation to a gear with very few teeth without checking the form factor, or treating the same module as adequate for both bending and wear.

### Q20. Why are worm gears self-locking? What are their advantages and their problems? [M]

**A:** A worm is essentially a screw, and its lead angle is low, typically 1 to 5 deg, well below the angle of friction of the sliding steel pair, which is of the order of 8 to 10 deg. If the worm is the driver, the tangential force tries to push the teeth along the helix instead of lifting the worm out of the mesh, so the train cannot back-drive - it is self-locking. The price is efficiency: the sliding action gives roughly 30 to 40 percent for a single-start worm, falling to 10 to 15 percent for a multi-start high-ratio unit, and most of that lost power becomes heat. So a worm box needs a generous cooling surface or a fan, and an oil with good cooling rather than grease. You use worm gears for high ratios, typically 20:1 to 100:1, in a compact self-locking package - lifts, conveyors, valve actuators.

**Push:** "How do you make a self-locking worm drive that still has acceptable efficiency?" - Increase the lead angle and use multiple starts, and use a good anti-seizure lubricant with a bronze wheel; you then accept that it is no longer self-locking, and you add a brake or a backstop to hold the load.

**Trap:** Thinking a worm drive is efficient because the ratio is high. The ratio and the efficiency are unrelated - the high ratio is exactly why the efficiency is low.

**What they're really testing:** Whether you can explain a self-locking mechanism from the lead angle and friction angle, and connect the efficiency to the heat problem.

---

## 9. Gear trains and the planetary gear - 1 question

### Q21. Explain simple, compound, reverted and epicyclic gear trains. How does a planetary train work, and why is it used? [M]

**A:** A simple train has one gear per shaft and the ratio is the product of the individual ratios. A compound train has two gears on one shaft, so the ratio is a product of two ratios and the train is longer but gives a large ratio accurately in a small space. A reverted train has the input and output on the same axis with the intermediate shafts parallel - the classic layout of a vehicle gearbox. An epicyclic or planetary train has planet gears that orbit a sun gear while meshing with an internal ring gear; all three members are coaxial, and the speeds are tied by Willis' equation, (Ns - Nc)/(Nr - Nc) = -Zs/Zr. With the ring fixed and the sun as input, the carrier turns at Zs/(Zs + Zr) of the sun speed, so a sun of 24 teeth and a ring of 72 gives a 4:1 reduction with the carrier as output - that is why you use a planetary for a high ratio in a single stage, in automatic transmissions and in coaxial reduction boxes, with torque multiplied by the ratio.

**Push:** "What has to be true about the tooth numbers?" - For equal spacing of the planets the sum of the sun and ring teeth must be a multiple of the number of planets, and for even distribution of the load the planets should be equally spaced, otherwise the load is shared unequally and the life of the gear set drops.

**Trap:** Treating a planetary train as a fixed-axis train and adding up the ratios. You must first decide which member is held, then the ratio follows.

**What they're really testing:** Whether you can build up a ratio from the train geometry and say why a planetary gives a high ratio in one stage.

---

## 10. Bearings: types, life and mounting - 3 questions

### Q22. What types of bearings do you know, what load can each take, and where is each used? [H]

**A:** Deep groove ball - the general-purpose bearing; takes radial load and a moderate axial load because of the shoulder geometry, very low friction, speed limit roughly 12000 to 15000 rpm depending on lubrication and cage; used in motors, gearboxes and small machines. Cylindrical roller - higher radial capacity than a ball bearing of the same size, almost no axial capacity, used for heavy radial loads. Tapered roller - combined radial and axial load, mounted in pairs, used in wheel hubs and machine tool spindles. Angular contact ball - axial load in one direction, so it also goes in pairs, higher speeds, used where real axial thrust exists. Spherical roller - self-aligning, heavy radial plus moderate axial, tolerant of shaft deflection and misalignment, used in conveyors and crushers. Thrust ball and thrust roller - axial load only, used in clutches, screw jacks and vertical shafts. Plain or journal bearing - a sliding bearing with an oil film, used for large slow heavy shafts and where shock loads are high.

**Push:** "Why use a roller bearing instead of a ball bearing of the same bore?" - The roller carries more load because the line contact is much smaller than the ball contact, so the contact stress and therefore the capacity per size is higher; the price is more sliding friction and a lower limiting speed.

**Trap:** Fitting a deep groove ball bearing alone where a large axial thrust exists. It will carry some, but the axial capacity is limited and it should be paired with an angular contact or tapered roller bearing.

### Q23. How do you calculate the life of a bearing? Explain the L10 life. [H]

**A:** The catalogue life L10 is the number of revolutions, or hours at a given speed, that 90 percent of a statistically identical batch of bearings will exceed under a constant load before the first sign of metal-to-metal contact. The basic rating life is L10 = (C/P)^p, where C is the dynamic load rating - the constant load that gives one million revolutions - P is the equivalent dynamic load, and p is 3 for ball bearings and 10/3 for roller bearings. Life therefore scales with the cube of the load ratio: double P and the ball bearing life falls by a factor of 8. The modified rating life is L_nm = a1 (C/P)^p, where a1 is the reliability factor - about 1 for 90 percent reliability and higher for 95 or 99 percent.

**Push:** "What is the equivalent dynamic load P?" - When a bearing carries both radial and axial load, P = X Fr + Y Fa, with X and Y taken from the catalogue for the Fa/Fr ratio and the e value. If the load is constant, P is simply that load; if it varies, you use the equivalent load with the load factors from the catalogue.

**Trap:** Using p = 3 for a roller bearing or p = 10/3 for a ball bearing. Also forgetting that L10 is a life for 90 percent of bearings, not for every bearing.

### Q24. Why should a bearing never be hammered onto a shaft? What are the mounting rules? [M]

**A:** A ball or roller bearing is a hardened, thin-walled ring with raceways only a few millimetres thick, and the rolling elements are hard. Driving it on with a hammer, or pressing it on the wrong ring, sends the installation force through the rolling elements instead of through the ring, and it dents the raceway and the rollers. The damage may not show until the bearing fails in service, and it is not a warranty claim. The rules are: apply the force only to the ring being fitted - the inner ring onto the shaft, the outer ring into the housing - always through a close-fitting sleeve or a proper puller, never through the rolling elements; use induction heating for the inner ring and a cooling shrink fit for the outer ring; and check the shaft and housing fit, the shoulder height and the axial locking.

**Push:** "What is a locating and floating bearing arrangement?" - On a long shaft you fix the shaft axially at one end with a locating bearing (deep groove or angular contact) and let the other bearing float (cylindrical roller, or a deep groove on a loose fit), so thermal expansion cannot over-constrain the shaft and squeeze out the internal clearance.

**Trap:** Assuming a bearing that goes in easily is fine. The installation damage is invisible until it fails.

**What they're really testing:** Whether you respect the bearing as a precision component - correct life calculation, correct load direction, and correct installation.

---

## 11. Lubrication - 1 question

### Q25. Explain the lubrication regimes you meet in practice, the Sommerfeld number, and why journal bearings use Babbitt. [M]

**A:** Three regimes. Boundary lubrication - the surfaces are so close that the load is carried by the adsorbed molecular film and partly by the surface asperities; this is the start-up condition and the regime in a plain bearing with a marginal oil. Mixed lubrication - a partial film with some asperity contact, and this is where most machine bearings actually live. Hydrodynamic or full-film lubrication - a continuous film of oil separates the surfaces completely and the load is carried by the pressure in the film. The Sommerfeld number S = (mu/p)(r/c)^2 measures how well the film is established, and full film needs S above about 1. Journal bearings use Babbitt - tin-lead-copper-antimony - because it is soft enough to embed dust and to conform to a slightly oval or deflected journal, and it is a good anti-seizure running surface against a hardened steel shaft.

**Push:** "What does the hydrodynamic film depend on?" - On a converging wedge, which needs relative motion and a converging geometry; on the viscosity of the lubricant; and on the ratio of load to clearance. Speed and viscosity build the film, load and clearance destroy it, and the whole picture is the Stribeck curve of friction against the Sommerfeld number.

**Trap:** Believing full-film lubrication means no friction. Even in the full-film regime there is shear in the oil, so the friction is lowest but not zero.

**What they're really testing:** Whether you can name the three regimes and explain the hydrodynamic film from wedge, viscosity and clearance rather than from memory.

---

## 12. Springs - 2 questions

### Q26. What types of springs are there, which load does each one carry, and how do you size a helical compression spring? [M]

**A:** Helical compression spring - takes a compressive load between two surfaces; the commonest spring, used in clutches, valves and suspensions. Helical extension spring - takes a tensile load, with hooks or eyes at the ends. Leaf spring - takes a bending load; the simple leaf for light duty and the laminated leaf, a stack of graduated leaves with a master leaf, for vehicles and heavy equipment, where the leaves can be combined for different loads. Belleville or disc spring - a conical dished washer taking a compressive load, used where a high load must be carried in a small space and for near-constant-force applications. Torsion spring - takes a torque, used on hinges, clutches and garage doors. The spring rate of a helical compression spring is k = G d^4 / (8 n D^3), with G the shear modulus, about 80 GPa for steel, d the wire diameter, D the mean coil diameter and n the number of active coils.

**Push:** "What are the Wahl factor and surge?" - The Wahl factor K = (4C - 1)/(4C - 4) + 0.615/C, with C = D/d, corrects the simple direct-shear formula for the curvature of the wire and for the incomplete end coils. Surge is the axial resonance of a close-coiled spring when the number of active coils is small; you avoid it by increasing the active coils, by using plain or ground ends, or by keeping the helix angle low.

**Trap:** Forgetting the d^4 in the spring rate - a small change in wire diameter changes the rate drastically, which is why the wire size, not the coil diameter, is the sensitive variable.

### Q27. Why does a leaf spring have an eye? How is a leaf spring arranged on a vehicle, and what is the advantage of the arrangement? [L]

**A:** The eye locates the spring in a shackle or hanger and lets the spring pack be removed without disturbing the rest; it also lets the pack change its length slightly under load so the leaves can slide against each other. In a semi-elliptic spring the leaves are curved and both ends are fixed to the chassis - a full-elliptic spring has an eye at each end and shares the load better. The leaves are stacked with the longest leaf, the master leaf, in the middle or on top and the shorter ones above and below, all clamped by a centre bolt, and the graduated lengths give progressive springing: as the spring deflects, the shorter leaves come into contact one by one, so the rate increases. That gives a soft ride under light load and a firm rate under heavy load in one component.

**Push:** "Why is the master leaf given a greater thickness?" - It is the leaf that carries the load when the spring is nearly flat, and it is the one that takes the full deflection, so it is thicker and it is the one that can break and can be replaced.

**Trap:** Believing a leaf spring carries a constant force. The load rises as it deflects because the leaves engage progressively.

**What they're really testing:** Whether you know the spring families and their loads, and can connect the geometry of a leaf pack to the force-deflection behaviour.

---

## 13. Fasteners and preloading - 2 questions

### Q28. Why do we tighten a bolt to a specified torque? What is preload, and why must you not overtighten? [H]

**A:** A bolted joint works by preload, the clamp force generated when the bolt is tightened. The joint separates only when the external separating load exceeds the preload, and the preload also stops the joint slipping and prevents fatigue at the interface. Preload is set by torque through the thread friction: T = K F d, where K is the nut factor, about 0.2 for a clean lubricated steel bolt, F is the preload and d the nominal diameter. So a large fraction of what you apply with a wrench is lost to thread friction rather than going into stretching the bolt - which is why you always tighten to the same specified torque with the same lubrication. If you overtighten, the bolt can yield and then fail in fatigue, the thread can strip, or the clamped part can be crushed; because the torque-to-preload relation is so uncertain, the rule is to tighten to the specified value and never exceed it.

**Push:** "How is the preload calculated or verified?" - The torque method is the everyday one, but the better methods are the turn-of-nut method, a defined fraction of an extra turn after snug tight, and the direct tension method, measuring the bolt stretch with a strain gauge or by ultrasound. For a preloaded bolt the target is typically around 70 to 90 percent of the proof strength times the tensile stress area, and you would use the code value for the bolt class.

**Trap:** Believing tightening harder always clamps better. Beyond a point you only reduce the margin against fatigue failure of the bolt.

### Q29. How do you design a threaded fastener for tensile and shear loading, and what safety factor do you use? [M]

**A:** You keep the threads in tension and the shank in shear clearly separated. In tension you use the tensile stress area, about 0.79 d^2 for an ISO metric coarse thread, not the shank area, and the limit is either the proof strength of the bolt or thread stripping in the tapped material if that is the weaker one. In shear you use the shank area pi d^2/4 and the shear strength of the bolt, commonly taken as about 0.6 times the tensile strength, with the proviso that if the threads lie in the shear plane you must use the tensile stress area instead. A typical static safety factor is 3 to 4 on the ultimate strength in ordinary practice, and for fatigue you use an endurance approach with a much lower allowable and a stress concentration factor of about 3 for the thread root.

**Push:** "What is the load the bolt actually sees in a preloaded joint?" - Only a fraction of the external load. The external load first relieves the clamp force, and only the balance goes into stretching the bolt, so with a typical joint stiffness ratio the bolt sees roughly 20 to 30 percent of the applied separating load. That is why a preloaded bolt is so much better than an unpreloaded one.

**Trap:** Using the shank area for the tensile check. The thread root is smaller, and that is where the bolt would actually break.

**What they're really testing:** Whether you know that the torque you apply and the tension in the bolt are not the same thing, and that the preload does most of the work.

---

## 14. Design practice: manufacturability, wear and standards - 1 question

### Q30. How do you design for manufacturability and against wear, and why do you prefer standard components over custom ones? [M]

**A:** For manufacturability you design to the process and to the shop: use standard stock sizes and standard tolerances, keep the geometry simple and machinable, avoid deep pockets, small holes and thin webs, make sure the part can be fixtured and inspected, and specify tolerances the process can actually hold - a tolerance nobody can make or measure is worse than no tolerance at all. Against wear the levers are the material pair, the hardness difference between the two surfaces, the clearance, lubrication and cleanliness, the surface finish, and where the duty is severe a wear-resistant facing or a proper bearing material instead of metal on metal. And you prefer a standard part wherever the duty allows - an ISO bolt, a catalogue bearing, a standard coupling - because it is cheaper, arrives faster, is already proved, and comes with published ratings.

**Push:** "When would you still design something custom?" - When no standard exists, when a custom part saves a lot of assembly time or space, or when a standard part has itself caused a failure. Then you design it in-house with the same care and make it the standard for the next job.

**Trap:** Drawing something custom when a standard would do. The custom part is the one that gets drawn, machined, inspected and then fails at 3 am because nobody stocked a spare.

**What they're really testing:** Whether design for the real world - the shop floor, the wear environment and the spares inventory - is part of engineering, not afterthought.

---
