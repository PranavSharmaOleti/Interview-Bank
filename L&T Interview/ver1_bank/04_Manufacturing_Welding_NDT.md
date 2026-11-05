# Manufacturing, Welding and NDT - L&T GET technical interview bank

**Part 4 of 8 | 34 questions | Lathe and CNC machining, casting / forming / heat treatment, welding processes and NDT**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly,
[L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you
cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing
recall, they are testing whether you can reason out loud.*

---

## 1. Manufacturing and Machining - 15 questions

### Q1. Walk me through the main operations you can do on a lathe. [H]

**A:** Turning, facing, parting off, grooving, threading, chamfering, boring, tapping and knurling are the standard lathe operations. Turning reduces the diameter (external), facing produces a flat end, parting off severs the finished part, grooving cuts a groove, threading cuts the screw thread, boring enlarges and finishes an existing hole, tapping cuts an internal thread and knurling puts a grip pattern on the surface. On a CNC turning centre exactly the same things happen, driven by G-codes instead of handwheels.

**Push:** Why do you not bore a hole from solid on the lathe? - Because you would remove a huge amount of metal as swarf with a long slender bar that would chatter and break; you drill the hole first and then bore it to size.

**Trap:** "Facing and turning are the same operation" - facing makes a flat surface perpendicular to the axis, turning makes a cylindrical surface.

### Q2. What is the difference between a roughing cut and a finishing cut? [H]

**A:** Roughing is the heavy cut that removes most of the material: deep depth of cut, high feed, relatively lower cutting speed, a tougher tool with a large nose radius and good coolant supply. Finishing is the light final cut: small depth of cut, fine feed, higher speed, a sharp rigid tool with a small nose radius, and it is judged on accuracy and surface finish rather than metal removal rate. Roughing sets the shape, finishing sets the size and the finish.

**Push:** How do you choose the cutting speed for a given operation? - From the tool material and the workpiece: carbide runs several times faster than HSS on the same workpiece, and the diameter sets the rpm you need for that speed.

**Trap:** "Roughing uses high speed and light feed" - that is finishing; roughing runs at a lower speed with heavy feed and a deep cut.

### Q3. How do you know a cutting tool has worn out? What is a "tool signature"? [H]

**A:** On a single point turning tool, flank wear shows up as a bright secondary bevel or band just behind the cutting edge - that band is the tool signature, and its width tells you how much wear has built up. On the workpiece the same wear shows as a taper on the turned diameter (it grows away from the chuck), a drifting dimension, or a rough finish. So you inspect the tool visually, watch the dimension trend across the job, and compare the wear land against the limit for that tool grade.

**Push:** Which wears faster, flank wear or crater wear? - Crater wear on the rake face, caused by heat and chemical reaction with the hot chips, usually develops faster on ductile materials at high speeds; flank wear dominates on hard or abrasive workpieces.

**Trap:** "The tool signature is the bright band you see on the workpiece" - the signature is on the tool; the workpiece shows a taper, a loss of size, chatter marks or a poor finish.

### Q4. What is the difference between up milling and down milling? Which do you prefer and why? [H]

**A:** In up milling the cutter rotates so the tooth pushes the workpiece upward into the chip; the chip starts at zero thickness and grows, so the tooth is rubbing rather than cutting at the start of its engagement. In down milling the tooth drives the workpiece down, the chip is cut from full thickness down to zero, and the cutter is pulled into the cut. Down milling is preferred because the cutting force pushes the work down onto the table instead of lifting it, so it resists climb and chatters less, and the vertical wall it leaves has a better finish.

**Push:** Why does up milling produce a poor finish on the wall? - The cutter is climbing out of the cut, so the force grows with chip thickness and it grips and releases the workpiece, leaving a step at the top of the wall.

**Trap:** "Down milling cuts the chip from thin to thick" - that describes up milling; down milling enters at full depth and the chip thins out.

### Q5. What types of milling cutters are there, and how is a keyway made? [H]

**A:** The main ones are the plain (slab or cylindrical) milling cutter used on a horizontal machine for peripheral cutting, the face mill used for surfacing (usually indexable inserts on a shell mill), the end mill used on a vertical machining centre for pockets, slots and profiling, the form cutter for contours, and the gang cutter that cuts several slots at once. A keyway is a longitudinal slot with a rounded end that carries a shaft key to transmit torque; it is cut with an end mill or a keyway cutter, and its width and depth must match the standard key size for the shaft.

**Push:** Slab cutter versus end mill - which machine? - Slab or cylindrical cutters go on horizontal plain milling machines and cut on the periphery; end mills go on vertical machining centres and cut on the periphery and with the end face, which is what lets them drill, slot and profile.

**Trap:** "An end mill cuts only on the face" - end mills cut on the periphery and can cut with the end; the face mill is the one that cuts mainly with its face.

### Q6. What is machining allowance, and how is it different from tolerance? [H]

**A:** Tolerance is the permitted variation of a dimension, stated as limits around the nominal size (for example 25.00 +0.02 / -0.01). Allowance is the extra material deliberately left on the rough-machined part so that the finishing cut has something to remove - a turned shaft might be left with about 0.5 mm per surface. You leave allowance because the finishing cut is small and steady, so it corrects the errors of the roughing operation; if you machined straight to final size, every error in the rough cut would be locked into the finished part.

**Push:** Where is the allowance recorded? - In the drawing or, more usually, in the process plan and route card, as a stock allowance per stage; for castings and forgings it is the machining allowance the foundry or forger is asked to leave.

**Trap:** "Allowance and tolerance mean the same thing" - tolerance is what you permit, allowance is what you deliberately leave.

### Q7. What is the difference between a jig and a fixture? [H]

**A:** A jig holds and locates the workpiece, and it usually also guides the tool - a drill jig has a bush that guides the drill and carries the side load. A fixture holds, locates and supports the tool while the workpiece is clamped in it - a milling fixture is bolted to the table and carries the cutter. The short version: the jig holds the workpiece, the fixture holds the tool.

**Push:** Do you still use fixtures on a CNC machining centre? - Yes, the fixture is bolted to the table and the work is clamped in it; the jig as a separate guiding tool is largely replaced by the fixture plus the workholding devices.

**Trap:** "A jig holds the tool and a fixture holds the workpiece" - it is the other way round.

### Q8. How do you hold a workpiece on a lathe? What are soft jaws? [H]

**A:** The common methods are the three-jaw self-centring chuck for cylindrical work between centres, the four-jaw independent chuck for square or offset work or for holding a step to be machined, jaw sets and collets for small precision parts, a faceplate for large or flat work, and a tailstock centre to support long thin shafts. Soft jaws are jaw blanks that are machined on the machine for that specific job, so the gripping surface matches the part and gives better concentricity and a cleaner surface than standard hard jaws. Clamping force must be enough to stop the part slipping but not so much that it is distorted.

**Push:** What is indexing, and how do you clamp a multi-sided part? - Indexing means moving the part to a new position in a known direction so a repeated feature lands on the same axis each time; on a lathe you index the four-jaw chuck, and on a milling machine you use a rotary table or a dividing head, with the work clamped hard so the position cannot shift under the cut.

**Trap:** "Soft jaws grip better because they are soft" - soft means machined to suit the part; they give accurate location and no marking, but they must be hard enough to carry the load.

### Q9. What do G-codes and M-codes do in CNC? [H]

**A:** G-codes are preparatory codes that tell the control how to move: G00 rapid positioning, G01 linear feed, G02 and G03 circular interpolation clockwise and anticlockwise, G17, G18 and G19 plane selection, G90 and G91 absolute and incremental programming. M-codes are the miscellaneous machine functions: M03 and M04 spindle clockwise and anticlockwise, M05 spindle stop, M08 and M09 coolant on and off, M06 tool change, M30 program end and reset.

**Push:** What is a canned cycle? - A subroutine stored in the control for a repetitive operation such as drilling, tapping or pocketing (G81, G83, G84), so you only enter the position and the depth.

**Trap:** "G-codes run the spindle and M-codes control the axes" - it is the reverse: G-codes are motion and geometry, M-codes are auxiliary functions.

### Q10. How do you calculate cutting speed and feed? [H]

**A:** Cutting speed is the peripheral speed of the tool, V = pi * D * N / 1000 m/min, with D in mm and N in rpm; a 20 mm cutter at 800 rpm gives V = 3.1416 x 20 x 800 / 1000 = about 50 m/min. Feed is how fast the tool advances, f = N x z x fn mm/min, with z the number of teeth and fn the feed per tooth, and on a lathe feed is set in mm/rev. Cutting speed is limited by the tool material, the workpiece hardness and the tool life you want; feed and depth of cut set the metal removal rate and the load on the tool.

**Push:** How do you avoid long chips and tool breakage? - Use a proper chip breaker on the insert, keep the feed right so the chip breaks, flood coolant to control the temperature, and reduce the depth of cut if the machine is rigid enough; long chips wrap around the tool and spoil both the finish and the tool.

**Trap:** "That formula gives you the spindle speed" - it gives cutting speed in m/min; for rpm you rearrange it to N = 1000 V / (pi D).

### Q11. How does a micrometer work, and why does it have a ratchet? [H]

**A:** A micrometer measures the gap between the anvil and the spindle using a spindle screw of pitch 0.5 mm, so one turn of the thimble moves the spindle 0.5 mm while the sleeve is graduated in 0.01 mm - a least count of 0.01 mm and, on a good instrument, an accuracy of about 0.01 mm over the 0-25 mm range. The ratchet at the end of the spindle is a friction device: you turn the ratchet instead of the thimble, so the spindle always applies the same light, constant force. That makes the reading repeatable and stops you overtightening, which would give a false reading and shift the spindle.

**Push:** How do you check that a micrometer is correct? - Close it over a gauge block or slip gauge, rotate the ratchet, and see whether the reference mark on the sleeve lines up.

**Trap:** "You should tighten the thimble firmly to get an accurate reading" - the ratchet exists precisely so that you do not; overtightening gives a false reading and can damage the spindle.

### Q12. Which measuring instrument would you use for different features, and how do you inspect a critical dimension? [M]

**A:** Vernier caliper for general shop work (least count 0.02 or 0.05 mm), micrometer for higher accuracy at 0.01 mm, a bore gauge with a telescoping plug for bores, plug gauge (GO/NO-GO) for a limit hole, pin gauge for a small limit hole, thread gauge for threads, and slip gauge or Johannson gauge as the high accuracy master in the inspection room. For a critical dimension I confirm the instrument is calibrated and clean, take repeat readings, and for a limit dimension finish with a gauge as the accept/reject check. Surface finish is specified as Ra in micrometres, for example Ra 1.6.

**Push:** What is gauge tolerance? - The gauge itself is manufactured and certified to a stated accuracy, for example a 20 mm plug gauge held to plus or minus 0.006 mm; a part within that band is accepted. You have to know the gauge tolerance because it effectively sets the real tolerance of the part.

**Trap:** "Inspection is a formality done at the end of the job" - inspection is a gate whose whole purpose is to stop a bad batch going downstream, and readings are only meaningful if the gauge is calibrated and the results are recorded.

### Q13. What are the main types of CNC machine, what do axes mean, and how is a job set up? [M]

**A:** A vertical machining centre has a vertical spindle, with the table in X and Y and the spindle in Z - the general purpose machine for pockets, slots and face work. A horizontal machining centre has a horizontal spindle, which suits deep cavities and lets the chips fall away. A CNC turning centre makes turned parts from bar in X and Z. A five-axis machine adds two rotary axes so a complex 3D surface is machined in one setup. Setting up a job uses two kinds of offset: a tool offset stores each tool's length or radius and length, and a work offset stores the part datum, so the program is written in drawing coordinates.

**Push:** Why have tool and wear offsets separately? - The geometry offset is set once per tool and the wear offset is dialled in as the tool wears, so you correct a drifting dimension without resetting the whole tool.

**Trap:** "The tool offset tells the machine where the part is" - that is the work offset; the tool offset is the position of the tool tip relative to the spindle.

### Q14. What are the main types of grinding, and how does centreless grinding work? [M]

**A:** Surface grinding has a rotating wheel with the workpiece on a reciprocating table and produces a flat surface. Cylindrical grinding has a wheel running against a workpiece rotating between centres, for shafts and for internal bores. Centreless grinding has no centres at all: the workhead blade pushes the rotating workpiece against a regulating blade, and the part rests on the workpiece support and the wheel, so it is very fast for small round parts such as pins and needles, though the diameter range it can handle is limited. Grinding is a finishing process - it removes very little material but gives excellent accuracy and finish.

**Push:** Why is a grinding wheel so hard, and why is it dressed? - The wheel is a mass of hard but friable abrasive grains held in a bond; the grains do the cutting, so they must be sharp, and dressing breaks away the worn grains and exposes fresh ones while restoring the profile and the sharpness.

**Trap:** "Grinding is a rough stock-removal operation like rough turning" - grinding removes very little metal; it is used for accuracy and finish, and on hardened work it is the only economical way to cut.

### Q15. Tell me about drilling, boring, reaming, honing, lapping and broaching - where does each fit? [L]

**A:** Drilling makes a rough hole; the drill point is normally ground to 118 degrees, which balances the cutting lips and the rake face (about 135 degrees for soft ductile material, 80 to 90 for hard material). Reaming finishes an existing hole with a multi-flute tool cutting on a fixed margin, removing only 0.1 to 0.3 mm. Boring enlarges and finishes a hole that already exists, and is the accurate way to make a large hole. Honing uses an abrasive stone, rotating and reciprocating at low pressure, to put a cross-hatch pattern and final size on a bore. Lapping uses a lap and loose abrasive slurry to get a very flat surface. Broaching pulls a multi-tooth broach through the part, so every tooth cuts - fast, and mainly for non-ferrous and cast iron.

**Push:** Why can a reamer not be used to remove a large allowance, and how are the sharp edges finished? - The reamer has a small cutting margin, so with too much to remove it will rub, chatter and can break; drilling has to get within about 0.1 to 0.3 mm of size first. Deburring is then done with a file, emery or a chamfering tool so the part is safe to handle.

**Trap:** "A drill should be fed slowly so the chip is broken" - you feed the drill at a rate matched to its helix so the chip forms and is carried up the flutes; a slow feed lets the drill rub and burn.

**What they're really testing:** whether you can turn a workshop operation into a reason - what the cut is doing, what limits it, and how you know it is right - rather than reciting a list of names.

---

## 2. Casting, Forming and Heat Treatment - 10 questions

### Q16. Take me through the steps of producing a casting. [H]

**A:** The sequence is: make the pattern, make the mould, place the cores, melt the metal, pour, allow it to solidify, shake out the casting, cut off the risers and gates and fettle (clean) the surfaces, then inspect. The pattern is a scaled-up replica of the component, normally split into cope and drag halves with a parting line so the mould can be opened and the casting removed; cores are used for internal holes and cavities. The aim at every stage is a dense, defect-free casting that is close to the final shape.

**Push:** Why is the pattern made larger than the finished part? - To allow for the shrinkage of the metal as it cools; the shrinkage allowance is built into the pattern, roughly about 1 percent for cast iron and around 2 percent for steel, though the foundry standard is what you would actually use.

**Trap:** "The pattern is the mould" - the pattern is the tool used to form the mould; the mould is the sand body that actually holds the metal.

### Q17. Compare sand casting, die casting, investment casting and shell moulding. [H]

**A:** Sand casting forms the part in sand around a pattern: cheapest and most flexible, good for low volume and large parts, but accuracy is only a couple of millimetres and the surface is rough. Die casting injects molten metal at high pressure into a reusable steel die - fast with a good finish, holding small features to roughly +/- 0.05 mm, but the die cost is high so it pays only in high volume. Investment casting (lost wax) coats a wax pattern in ceramic and burns it out; it gives the best accuracy, about +/- 0.03 mm, and complex shapes, but is slow and expensive per part, so it suits turbine blades in small quantities. Shell moulding forms a resin-coated sand shell over a heated pattern - better accuracy than plain sand at moderate volume.

**Push:** Where does centrifugal casting fit in? - The mould rotates and the metal is thrown against the wall by centrifugal force, so it makes hollow cylindrical parts such as pipes and bushings with the dense metal outside and a good bore surface.

**Trap:** "Investment casting is the cheapest process for making a large number of small parts" - it is one of the most expensive per part; it is chosen for accuracy and complexity in small batches.

### Q18. What are the common casting defects, and what causes them? [H]

**A:** Porosity and blowholes are gas - hydrogen in the melt or moisture in the mould - so you dry the charge, the mould and the cores, degas the melt and use risers. Shrink cavities form in the thick, last-to-freeze sections, so you add risers and feed thick-to-thin. Cold shuts are two streams of metal meeting without fusing - too low a pour temperature or an interrupted pour. Misruns are incomplete filling - again too low a pour temperature or poor fluidity. Inclusions are sand or slag dragged in - bad moulding or gating. Hot tears are cracks opened by the mould restraining contraction - use collapsible binders and round the corners.

**Push:** How do you find these defects? - Radiography and ultrasonic testing for internal porosity and shrink cavities, dye penetrant for surface cracks, visual inspection for cold shuts and misruns, and sectioning or a machinability test on sample castings.

**Trap:** "Shrink cavities and porosity are the same defect" - porosity is many small round gas voids scattered through the metal, a shrink cavity is one large irregular void in a region that froze last.

### Q19. Forging, casting, rolling, extrusion, sheet forming and powder metallurgy - why do you choose each? [H]

**A:** Casting gives complex shapes in quantity with the least machining, but the grain follows the cooling contours and the shrinkage porosity acts as a crack starter. Forging squeezes the metal and refines and aligns the grain flow with the shape and the load path, which is why forgings are far more fatigue resistant than castings - crankshafts and gear blanks are forged for that reason. Rolling and extrusion are primary routes for long products and give a refined, directional grain. Sheet forming makes thin shells and panels cheaply. Powder metallurgy gives near-net shapes with no machining and controlled porosity for filters and bearings, but the size and shape are limited.

**Push:** What is additive manufacturing and when would you use it? - It builds a part layer by layer from a CAD model (SLS, SLM, FDM). It is used for prototypes, complex internal channels, topology-optimised brackets and low-volume spares, but it is slow and expensive per kilogram, the build size is limited and the properties are anisotropic with weaker interlayer bonding, so it does not replace casting or forging for heavily loaded structural parts.

**Trap:** "Forging and casting give the same grain flow" - forging aligns the grain along the load path, casting gives a dendritic structure with shrinkage porosity that initiates cracks under fatigue.

### Q20. What are the main heat treatments, and what does each one do? [H]

**A:** Annealing heats above the critical temperature (A3 for hypo-eutectoid steel), soaks and cools slowly: it softens, refines the grain, relieves stress and improves machinability. Normalising heats just above the critical temperature and cools in still air, giving a finer pearlite and more uniform properties with a moderate gain in strength. Hardening (quenching) forms martensite - very hard and strong but brittle. Tempering reheats below the critical temperature to relieve the martensite stresses and restore toughness, giving up a little hardness. The quench media set the cooling rate: water is fastest and risks distortion and cracking, oil is slower and milder, air or polymer suits high-alloy steels.

**Push:** Which treatment would you give a casting before machining, and why? - Annealing or normalising, to relieve the residual stress of casting, soften the material so the cutting forces and hence the distortion are lower, and refine the grain.

**Trap:** "Hardening gives a hard and tough component" - quenching gives hardness and strength with very low toughness; toughness only comes back with tempering.

### Q21. Compare Brinell, Rockwell and Vickers hardness testing. [H]

**A:** All three measure the resistance to plastic indentation by a hardened indenter. Brinell uses a 10 mm ball with about 3000 kgf for steel and reads the diameter of the impression after about 10 seconds; it is accurate for cast iron and heavy forgings but leaves a large mark. Rockwell uses a diamond cone with a minor and a major load and reads the depth directly - fast, and the standard for production checks on hardened steel. Vickers uses a diamond pyramid with 1 to 20 kgf and reads the diagonal; it is the most accurate, works on thin sections, and is the laboratory reference scale, broadly comparable with HRC.

**Push:** Which test would you use for a thin sheet, for a small case-hardened part, and for checking a gear tooth? - Vickers for thin or small parts and for laboratory work, Rockwell for routine production checks on hardened parts, and a small-indent or portable instrument for a tooth surface.

**Trap:** "The hardness number is the same whichever test you use" - the scales are not directly comparable; the same part can read about 200 HB, 20 HRC and 230 HV, so you must quote the scale and convert properly.

### Q22. What is a 2-high, 3-high and 4-high rolling mill, and what is extrusion? [M]

**A:** In a 2-high mill the two rolls are the only ones, the top roll is driven and the bottom follows by friction - simple, used for roughing. A 3-high mill adds a smaller roll between the two working rolls, which reverses the drive and allows a bigger reduction per pass. A 4-high mill has small working rolls backed by two backup rolls - the Sendzimir mill for thin, accurate strip. Rolling reduction is the reduction in thickness per pass. Extrusion pushes a billet through a die: direct has a stationary billet and a moving ram, indirect moves the die towards the billet and gives a better surface. Cold extrusion gives good finish and work hardening but needs high tonnage; hollow sections come from a tubular billet and a die with a mandrel.

**Push:** Why is rolling used for plates and sheets rather than forging? - Rolling is a continuous high-throughput process giving a uniform reduction along a long length with the work in compression so the surface stays sound; forging is for localised shapes and changing the cross-section.

**Trap:** "In a 2-high mill the bottom roll is driven" - normally the top roll is driven and the bottom one is dragged round by friction, which limits the torque available.

### Q23. Explain the main sheet metal operations, and what bend allowance and bend deduction mean. [M]

**A:** Shearing cuts the edge; blanking cuts a shape out of the sheet and leaves a hole, while piercing makes a hole without removing material. Bending forms the sheet around a radius between punch and die, drawing pulls a blank to form a cup, deep drawing increases the wall depth in successive draws with a blank holder controlling wrinkling and tearing, and stretch forming deforms the sheet over a form with little draw-in. Bend allowance is the length of material that ends up in the bend region - the arc plus the tangent legs; bend deduction is the allowance minus the sum of the outside flange dimensions, and you subtract it from the flange dimensions to get the flat blank length.

**Push:** Why do the bend radius and the grain direction matter? - A minimum bend radius, of the order of one to two times the material thickness depending on the material and tooling, is needed so the outside fibre does not crack and the punch does not mark the sheet; and the bend line should run across the grain, not along it, because bending parallel to the grain direction splits the surface and reduces the formability and the strength of the bend.

**Trap:** "Bend allowance and bend deduction are the same quantity" - bend allowance is the arc length used in the calculation, bend deduction is the allowance minus the outside flange dimensions; both are needed to develop a flat blank.

### Q24. What is case hardening and how is it done? [M]

**A:** Case hardening gives a hard, wear-resistant skin over a tough core. Carburising heats low-carbon steel in a carbon-rich atmosphere at around 900 deg C, giving a case typically 0.5 to 2 mm deep and very high surface hardness, but it distorts and needs quenching and tempering. Nitriding works at about 500 to 570 deg C in ammonia; the case is shallow, roughly 0.3 to 0.6 mm, but very hard, and the part barely distorts. Induction and flame hardening heat only the surface locally by eddy currents or a flame and quench it - fast and selective. A deeper case lasts longer under abrasion, but taking it too deep leaves less tough core to carry the load.

**Push:** What case depth do you specify for a gear? - It is chosen from the Hertzian contact stress and the required life, normally a fraction of the tooth depth, deeper where shock loading is high, with enough sound core left below the case to carry the load.

**Trap:** "Nitriding gives a deep hardened case" - nitriding gives one of the shallowest cases, well under a millimetre; carburising is the process for a deep case.

### Q25. What are routing and a process plan, and how is a standard time fixed? [L]

**A:** Routing is the ordered list of the operations and machines the job goes through. A process plan states, operation by operation, what is to be done, on which machine, with which tools and jigs, at what feeds and speeds, and the tolerances to be achieved. A standard time comes from work study - the observed element times plus allowances for fatigue and personal needs - and rate fixing converts that into the output the operator is expected to achieve. It is an agreed target, not a measurement, and it is the basis of both the incentive scheme and the costing.

**Push:** What is the difference between an observed time and a standard time? - The observed time is what you actually timed; the standard time is that plus the allowances, and it is what the operator is expected to achieve.

**Trap:** "A standard time is the fastest the operator can go" - it is the time agreed for a competent operator at the prescribed pace with allowances added, not a best-effort sprint.

**What they're really testing:** whether you understand that manufacturing is a chain of processes, each one chosen for a reason, and each with its own defects and its own properties to control.

---

## 3. Welding and NDT - 9 questions

### Q26. Compare the main welding processes. [H]

**A:** SMAW uses a flux-coated consumable electrode, needs no gas, works in any position and outdoors, but it is slow - the standard for site erection. GMAW/MIG feeds a continuous wire under a shielding gas: fast, clean, good for thin sheet, but it needs wind protection. GTAW/TIG uses a non-consumable tungsten with argon and a hand-added filler; the highest quality and control, but slow, so it suits root passes, thin tube and stainless. SAW feeds a bare wire under a flux blanket, giving a very high deposition rate on long seams in thick plate. FCAW uses a flux-cored wire and needs little or no shielding gas - easy like MIG, but with a slag. Plasma and laser are mainly cutting processes rather than joining, though plasma welding does exist.

**Push:** Which process for a 2 mm stainless sheet, and why? - TIG, because it gives a clean, oxide-free, low-heat-input weld with no flux contamination and the heat input can be controlled to avoid distortion; laser if the volume is high and the joint is simple.

**Trap:** "SMAW gives the best quality weld because it is the toughest process" - the shielded processes give cleaner and more consistent deposits; SMAW's advantage is that it is robust and works everywhere.

### Q27. What are the welding positions, and why is vertical-up the hardest? [H]

**A:** The positions are flat (F), horizontal (H), vertical (V) and overhead (OH), defined by the direction of travel of the weld relative to the plate and the position of the molten pool. Vertical-up is the hardest because the molten pool has to be held against gravity: the metal and the slag tend to run down, the puddle is hard to control, and as the bead grows the pool gets bigger and harder still, so the electrode must be held at an angle to direct the arc force upward. Vertical-down is easier because the arc force pushes the molten metal down into the joint, but the deposition rate is lower and the root profile is affected.

**Push:** How does a welder get qualified for vertical work? - The welder makes a test assembly in that position to the qualified procedure and passes the specified visual and NDT acceptance criteria, so the qualification record must cover the position and the process actually used on the job.

**Trap:** "Overhead welding is the hardest position" - vertical-up is generally regarded as the hardest to control because of the pool; overhead is difficult mainly for the welder's strength and for fatigue in the wrist and arm.

### Q28. What are the common weld defects, and what causes them? [H]

**A:** Porosity is trapped gas - wet electrodes, dirty plate, poor shielding or too much travel speed. Undercut is a groove at the weld toe - current too high, arc too long or travel speed too high. Slag inclusion is flux trapped in the bead - poor interpass cleaning or wrong electrode angle. Incomplete fusion and lack of penetration come from too little heat input, a bad bead placement or wrong joint preparation. Overlap is a bead too wide for the groove. Distortion is weld shrinkage pulling the plates out of shape, controlled by sequence, tacking and balanced welding. Hot cracks form in the weld metal while it is still hot and fragile; cold cracks form in the HAZ after cooling, driven by hydrogen and restraint.

**Push:** How do you tell a hot crack from a cold crack? - A hot crack is in the weld metal, forms while the metal is still hot, is intergranular and its faces are oxidised and rounded; a cold crack is in the HAZ or the parent metal, transgranular, and often appears only days later because of hydrogen.

**Trap:** "Undercut is caused by too low a current" - it is usually too high a current or too long an arc, though poor technique adds to it.

### Q29. What is the heat affected zone, and why do we preheat and do post-weld heat treatment? [H]

**A:** The heat affected zone is the region of parent metal next to the weld that was heated by the arc but did not melt, so its properties change - it can turn hard and brittle in a carbon or low-alloy steel, and many weld failures start there. Preheat slows the cooling rate so the HAZ transforms gently instead of forming martensite, and it helps hydrogen diffuse out; it is used for thick sections, high carbon steels and cold weather. Post-weld heat treatment reheats the assembly to relieve the residual stresses of welding and restore the HAZ properties, on pressure vessels and heavy restrained joints.

**Push:** What are the residual stresses in a welded joint, and how are they handled? - The weld metal shrinks as it cools while the surrounding plate restrains it, so the weld is left in tension and the plate around it in compression; on a pressure vessel this can be more severe than the working pressure, which is why PWHT is used and why critical welds get full radiographic or ultrasonic examination.

**Trap:** "The HAZ is the weakest part of the joint because it did not melt" - if the procedure is right the HAZ is not the weak link; the failures come from weld metal defects and from a hard, hydrogen-affected HAZ, which is exactly why preheat matters.

### Q30. What non-destructive testing methods are there, and what does each one detect? [H]

**A:** Visual inspection catches surface flaws - undercut, cracks, lack of fusion, bad profile - and is always done first. Dye penetrant finds fine surface-breaking cracks on non-porous material. Magnetic particle finds surface and near-surface cracks, and is the best method for welds, but only in ferromagnetic material. Radiography shows internal flaws - porosity, lack of fusion, inclusions - but is poor at surface cracks and needs access on both sides. Ultrasonic finds internal cracks, lack of penetration and laminations and can measure thickness, but needs a skilled operator and a reference block. Eddy current finds surface and near-surface cracks in any conductive material without contact, so it is used on heat exchanger tubes.

**Push:** So which method for a crack in a stainless steel pipe weld? - Neither dye penetrant nor magnetic particle, because stainless is non-ferromagnetic; you use dye penetrant for a surface-breaking crack and ultrasonic testing for one that is not open to the surface.

**Trap:** "Radiography will show a surface crack" - radiography is for internal flaws like porosity and lack of fusion; a fine surface crack is better seen by dye penetrant or magnetic particle.

### Q31. What is the difference between NDT and destructive testing, and what gets destructively tested on a lot basis? [M]

**A:** NDT leaves the component intact, so it can be applied to every item in a batch and the part still goes into service; destructive testing destroys the specimen, so it is used on test coupons or sample pieces taken from the lot, never on the component itself. On a lot basis you do tensile, hardness and Charpy impact tests on the material, bend tests on welds and on plate, chemical analysis, and sometimes sectioning and macrosetch of a sample casting or forging to check internal soundness. Weld quality acceptance is judged on the same logic - visual inspection plus the specified NDT, against the acceptance criteria in the WPS, with the results recorded against the joint.

**Push:** Why is impact testing specified separately from the tensile properties? - Because Charpy impact energy is not implied by strength; a steel can have adequate yield strength and still be brittle at low temperature, so toughness has to be demonstrated separately, particularly for service below the ductile-to-brittle transition temperature.

**Trap:** "If a part passes NDT it needs no destructive test" - NDT cannot prove the strength or the toughness of the material or the bend ductility of a weld; those still have to be shown on sample pieces.

### Q32. Why is welding dissimilar metals difficult, and where does it come up? [M]

**A:** The difficulties are that the two metals have different melting ranges, different coefficients of thermal expansion and different thermal conductivities, and the weld metal gets diluted by the base metal, so a mix of the two can form brittle intermetallic compounds and a crack at the fusion boundary. The differing expansion also leaves residual stress in the joint, and the different conductivities give an uneven, distorted weld pool. So dissimilar welding needs a procedure that controls the heat input, often a buttering or cladding layer on one side to isolate the metals, sometimes a post-weld heat treatment, and it is avoided where a transition piece or an intermediate joint can be used.

**Push:** Give a real example. - Dissimilar joints are common in high-temperature plant: stainless steel piping welded to carbon steel, a stainless liner welded to a carbon steel shell, and cladding or overlay of a corrosion- or wear-resistant layer on carbon steel base metal.

**Trap:** "Dissimilar metals weld easily if you keep the heat input low" - low heat input helps the cooling rate and the distortion, but dilution and intermetallic formation are metallurgical problems that a procedure alone cannot always fix.

### Q33. When would you weld a component rather than cast it or machine it, and what is the cost logic? [M]

**A:** Welding is chosen when the item is large, when it is a structure rather than a component - frames, vessels, tanks, stacks, pipe spools - when the shape is not economical to cast, and when field repair matters. A welded fabrication is generally cheaper than a casting of the same size, because a casting needs a pattern, a mould and a melting furnace while welding needs only fit-up and the welding process. But welding is not free: the cost is in consumables, welding man-hours, fit-up and NDT, and it grows with joint thickness and the number of passes. For a small component with tight tolerances, machining from bar is still cheapest.

**Push:** Where is welding used in heavy structures? - In structural steel and heavy plant the joints are usually specified as full penetration butt welds with continuous inspection, because the load path and the fatigue life of the structure depend on the weld quality rather than on the strength of the parent metal.

**Trap:** "Welded construction is always cheaper than a casting" - for a very large casting the opposite can be true, and any fair comparison must include the pattern cost, the reject rate and the machining that follows.

### Q34. What is a weld symbol, and what is a WPS and a welder qualification? [L]

**A:** A welding symbol is the notation under a reference line that tells the fitter and the welder how to make the joint: the arrow points at the joint, the symbol gives the weld type (fillet, butt, plug or slot) with its size and length, and the specification side gives the process, the electrode, the positions and the NDT requirement. A WPS is the qualified instruction document - process, joint type, filler, preheat and interpass temperature, heat input, technique and acceptance criteria - and it is qualified by testing. Welder qualification is separate: the welder makes a test piece to that WPS in the qualified position range and passes the visual and NDT checks.

**Push:** Why are the procedure and the welder qualified separately? - A good welder with a poor procedure still makes a bad weld, so both the procedure (for the joint and the variables) and the welder (for the skill) must be demonstrated before the weld is acceptable.

**Trap:** "If the WPS is qualified then any welder can make that weld" - each welder must be qualified separately for that procedure and position range, and the qualification has to be current.

**What they're really testing:** whether you can explain how a weld is made soundly and how it is proved - which process, which position, which defects to expect, and which test proves what.

---

*End of Part 4. Suggested revision order: the [H] questions in each section first (11 + 6 + 6 = 23 questions), then the [M] questions, and use the [L] ones to round off the picture.*
