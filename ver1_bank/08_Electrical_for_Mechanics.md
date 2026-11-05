# Basic Electrical and Power for a Mechanical GET - L&T GET technical interview bank

**Part 8 of 8 | 23 questions | AC vs DC, three-phase, power factor, transformers, induction motors, earthing, protection, cables, switchgear, instruments and VFDs**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly,
[L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you
cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing
recall, they are testing whether you can reason out loud.*

## 1. AC, DC and three-phase fundamentals - 2 questions

### Q1. What is AC and DC, and why does the whole industry use AC? [H]

**A:** DC keeps one polarity, so its current flows in one direction only; AC reverses periodically, and in India the supply is 50 Hz, so the voltage reverses 100 times a second. Industry uses AC mainly because it can be transformed: a static transformer with no moving parts steps voltage up for transmission and down for distribution, which DC needs a rotating motor-generator set to do, with losses. AC is also easy to generate with an alternator and it lets us run rugged, brushless, self-starting induction motors - the machine under every pump, fan and compressor on site.

**Push:** So why does any industry still use DC? Electrolysis, electroplating, battery charging, traction and large drives, plus HVDC links where conversion is cheaper than AC over very long distances.

**Trap:** Saying AC is used because DC cannot be stepped up at all. DC can be stepped, just not with a transformer, so it needs rotating machinery and extra losses.

### Q2. Why does a three-phase system exist, and how are line and phase quantities related? [H]

**A:** Three-phase means three AC voltages 120 electrical degrees apart - 360/3 - so they always sum to zero, and the three together create a rotating magnetic field. It exists because it beats single-phase: for the same power, voltage and losses it needs about 25 percent less copper, and with the same conductor size it carries about 1.4 times the power of single-phase. In star, V_ph = V_L/sqrt(3) and I_L = I_ph; in delta, V_L = V_ph and I_L = sqrt(3) x I_ph. Total three-phase power is P = sqrt(3) x V_L x I_L x cos(phi).

**Push:** Give me a number: a 50 kW, 415 V, 0.8 power factor three-phase motor. I = P/(sqrt(3) x V_L x cos phi) = 50000/(1.732 x 415 x 0.8) = about 87 A, and that current is what sizes the feeder, the starter and the transformer.

**Trap:** Confusing the two connections. In star it is the voltage that is divided by sqrt(3) and the current that is unchanged; in delta it is the current that is multiplied by sqrt(3) and the voltage that is unchanged.

**What they're really testing:** Whether you can explain why the electrical plant on an EPC site is built the way it is, and compute the one number - current - that every electrical decision downstream depends on.

## 2. Power factor - 2 questions

### Q3. What is power factor, what makes it low, and why does a low power factor cost money? [H]

**A:** Power factor is cos(phi), the ratio of real power to apparent power, so kW = kVA x PF. It falls when current and voltage are out of phase, which happens with inductive loads - induction motors, transformers, welding sets, ballasts - where current lags voltage. A low PF is expensive because for the same kW the current is higher, I = P/(sqrt(3) x V_L x cos phi), so you pay more I-squared-R loss in cables and transformers, you need bigger cables, transformers and generators, you get more voltage drop, and the utility penalises you below the power factor agreed in the supply contract.

**Push:** Which equipment is the worst offender? Large induction motors running lightly loaded - at full load a motor is close to unity PF, but at part load its PF drops badly; a transformer on no load is also very poor, around 0.2 to 0.3.

**Trap:** The classic wrong answer is that a low PF is only a nuisance. It directly inflates current, losses and equipment size. Note also that in the source question bank "power factor" is tagged ELECTRICAL, so treat it as insurance for a mech panel, not a guaranteed question.

### Q4. How do you correct a low power factor, and where does it actually bite on a project? [M]

**A:** You correct it with shunt capacitor banks, usually in automatic steps, connected at the LV bus so they supply the reactive power locally and the current drawn from the utility drops towards unity. You can correct at the individual load, at a group of loads or at the main switchboard. A VFD helps too: it keeps the motor near its efficient loading point, and drives with an active front end draw close to unity PF. On a project it bites in three places - the utility bill and PF penalty, the size and cost of the incoming transformer, feeders and cables, and the usable capacity of the installed generation.

**Push:** What happens if you over-correct? The total PF goes leading, the bus voltage rises, and the capacitor banks and their switching contactors must be rated and stepped for the actual load profile; harmonic resonance with the supply is a real risk too.

**Trap:** Saying you improve PF with a capacitor in series. Correction is always by a shunt (parallel) capacitor. This is still tagged ELECTRICAL in the source bank, so answer it from the project angle.

**What they're really testing:** Whether you can connect an abstract electrical quantity to money and to equipment size on a real job - the exact thinking an EPC mechanical engineer needs when he has to justify a motor or a capacitor bank.

## 3. Transformers - 3 questions

### Q5. How does a transformer work, and why can it never be connected to DC? [H]

**A:** A transformer works on Faraday's law: AC in the primary winding creates an alternating flux in the laminated steel core, and that changing flux induces an EMF in the secondary proportional to the turns ratio. Connect DC and the flux does not change, so no EMF is induced in the secondary at all - the transformer simply does not transform DC. Worse, the primary then sees only its winding resistance, the core saturates, and it draws a very large current that will burn the winding or trip the supply. So no DC across a transformer, under any circumstances.

**Push:** Why is the core laminated and made of silicon steel? Lamination breaks the loops that would create eddy currents, and silicon steel raises resistivity so those losses stay low; with DC the core is magnetised solid and the flux has nowhere to go.

**Trap:** Stopping at "the secondary gets zero volts". The dangerous part is the primary current, which becomes huge because the core saturates - people wrongly think applying DC is a harmless no-op.

### Q6. What is the turns ratio, how is a transformer rated, and what do ONAN, ONAF and OFAF mean? [M]

**A:** The turns ratio is N1/N2; in an ideal transformer V1/V2 = N1/N2 while the current ratio is reversed. A transformer is rated in kVA, not kW, because its heating depends on current, not power factor - a 100 kVA transformer gives 100 kW at unity PF but only 80 kW at 0.8 PF. The cooling codes are IEC: ONAN is oil natural, air natural; ONAF adds fans; OFAF adds an oil pump as well, for large units. Oil immersed is normal for HV ratings, dry type for indoor or fire-risk areas.

**Push:** Oil filled or dry type next to a motor control centre in a flammable area? Dry type, or an oil-filled unit specifically certified for that zone - a plain oil transformer is not acceptable in a classified hazardous area.

**Trap:** Rating a transformer in kW, and misreading the cooling letters - in ONAN/ONAF/OFAF the first letter is the oil and the second is the air, and the N or F of each pair tells you natural or forced.

### Q7. Under what condition is a transformer most efficient? [M]

**A:** Efficiency is maximum when the copper loss equals the iron loss. The iron (core) loss is roughly constant as long as flux is constant, while copper loss goes as I squared and rises with the square of the load. So total loss is minimum where the variable copper loss matches the fixed iron loss, which for a typical distribution transformer is at or near full load - the exact point comes from the data sheet, because it depends on the design. The same idea appears in an induction motor, where maximum efficiency is a little above full load.

**Push:** Why is a transformer so inefficient at no load? At no load there is no copper loss, so the only loss is iron loss while the output is nearly zero - efficiency is nearly zero.

**Trap:** Saying maximum efficiency is at half load, or that it is where the losses vanish. The condition is equality of copper and iron loss, not a fixed load percentage.

**What they're really testing:** Whether you can reason from physics - changing flux, I-squared-R - instead of reciting textbook lines, and connect it to why an EPC project specifies transformers by kVA and not by kW.

## 4. Motors, machines and motor selection - 7 questions

### Q8. How does a three-phase induction motor work, and what is slip? [H]

**A:** A three-phase supply creates a rotating magnetic field in the stator; that field cuts the rotor conductors and induces current in them, and the interaction of that rotor current with the field produces torque, so the rotor follows the field at a speed slightly below it. Slip is that difference as a fraction, s = (Ns - N)/Ns, where Ns = 120 x f / P with P the number of poles. At full load a motor typically runs with a slip of roughly 2 to 6 percent depending on size, and it is this slip that is what converts into torque.

**Push:** Why can't it run at exactly synchronous speed? At synchronous speed there is no relative motion between the field and the rotor, so no current is induced and no torque is produced - a small slip is essential.

**Trap:** Saying the motor runs at synchronous speed, or quoting a running slip of 100 percent. Slip of 1 is the starting condition; running slip is a few percent.

### Q9. Why is a starter needed, and what happens on DOL starting? [H]

**A:** On direct-on-line starting the motor is connected straight across the supply, and the current at standstill is typically 5 to 7 times the full-load current, because at zero speed the rotor sees the full supply frequency and the motor impedance is at its lowest. That inrush pulls the supply voltage down, stresses the transformer and cables, and can trip the protection, so above a certain size you do not close the contactor straight to the line - you start through a reduced-voltage means. A starter does that, and also gives you a safe way to stop and reverse the machine plus overload and short-circuit protection for it.

**Push:** Does that starting current damage the motor? Usually not, because the inrush lasts only a second or two and the winding has a good short-time withstand; the real victims are the supply, the starter contacts and the mechanical train.

**Trap:** Saying a starter is there to limit speed or to save power. Note also that in the source question bank "three-phase induction motor starting" is tagged ELECTRICAL, so treat it as insurance for a mech panel, not the main event.

### Q10. Star-delta versus DOL - what happens to the current and the torque, and when do you use it? [M]

**A:** In star-delta starting the motor is first connected in star across the supply, so each phase gets V_L/sqrt(3) instead of V_L. The line current in star is one third of the DOL current, and since starting torque goes as the square of the phase voltage, the starting torque is also one third of the DOL value. That is the trade: you cut current and torque to a third, so it suits light starting loads only - centrifugal pumps and fans, light conveyors - where the required torque is below one third of DOL. The motor must be delta connected in service, and changeover happens only after it has accelerated close to synchronous speed.

**Push:** What if the motor is still slow when you switch to delta? The line current jumps back to roughly the DOL value at that lower speed, which defeats the whole purpose and stresses the supply, so the changeover is timed or speed-sensed.

**Trap:** Saying star-delta cuts the current to a third but keeps the torque, or that the torque falls to a ninth. Both current and torque come down by a factor of three.

### Q11. How do you control the speed of an induction motor? [M]

**A:** The synchronous speed is set by frequency, Ns = 120 x f / P, so the practical options are: changing the number of stator poles for a step change such as 4/8 pole; varying frequency with a VFD for continuous control plus soft starting; inserting rotor resistance in a slip-ring machine, cheap but inefficient for a fan; and letting the load itself regulate, since a centrifugal pump or fan slows as system resistance changes. VFD is the modern answer because it removes the starting inrush and matches speed to the duty instead of running a fixed-speed machine against a throttling valve.

**Push:** What does a VFD do to the motor? It rectifies the supply into a DC link and then switches it at a variable frequency to give the motor variable frequency and voltage; below base speed it keeps V/f constant so flux and torque stay roughly constant, above base speed it holds the voltage and weakens the field.

**Trap:** Saying you can control the speed of a squirrel-cage motor just by reducing the applied voltage. Torque falls as the square of the voltage, so under load the motor cannot hold a lower speed - that trick only works for fans.

### Q12. What are the IE efficiency classes, and why do they matter on a project? [M]

**A:** IE1, IE2 and IE3 are the standard motor efficiency classes - IE1 standard, IE2 high efficiency, IE3 premium - each step cutting losses by roughly one to three percentage points depending on rating, with IE3 in the mid-90s percent for the larger sizes. They matter because on a plant with thousands of kW of continuously running motors, every loss is electricity you buy every hour: one extra percent of efficiency on a 500 kW motor running 8000 hours a year is about 5 kW, roughly 40000 kWh a year of waste.

**Push:** How do you sell that to a client who looks only at the purchase price? Compare life-cycle cost - the kWh saved over the real duty hours times the site tariff, against the few percent premium on the purchase price.

**Trap:** Treating an efficiency class as one fixed number. The absolute efficiency differs with kW and with load, and the number that matters is the catalogue efficiency at the actual operating point, including the part-load correction.

### Q13. How do you select a motor for a pump, a fan, a compressor, a crane and a conveyor? [M]

**A:** You start from the load, not from a nameplate. For a centrifugal pump or fan, shaft power follows the pump curve, so you rate the motor at the maximum duty it can reach in service and add a service factor, often 1.1 to 1.25. Compressors and cranes are high starting-torque duties, so you check breakaway torque against the motor's starting torque and may need a soft starter, VFD, unloaded start or wound-rotor motor. Conveyors, especially vertical ones, are governed by inertia and starting time. As the mechanical engineer you specify power, speed, torque, duty, rotation and the drive arrangement - direct coupled or belt - and the electrical side sizes starter and cable from that.

**Push:** Why is a pump motor often deliberately given a margin? Because the pump curve has a peak and the machine may run at a duty slightly off design, so the motor is checked against the maximum power the pump can absorb, not only the design point.

**Trap:** Sizing the motor at the design point only, or at the gearbox rating instead of the actual load torque, and forgetting the load inertia, which is what really decides the starter and the starting time.

### Q14. What is the difference between a DC machine and an AC machine? [L]

**A:** A DC machine has a stationary field and a rotating armature with a commutator and brushes that mechanically rectify the induced AC; it gives easy speed control, but the brushes wear and the commutator limits power and speed. An induction motor, the common AC machine, has the supply on the stator, a rotating field, and a short-circuited cage or wound rotor with no commutator, so it is cheap, rugged and low-maintenance, but its speed is tied to supply frequency. A synchronous machine also has a commutator-free rotor with a DC field from an exciter, runs at exactly synchronous speed, and can be used as a synchronous condenser for power factor correction.

**Push:** Where would you still specify a DC machine? Cranes, hoists, elevators, rolling mills and older machine tools, where the wide and easily controlled speed range matters more than efficiency and brush maintenance.

**Trap:** Saying a DC machine has a rotating field and a stationary armature. It is the other way round - the field is stationary and the armature with the commutator rotates.

**What they're really testing:** Whether you can select and size the machine on a project - starting torque, load inertia, service factor, drive arrangement - because on an EPC job the mechanical engineer's motor data list is what the electrical side and the client both depend on.

## 5. Earthing, protection and site safety - 3 questions

### Q15. Why do we earth equipment, and what is the difference between earthing and grounding? [H]

**A:** Earthing creates a deliberate low-impedance path to earth so that if a live conductor touches a metal enclosure, a large fault current flows and the protective device trips quickly, instead of the enclosure sitting at mains voltage and electrocuting whoever touches it. The same path lets the earth-fault relay detect the fault, and it stabilises the system voltage and gives surges a route away. Grounding and earthing are used interchangeably in industry; IEC and Indian practice distinguish protective earthing of exposed metal parts, system earthing of the star point and working earthing of the neutral, while US usage calls the neutral connection grounding and the metal-part connection bonding.

**Push:** What are the TN, TT and IT systems? In TN the source neutral is earthed and exposed metal parts are connected back to that earth through a protective conductor; in TT the metal parts have their own separate earth electrode, so the fault loop depends on the electrode and you normally need an RCD for safety; in IT there is no direct earth on the source, the first fault is tolerated and an insulation monitor alarms - the system used in hospitals and mines.

**Trap:** Saying earthing is only for lightning protection, or that earthing and grounding are physically different things. The terminology differs by standard, not by physics; earthing's main job is fault current and human safety.

### Q16. What is permit-to-work and lockout-tagout for electrical work, and why must a mechanical engineer respect it? [H]

**A:** Before any work on or near live electrical equipment, an electrical permit to work is raised: it identifies the equipment, the isolation, the earthing, the hazards and the person doing the work, and it must be closed out and re-issued if the scope changes. LOTO is the isolation procedure - isolate, lock the isolator with your own padlock, tag it, then apply the test-before-touch rule: prove absence of voltage with a tester proved before and after. Portable earths then discharge stored charge and block back-feed, which matters on VFD DC links. A mechanical engineer must respect it because the machine he works on is electrically driven and can start without warning.

**Push:** What else has to be made safe before you open a machine? The non-electrical stored energies - hydraulic or pneumatic pressure, springs or counterweights, and rotational inertia - so you isolate, lock out, bleed, block and support before covers come off.

**Trap:** Thinking that because the job is mechanical the electrical permit is not needed, or that switching off the local isolator is enough. It is the lock, the tag and the proving-dead test that protect you.

### Q17. What is the difference between a fuse, an MCB and a circuit breaker, and what is a tripping curve? [M]

**A:** A fuse is a sacrificial element that melts when the current exceeds its rating - simple, cheap, in series, and it must be replaced after it operates. An MCB is a resettable device with a thermal bimetallic element for overload on an inverse time curve and a magnetic solenoid for instantaneous short-circuit tripping; the letters B, C and D give magnetic trip multiples, about 3-5x for B (resistive loads), 5-10x for C (inductive and lighting) and 10-25x for D (transformer and motor circuits with high inrush). A circuit breaker is the general term; in switchgear it means an MCCB or ACB.

**Push:** What number must you check on a breaker? Its breaking capacity in kA must exceed the prospective short-circuit current at the installation point - the fault level available from the transformer and the cable impedance - otherwise the breaker itself may not survive the fault it is meant to clear.

**Trap:** Saying a fuse and an MCB are the same because both trip on overload. They differ in resettability and time-current behaviour; also confusing the curves - a D-curve is chosen for motor circuits precisely because motors draw 5 to 7 times full-load current at start.

**What they're really testing:** Whether you will work safely on a live plant without being told - the behaviour a site safety culture is built on, and a panel will probe how seriously you take a permit.

## 6. Circuits, cables, switchgear and the power system - 3 questions

### Q18. What do resistance, reactance, impedance, phase difference and resonance mean in a simple RLC circuit? [M]

**A:** Resistance R opposes current and turns electrical energy into heat, V = I x R, in phase with the current. The inductor opposes change of current, with reactance X_L = 2 x pi x f x L; the capacitor opposes change of voltage, with reactance X_C = 1/(2 x pi x f x C). Together they give the impedance Z = R + jX, magnitude sqrt(R^2 + X^2), with a phase angle phi where tan(phi) = X/R - the angle behind power factor cos(phi). In a series RLC circuit the two reactances cancel at f0 = 1/(2 x pi x sqrt(L x C)); the circuit then looks purely resistive, current is maximum, and the voltages across L and C are magnified.

**Push:** Where does that show up in industry? Power factor correction by capacitors is exactly this - you add a capacitive reactance to cancel the inductive one. Resonance shows up as ferroresonance in transformers and as a real hazard where capacitors and transformers sit on the same system.

**Trap:** Saying an inductor opposes current (it opposes change of current), or that a capacitor blocks current forever - at steady-state DC it is open, but the transient charging current is exactly why you must discharge and earth it before touching it.

### Q19. What cables are used, and why is a cable derated? [M]

**A:** LV power cables are typically copper or aluminium, stranded, with PVC or XLPE insulation, single-core or multicore, armoured or plain; MV cables are usually XLPE at 6/10 kV and above, with separate control and instrumentation families for the signals. The quoted current-carrying capacity assumes a reference installation - roughly in air at 30 deg C ambient, single cable, free air - so you derate for a higher ambient, for cables bundled and touching in a tray, for the installation method (in conduit, on a tray, buried in ground, thermally insulated) and for altitude. Derating exists because it is the conductor temperature, not the current, that ages the insulation.

**Push:** What must a mechanical engineer hand the electrical team so the feeder can be sized? Connected load in kW, running current, starting method and starting current, length for the voltage-drop check, number of cables running together, ambient and installation method - and the power factor, because that sets the current.

**Trap:** Treating the catalogue current as the final answer, or forgetting the starting case, or believing a bigger cable solves a starting problem rather than a voltage-drop problem.

### Q20. Walk me through the power system, and what is switchgear made of? [M]

**A:** Power is generated in power stations - thermal, hydro, nuclear, solar, wind - as three-phase AC in an alternator at around 11 kV, stepped up to 400, 220 or 132 kV for transmission, carried on overhead lines to substations, then stepped down through 33 and 11 kV to 0.415 kV for distribution and the consumers. Transmission is at high voltage because for a given power the current is P/(sqrt(3) x V x cos phi) - raise the voltage and the current falls, so the I-squared-R line loss and the voltage drop both fall sharply and a lighter conductor will do.

**Push:** What is switchgear, and what does a switchyard contain? Switchgear is the assembly of switching, protection, measuring and control gear - circuit breakers, isolators, earthing switches, CTs and VTs, surge arresters, busbars, relays and the control panel - and a switchyard is the outdoor arrangement of that gear with busbars and line bays. This is where an EPC mechanical engineer meets it: at the MCC feeding his motors, and at the client substation that his load list sizes.

**Trap:** Confusing a switchyard with a switchboard. A switchyard is the outdoor HV installation with busbars and bays; a switchboard is the indoor metal-clad LV/MV panel with breakers, relays and mimic diagrams.

**What they're really testing:** Basic electrical literacy - enough that you can talk to the electrical engineer on your project without fear, and understand why the load list you prepare ends up sizing transformers, cables and switchgear.

## 7. Instrumentation, drives and energy economics - 3 questions

### Q21. Which instruments are on an electrical panel, and how do you read a machine's health from them? [M]

**A:** The panel gives an ammeter per phase, a voltmeter on the bus, a multimeter for troubleshooting, a tachometer for speed, and temperature sensors in the windings and bearings. An ammeter connects in series, a voltmeter in parallel, and a clamp meter is the ammeter you put around a live conductor. A thermocouple uses the Seebeck effect - two dissimilar metals give a small mV proportional to the hot-junction temperature - and is rugged and usable well past 1000 deg C but less accurate; an RTD, usually Pt100, changes resistance predictably, more accurate and stable but slower and limited to a narrower range.

**Push:** How do you use the panel to judge machine health? Current higher than the nameplate at the same duty points to added load, a dragging bearing or bad alignment; a steady rise in bearing RTD temperature points to lubrication or alignment; speed below the nameplate means the load has increased or the drive is slipping; and comparing the three phase currents shows an unbalance.

**Trap:** Forgetting cold-junction compensation on a thermocouple. It measures the difference between the hot junction and a reference junction, so the reference must be held at a known temperature.

### Q22. What does a VFD do for a motor, and why is it specified on pumps and fans? [M]

**A:** A VFD converts a fixed-frequency supply (415 V, 50 Hz) into variable frequency and voltage for the motor: rectifier, then a DC link capacitor, then an IGBT inverter. That gives variable speed, controlled torque via V/f control, and a soft start with no 5-to-7-times inrush, plus reversing and precise flow control without a valve. On pumps and fans it is doubly attractive, because by the affinity laws flow goes as speed, head as speed squared and power as speed cubed, so a 20 percent speed reduction cuts the power to 0.8 cubed, roughly half - while throttling to get the same flow would burn that excess energy in the valve.

**Push:** What are the cautions with a VFD? The motor must be VFD-rated (insulation, bearings, shaft currents, and cooling at low speed), there are supply-side harmonics, cable length is limited, and a compressor cannot be run too slow because of lubrication and cooling.

**Trap:** Believing a VFD only saves energy by making the motor run at its best efficiency point. The main win on a pump or fan is the affinity-law power saving plus the removal of throttling losses; on a constant-torque machine the saving is much smaller.

### Q23. What is the difference between kW, kVA and kWh, and what do you mean by unit consumption? [M]

**A:** kW is real power, the useful output; kVA is apparent power, which is what the transformer, cable and generator are sized for; kWh is energy, kW times hours, which is what you pay for. The link is kW = kVA x power factor, so a 100 kW load at 0.8 PF draws 125 kVA, and running it 10 hours uses 1000 kWh. Unit consumption is energy per unit of product - kWh per tonne of material, per m3 of compressed air, per ton of refrigeration - obtained by dividing the plant's total kWh by production over the same period. It is how you benchmark a plant, spot degradation and price the energy into the product.

**Push:** So why should a mechanical engineer care about power factor and motor efficiency? Because the choices you make - motor size and loading, VFD versus throttle, pump selection, star-delta versus soft start - set both the current drawn and the losses, and on a project with thousands of kW running all year those two numbers are what the client's energy bill and the operating cost estimate are built on.

**Trap:** Mixing kVA and kW when sizing equipment, and quoting energy in kW. Power is a rate (kW); consumption over a period is kWh - and one of them has a time in it, which is why energy is what you actually pay for.

**What they're really testing:** Whether you can connect electrical quantities to project cost and to mechanical decisions - the mindset of an engineer who is expected to look after the operating cost of the plant, not just the completion of the equipment.
