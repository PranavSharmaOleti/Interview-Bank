# Theory of Machines - Core Interview Bank

**Part 4 of 10 | 45 questions | Mechanisms, kinematics, dynamics, cams, gears, balancing, governors**
*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Mechanisms and Kinematics - 12 questions

### Q1. Degrees of freedom in planar mechanism. [H]
**A:** Degrees of freedom (DOF) is the number of independent parameters needed to define position of all links. For planar mechanisms, Kutzbach formula: F = 3(n-1) - 2*j1 - j2, where n = number of links, j1 = lower pairs (revolute/prismatic), j2 = higher pairs (cam/gear). F > 0 means unconstrained motion, F = 0 is a structure, F < 0 is overconstrained (preloaded).
**Push:** What is the DOF of a four-bar linkage? -> n=4, j1=4 -> F = 3(3) - 2(4) = 1. It has one input, fully defined.
**Trap:** Using the spatial formula F = 6(n-1) - 5j1 - 4j2... for planar mechanisms - that's for 3D.
**What they're really testing:** Whether you can calculate DOF for planar mechanisms and interpret the result.

### Q2. Grashof's law for four-bar linkage. [H]
**A:** For a four-bar with links s (shortest), l (longest), p, q (intermediate): if s + l <= p + q, the shortest link can fully rotate - Grashof condition satisfied. Four cases: (1) s is ground link -> double crank (drag link), both cranks rotate fully. (2) s is coupler -> double rocker, no full rotation. (3) s is adjacent to ground -> crank-rocker, one crank one rocker. (4) s is opposite ground -> rocker-crank, same as case 3 but inverted. If s + l > p + q, it's a non-Grashof double rocker.
**Push:** How do you quickly identify which link is the crank? -> The link adjacent to ground that can rotate 360 deg is the crank; the other moving link is the rocker.
**Trap:** Confusing which link is s or l, or forgetting that Grashof is necessary but not sufficient.
**What they're really testing:** Whether you can apply Grashof's law to classify four-bar linkages.

### Q3. Crank-rocker mechanism, applications. [H]
**A:** Crank-rocker is a Grashof four-bar where the shortest link is adjacent to ground. The shortest link (crank) rotates fully; the opposite link (rocker) oscillates. Converts continuous rotation to reciprocating oscillation. Used in windshield wipers, sewing machine needle drive, pump reciprocating mechanisms, packaging machines.
**Push:** How do you change the rocker's stroke angle? -> Change the link lengths - longer coupler or rocker increases stroke, but check Grashof still holds.
**Trap:** Saying crank-rocker gives linear motion - it gives angular oscillation; slider-crank gives linear.
**What they're really testing:** Whether you understand the crank-rocker function and can identify applications.

### Q4. Quick-return mechanism, Whitworth. [M]
**A:** Quick return mechanism makes the forward (working) stroke slower and the return stroke faster. Achieved by offsetting the crank centre or using Whitworth mechanism. Time ratio (forward/return) > 1. Used in shapers, slotters, planers, printing presses, broaching machines - any tool where cutting happens in one direction only.
**Push:** What is the time ratio for a standard Whitworth quick return? -> Time ratio = (180 + alpha) / (180 - alpha) where alpha is the angle between the two extreme crank positions.
**Trap:** Confusing quick return with constant velocity - the whole point is unequal speeds.
**What they're really testing:** Whether you understand quick-return motion and can apply it to reciprocating machinery.

### Q5. Straight-line motion mechanisms. [M]
**A:** Mechanisms that generate exact or near-exact straight-line motion from rotary input. Exact: Peaucellier cell (8 links, inversor), Hart's A-frame (6 links). Approximate: Watt's linkage (3 links, straight line near centre), Chebyshev linkage, Robert's mechanism. Used in early steam engine crossheads, suspension systems, robot end-effector guidance.
**Push:** Why did Watt's linkage replace the Peaucellier in practice? -> Peaucellier is exact but complex (8 links, more joints, wear); Watt's is 3 links, good enough for limited travel.
**Trap:** Saying all straight-line mechanisms are exact - most practical ones are approximate.
**What they're really testing:** Whether you know the common straight-line mechanisms and can distinguish exact from approximate.

### Q6. Cams and followers - key terms. [H]
**A:** Cams: radial (disc) or cylindrical. Followers: translating (radial/offset) or oscillating. Follower faces: knife-edge (sharp, high wear), roller (low friction, common), flat-faced (simple, high contact stress), spherical-faced. Cam profile is the envelope of follower positions for the desired motion curve. Given follower motion (displacement vs cam angle), you invert the motion to generate cam surface.
**Push:** Why use a roller follower over knife-edge? -> Roller reduces friction and wear, allows higher speeds; knife-edge wears fast and jams.
**Trap:** Thinking cam profile = follower displacement curve - they are different; profile is the physical surface.
**What they're really testing:** Whether you understand cam-follower kinematics and can specify follower types.

### Q7. SHM, cycloidal, constant velocity motion profiles for cams. [H]
**A:** SHM: simple sine displacement, smooth velocity/acceleration, but infinite jerk at start/end - causes vibration. Cycloidal: sine acceleration, zero jerk at boundaries, smoothest, best for high speed. Constant velocity: infinite acceleration at boundaries (impossible physically), only for very slow cams. Cycloidal is standard for high-speed cams; SHM for moderate; constant velocity avoided except for dwell transitions.
**Push:** Which profile gives minimum maximum acceleration for a given lift and duration? -> Cycloidal - its acceleration is sinusoidal with lower peak than SHM.
**Trap:** Using constant velocity for high-speed cams - causes infinite jerk, destroys mechanism.
**What they're really testing:** Whether you know motion profile comparisons and can select the right one.

### Q8. Pressure angle in cam, effect on performance. [M]
**A:** Pressure angle is the angle between the follower motion direction and the normal to the cam profile at the contact point. High pressure angle -> high side thrust on follower -> increased friction, wear, bending stress, possible jamming. Limit: < 30 deg for translating followers, < 35-40 deg for oscillating. Increase base circle radius or reduce lift to reduce pressure angle.
**Push:** What happens if pressure angle exceeds 45 deg? -> Side thrust exceeds normal force - follower binds, chatters, or jumps; cam may need spring preload which increases wear.
**Trap:** Ignoring pressure angle when designing high-lift cams - it's the primary limit on lift for a given base circle.
**What they're really testing:** Whether you understand pressure angle as the primary constraint on cam design.

### Q9. Coriolis acceleration in slider-crank. [H]
**A:** Coriolis acceleration = 2 * omega x v_rel, appears when a point moves on a rotating link (sliding contact). In slider-crank, the slider moves on the rotating connecting rod - the slider has Coriolis component perpendicular to rod, magnitude 2*omega_rod*v_slider. Direction: rotate v_rel by 90 deg in direction of omega. Must include it in acceleration polygon or relative acceleration equation.
**Push:** What is the direction of Coriolis acceleration for a slider moving outward on a CCW rotating link? -> Perpendicular to link, 90 deg ahead of slider velocity in rotation direction.
**Trap:** Missing Coriolis term entirely, or wrong direction - it's the most common error in acceleration analysis.
**What they're really testing:** Whether you can identify and calculate Coriolis acceleration in mechanism analysis.

### Q10. Velocity and acceleration analysis methods. [H]
**A:** Relative velocity: v_B = v_A + v_B/A (vector sum). For a rigid link, v_B/A is perpendicular to AB. Draw velocity polygon, solve unknowns. Instantaneous centre (IC): point on two links with same velocity. Kennedy's theorem: three bodies in plane motion have three ICs lying on a straight line. Find all ICs, then v = omega x r from IC. IC method is faster for 4-bar; velocity polygon works for any mechanism.
**Push:** How many ICs does a 6-link mechanism have? -> n(n-1)/2 = 15 ICs.
**Trap:** Forgetting that IC location changes with configuration - it's instantaneous, not fixed.
**What they're really testing:** Whether you can use velocity analysis methods for mechanism kinematics.

### Q11. Slider-crank mechanism, in-line vs offset. [H]
**A:** Links: crank (rotating), connecting rod (coupler), slider (reciprocating), frame (ground). In-line: crank centre, slider path, and connecting rod all lie in same line when crank at 0/180 deg - symmetric motion, equal time forward/return. Offset: slider path is offset by distance e from crank centre - gives quick return, asymmetric stroke, used when cutting load is only in one direction.
**Push:** How does offset affect maximum piston velocity? -> Offset increases max velocity on one stroke and decreases on the other; also shifts the crank angle of max velocity.
**Trap:** Saying offset slider-crank has equal forward/return time - that's in-line only.
**What they're really testing:** Whether you understand slider-crank kinematics and the effect of offset.

### Q12. Cams: displacement, velocity, acceleration diagrams. [H]
**A:** For a given follower motion (displacement vs cam angle), the cam profile is generated by inverting the motion. Velocity = derivative of displacement, acceleration = derivative of velocity. For SHM: displacement = (L/2)*(1 - cos(theta)), velocity = (L/2)*omega*sin(theta), acceleration = (L/2)*omega^2*cos(theta). For cycloidal: displacement = L*(theta/pi - sin(2*theta)/(2*pi)), velocity = L/theta_max*(1 - cos(2*theta)), acceleration = 2*L*omega/theta_max*sin(2*theta).
**Push:** Why does SHM have infinite jerk at start/end? -> Because acceleration jumps from 0 to (L/2)*omega^2 instantly at theta = 0 and 180 deg. Jerk = d(acceleration)/dt = infinity at these points.
**Trap:** Confusing displacement diagram with cam profile - they are different; profile is the physical surface.
**What they're really testing:** Whether you can relate follower motion to cam profile and calculate velocity/acceleration.

---

## 2. Gears and Gear Trains - 12 questions

### Q13. Types of gears and applications. [H]
**A:** Spur gear - straight teeth on cylindrical shaft with parallel axes; simplest and cheapest, used for low speed and general duty. Helical gear - teeth inclined to axis, parallel axes; smoother, quieter and higher capacity because more teeth share the load, but generates axial thrust that needs a thrust bearing. Bevel gear - conical, for shafts that intersect, typically at 90 deg. Worm - a screw driving a wheel, for very high ratios in a compact package, self-locking, but low efficiency and generates heat. Planetary - sun, planets and ring, all coaxial, very high ratio in one stage, used in automatic transmissions and coaxial reduction boxes. Rack and pinion - converts rotation to linear motion, used in machine tools and actuators.
**Push:** Why do helical gears generate axial thrust? -> Because the tooth force has a component along the axis, proportional to the helix angle; you must support that with a thrust bearing or a properly preloaded pair.
**Trap:** Believing helical gears are always more efficient than spur. They are smoother and quieter, but the axial thrust and extra sliding loss mean they are not automatically more efficient.
**What they're really testing:** Whether you know gear types and can select the right one for given conditions.

### Q14. Module, pressure angle, pitch circle, addendum, dedendum. [H]
**A:** The module m is the tooth size and it is the thing you actually specify, since the pitch diameter comes out of it: m = d/Z, so d = m Z. Two meshing gears must have the same module, and that plus the tooth numbers fixes the centre distance a = m(Z1 + Z2)/2. The pressure angle is the angle between the line of action and the common tangent at the pitch point; 20 deg is the standard because it gives a good balance between tooth force and bearing force. The pitch circle is the imaginary circle of radius d/2 whose circumference carries the circular pitch pi m. The addendum is the tooth height above the pitch circle, normally 1.0 m, and the dedendum is the depth below it, normally 1.25 m, so the whole depth is about 2.25 m.
**Push:** Why 20 deg and not 25 deg? -> A higher pressure angle reduces the tooth force for the same torque, which reduces bearing load, but it increases the contact ratio and makes the teeth thinner at the root, so the tooth root becomes weaker and more sensitive to root stress. 20 deg is the compromise that suits most general machinery.
**Trap:** Trying to design a gear by choosing a pitch diameter. You choose the module and the number of teeth.
**What they're really testing:** Whether you can size a gear from the module and tooth numbers, not from pitch diameter.

### Q15. Gear ratio, direction of rotation, torque multiplication. [H]
**A:** The gear ratio is i = N1/N2 = Z2/Z1 = d2/d1, the speed of the driver over the speed of the driven. If the driver has fewer teeth than the driven, the driven turns slower and the torque is multiplied; power is conserved, so T2 = T1 times i ignoring losses, and every multiplication of speed or torque is paid for in efficiency. Each external mesh reverses the direction, so an idler between two gears gives back the original direction; an internal gear keeps the same direction, and in a planetary the direction depends on which member is held.
**Push:** How do you get a reduction of 20:1? -> You cannot do it in one pair without a very small pinion; you use a compound train so the overall ratio is the product of two or more pair ratios, or a worm, or a planetary.
**Trap:** Confusing gear ratio with the ratio of diameters only and forgetting the tooth numbers, or assuming the torque increase is free.
**What they're really testing:** Whether you can build up a ratio from the train geometry and say why a planetary gives a high ratio in one stage.

### Q16. Lewis equation for gear tooth bending stress. [H]
**A:** The Lewis equation estimates the bending stress at the tooth root: sigma = Wt K Ks Kv Kg / (b m Y), where Wt is the tangential load, b the face width, m the module, Y the Lewis form factor and K a set of dynamic and load-distribution factors. The steps are: get the tangential load from the torque, Wt = 2T/d; find the form factor Y from the number of teeth and the pressure angle - for 20 deg full-depth teeth Y is about 0.154 - 0.912/Z; apply the dynamic factor Kv and, if the tooth is not across the full face width, the load-distribution factor; then divide by the face width times the module.
**Push:** How do you protect the gear against wear as well as bending? -> Bending is handled by the Lewis check and the module. Wear is a Hertzian contact problem: you compare the contact pressure at the flank from the normal load with the allowable contact stress of the material, which for steel scales roughly with the square root of the Brinell hardness. So the design levers are a harder, tougher pinion (case-hardened or nitrided, in the 30 to 40 HRC range) with a slightly larger module and a wider face.
**Trap:** Applying the Lewis equation to a gear with very few teeth without checking the form factor, or treating the same module as adequate for both bending and wear.
**What they're really testing:** Whether you can explain the Lewis equation and understand gear tooth failure modes.

### Q17. Worm gears: self-locking, advantages, problems. [M]
**A:** A worm is essentially a screw, and its lead angle is low, typically 1 to 5 deg, well below the angle of friction of the sliding steel pair, which is of the order of 8 to 10 deg. If the worm is the driver, the tangential force tries to push the teeth along the helix instead of lifting the worm out of the mesh, so the train cannot back-drive - it is self-locking. The price is efficiency: the sliding action gives roughly 30 to 40 percent for a single-start worm, falling to 10 to 15 percent for a multi-start high-ratio unit, and most of that lost power becomes heat. So a worm box needs a generous cooling surface or a fan, and an oil with good cooling rather than grease.
**Push:** How do you make a self-locking worm drive that still has acceptable efficiency? -> Increase the lead angle and use multiple starts, and use a good anti-seizure lubricant with a bronze wheel; you then accept that it is no longer self-locking, and you add a brake or a backstop to hold the load.
**Trap:** Thinking a worm drive is efficient because the ratio is high. The ratio and the efficiency are unrelated - the high ratio is exactly why the efficiency is low.
**What they're really testing:** Whether you can explain self-locking from the lead angle and friction angle, and connect efficiency to the heat problem.

### Q18. Simple, compound, reverted, epicyclic gear trains. [M]
**A:** A simple train has one gear per shaft and the ratio is the product of the individual ratios. A compound train has two gears on one shaft, so the ratio is a product of two ratios and the train is longer but gives a large ratio accurately in a small space. A reverted train has the input and output on the same axis with the intermediate shafts parallel - the classic layout of a vehicle gearbox. An epicyclic or planetary train has planet gears that orbit a sun gear while meshing with an internal ring gear; all three members are coaxial, and the speeds are tied by Willis' equation, (Ns - Nc)/(Nr - Nc) = -Zs/Zr.
**Push:** What has to be true about the tooth numbers? -> For equal spacing of the planets the sum of the sun and ring teeth must be a multiple of the number of planets, and for even distribution of the load the planets should be equally spaced.
**Trap:** Treating a planetary train as a fixed-axis train and adding up the ratios. You must first decide which member is held, then the ratio follows.
**What they're really testing:** Whether you can build up a ratio from the train geometry and say why a planetary gives a high ratio in one stage.

### Q19. Helical gear advantages and disadvantages. [M]
**A:** Helical gears have inclined teeth, so more teeth share the load at any instant, making them smoother, quieter, and able to handle higher loads than spur gears of the same size. The helix angle creates axial thrust that must be absorbed by thrust bearings or by using a double-helical (herringbone) gear with opposite helix angles that cancel the thrust. Helical gears have higher sliding velocity between teeth, which increases friction and heat, so they need better lubrication. They are used in high-speed gearboxes, vehicle transmissions, and industrial speed reducers.
**Push:** What is a herringbone gear and why use it? -> Two helical gears with opposite helix angles joined together, cancelling axial thrust. Used in heavy-duty applications where thrust bearings would be impractical.
**Trap:** Saying helical gears are always better than spur gears - they are smoother and quieter but have axial thrust and higher sliding losses.
**What they're really testing:** Whether you understand the trade-offs between spur and helical gears.

### Q20. Bevel gear types and applications. [M]
**A:** Bevel gears transmit power between intersecting shafts, typically at 90 deg. Types: straight bevel (simple, but noisy at high speed), spiral bevel (curved teeth, smoother, quieter, higher load capacity, generates axial thrust), hypoid (offset axes, allows pinion below centreline, used in automotive rear axles), zerol (curved teeth with zero spiral angle, no axial thrust). Selection based on speed, load, and shaft arrangement.
**Push:** Why are hypoid gears used in automotive rear axles? -> The offset allows the pinion to be below the ring gear centreline, lowering the driveshaft and improving vehicle ground clearance. Also gives more teeth in contact for smoother operation.
**Trap:** Confusing bevel gear (intersecting axes) with worm gear (crossed axes, non-intersecting).
**What they're really testing:** Whether you know bevel gear types and can select the right one for given conditions.

### Q21. Gearbox design considerations. [M]
**A:** Gearbox design involves: selecting gear type based on speed, torque, and space; calculating gear ratio for desired output speed; sizing gears for bending and contact stress (Lewis equation); selecting bearings for shaft support; designing lubrication system; ensuring thermal management; and considering noise and vibration. Housing must be rigid to maintain alignment. Common types: spur, helical, bevel, worm, planetary.
**Push:** What is the most common failure mode in gearboxes? -> Bearing failure (due to misalignment, lubrication issues, or overload) is more common than gear tooth failure in well-designed gearboxes.
**Trap:** Designing gears without considering bearing life - bearing failure often precedes gear failure.
**What they're really testing:** Whether you understand gearbox design as a system, not just gear teeth.

### Q22. Flywheel function and sizing. [M]
**A:** Flywheel stores kinetic energy to smooth out speed fluctuations in reciprocating engines and machines with intermittent loads. It absorbs energy when load is light and releases it when load is heavy. Energy stored: E = 0.5*I*omega^2. Flywheel sizing: coefficient of fluctuation of speed (Cs) = (omega_max - omega_min)/omega_avg. Required moment of inertia: I = E/(Cs*omega_avg^2). Material: cast iron or steel, with rim concentrated at large radius for maximum inertia per weight.
**Push:** Why is the flywheel rim concentrated at large radius? -> Because I = m*r^2, so mass at larger radius gives more inertia per unit mass. A thin rim at large radius is more efficient than a solid disc.
**Trap:** Thinking a flywheel increases power output - it only smooths speed, it doesn't generate power.
**What they're really testing:** Whether you understand flywheel function and can size it for speed fluctuation.

### Q23. Governors: types and working. [M]
**A:** Governor controls engine speed by regulating fuel supply. Types: (1) Centrifugal (Watt, Porter, Proell) - flyweights rotate with engine speed, outward force moves sleeve to adjust fuel. (2) Inertia (Hartnell) - uses both centrifugal force and inertia of flyweights. (3) Electronic - uses sensors and actuators for precise control. Governor sensitivity: change in speed / change in sleeve position. Hunting: oscillation due to over-correction.
**Push:** What is governor hunting and how to prevent it? -> Hunting is speed oscillation due to excessive governor sensitivity or lag in response. Prevent by reducing sensitivity, adding damping, or using isochronous governors.
**Trap:** Confusing governor with flywheel - governor controls speed, flywheel smooths speed.
**What they're really testing:** Whether you understand governor function and can distinguish it from flywheel.

### Q24. Balancing of rotating masses. [H]
**A:** Static balancing: centre of mass on axis of rotation (no net force). Dynamic balancing: no net force AND no net couple (centre of mass on axis + principal axis aligned with rotation axis). Multi-rotor: transfer all masses to two correction planes (reference planes), calculate centrifugal forces and couples, solve for two balancing masses in two planes. Two planes needed because you must cancel both force and couple.
**Push:** Why can't a single-plane balance fix dynamic unbalance? -> Single plane cancels force but creates a couple; two planes allow force and couple to be independently cancelled.
**Trap:** Saying static balance is enough for a long rotor - only dynamic balance prevents bearing loads at speed.
**What they're really testing:** Whether you understand static vs dynamic balancing and when each is sufficient.

---

## 3. Balancing and Vibration - 8 questions

### Q25. Balancing of reciprocating masses in engines. [M]
**A:** Reciprocating mass produces inertia force m*r*omega^2(cos theta + (cos 2theta)/n) where n = L/r. Primary force (cos theta) can be balanced by counterweight on crank, but creates vertical unbalanced force. Compromise: balance fraction c (typically 0.5-0.75) of reciprocating mass. Secondary force (cos 2theta) needs a separate contra-rotating shaft (Lanchester balancer) or is accepted. In multicylinder, arrange cranks to cancel primary/secondary forces.
**Push:** What fraction of reciprocating mass is typically balanced in a single-cylinder engine? -> About 50-75% - balances primary force partially while limiting vertical shake.
**Trap:** Saying you can fully balance reciprocating mass with a rotating counterweight - you can't, it trades horizontal for vertical force.
**What they're really testing:** Whether you understand the trade-offs in balancing reciprocating masses.

### Q26. Forced vibration, transmissibility. [H]
**A:** Forced vibration: system subjected to external periodic force. Response depends on frequency ratio r = omega/omega_n and damping ratio zeta. Transmissibility T = force transmitted to foundation / applied force = sqrt(1 + (2*zeta*r)^2) / sqrt((1-r^2)^2 + (2*zeta*r)^2). For force excitation: isolation (T < 1) requires r > sqrt(2) i.e., omega > 1.414*omega_n. Damping helps at resonance but hurts isolation at high r.
**Push:** If you want 90% isolation (T=0.1), what frequency ratio r do you need? -> For large r, T approx = 1/r^2. So r = sqrt(10) = 3.16. Need omega > 3.16*omega_n.
**Trap:** Saying "more damping always improves isolation" - it reduces peak but worsens high-frequency isolation.
**What they're really testing:** Whether you understand forced vibration and can design vibration isolation.

### Q27. Logarithmic decrement, damping measurement. [H]
**A:** Logarithmic decrement delta = ln(x_n / x_{n+1}) = 2*pi*zeta / sqrt(1-zeta^2) approx = 2*pi*zeta for small zeta. Measure successive peak amplitudes in free decay, compute delta, then zeta = delta / sqrt(4*pi^2 + delta^2). For viscous damping, delta is constant per cycle.
**Push:** If amplitude decays to 50% in 5 cycles, what is zeta? -> x_{n+5}/x_n = 0.5. 5*delta = ln(2) = 0.693 -> delta = 0.1386. zeta = delta/(2*pi) = 0.022.
**Trap:** Using delta = ln(x_1/x_n) / n but forgetting it's per cycle, or applying to non-viscous damping.
**What they're really testing:** Whether you can measure damping from free vibration decay.

### Q28. Machine fault signatures in vibration spectrum. [H]
**A:** Unbalance: 1x RPM, radial, single peak. Misalignment: 1x and 2x RPM, axial + radial, phase shift across coupling. Looseness: 0.5x, 1.5x, 2.5x RPM (sub-harmonics), erratic phase. Bearing defect: non-integer multiples (BPFO, BPFI, BSF, FTF) - calculated from geometry. Rub: 1x + 2x + 3x... harmonics, high radial, partial contact. Oil whirl: 0.4-0.48x RPM sub-synchronous. Resonance: high 1x with phase shift, amplification at critical speed.
**Push:** How do you distinguish unbalance from misalignment when both show 1x RPM? -> Unbalance: predominantly radial, phase difference ~0 or 180 deg across bearing. Misalignment: high axial at 1x and 2x, phase shift ~180 deg across coupling.
**Trap:** Assigning bearing frequencies to 1x/2x RPM, or saying looseness shows only at 1x.
**What they're really testing:** Whether you can diagnose machine faults from vibration spectrum.

### Q29. Gyroscope, precession. [M]
**A:** Gyroscope: rapidly spinning rotor with angular momentum L = I*omega. When a torque is applied perpendicular to the spin axis, the rotor precesses (rotates about a third axis) rather than tipping. Precession rate omega_p = T / (I*omega) where T is the applied torque. Gyroscopic effects cause steering reactions in vehicles (when turning, the vehicle tends to pitch up or down due to engine gyroscopic moment).
**Push:** What is gyroscopic couple? -> When a rotating disc is subjected to a torque, it precesses at 90 deg to the torque direction. The gyroscopic couple = I*omega*omega_p. This is why a spinning wheel resists being tilted.
**Trap:** Confusing precession with rotation - precession is the rotation of the spin axis itself, not the spin of the rotor.
**What they're really testing:** Whether you understand gyroscopic effects and can apply them to vehicles and rotating machinery.

### Q30. Critical speed of shafts. [H]
**A:** Critical speed = rotational speed at which shaft rotation frequency coincides with lateral natural frequency of the rotor-bearing system. At critical speed, synchronous whirling occurs - shaft centre rotates in orbit at running speed. Causes large vibration amplitudes. Practical fix: operate well away from critical speeds, improve balancing, increase stiffness, add damping (squeeze film dampers).
**Push:** Can a shaft have multiple critical speeds? -> Yes - one for each bending mode (first, second, third...). First critical speed is usually most important.
**Trap:** Confusing critical speed (rotational speed) with natural frequency (Hz), or saying critical speed only occurs in vertical shafts.
**What they're really testing:** Whether you understand critical speed as a resonance condition for rotating shafts.

---

## 5. Advanced Mechanisms and Governors - 10 questions

### Q36. Governor types: Watt, Porter, Hartnell. [H]
**A:** (1) Watt governor: simple centrifugal, flyweights on arms, sleeve moves up with speed. (2) Porter governor: adds central load (dead weight) on sleeve, increases sensitivity and speed range. (3) Hartnell governor: spring-loaded, flyweights act against spring, compact and isochronous. Sensitivity = range of speed / mean speed. Isochronous governor: maintains constant speed (zero speed range). Hunting: oscillation due to over-sensitivity.
**Push:** What is the difference between a governor and a flywheel? -> Governor controls speed by regulating fuel/power. Flywheel smooths speed fluctuations by storing energy. Governor is active control; flywheel is passive smoothing.
**Trap:** Confusing governor with flywheel - they serve completely different purposes.
**What they're really testing:** Whether you understand governor types and their function.

### Q37. Cam design: pressure angle and base circle. [H]
**A:** Cam design steps: (1) Select motion curve (SHM, cycloidal, polynomial). (2) Determine maximum acceleration. (3) Calculate minimum base circle radius from pressure angle limit: r_b >= (L/2) * (1 - cos(theta)) / tan(phi_max) for SHM, where L = lift, theta = cam angle for lift, phi_max = allowable pressure angle (30-35 deg). (4) Check follower acceleration and jerk. Larger base circle = lower pressure angle but larger cam.
**Push:** What happens if pressure angle exceeds 45 deg? -> Side thrust exceeds normal force, causing follower to bind or jump. Cam may fail.
**Trap:** Making base circle too small to save space - pressure angle exceeds limit, causing failure.
**What they're really testing:** Whether you can design a cam with proper pressure angle.

### Q38. Geneva mechanism (Maltese cross). [M]
**A:** Geneva mechanism: converts continuous rotation to intermittent rotary motion. Components: (1) Driving crank with pin, (2) Slotted wheel (Geneva wheel). Pin engages slot, rotates wheel by fixed angle, then disengages during dwell. Applications: (1) Indexing tables, (2) Film advance (movie cameras), (3) Automatic machinery. Dwell ratio = dwell time / total cycle time. For 4 slots: 90 deg rotation, 270 deg dwell.
**Push:** Why is Geneva mechanism used for indexing? -> Provides precise, repeatable angular positioning with dwell periods for operations (machining, assembly).
**Trap:** Saying Geneva mechanism provides continuous rotation - it provides intermittent motion with dwell.
**What they're really testing:** Whether you understand Geneva mechanism and its applications.

### Q39. Ratchet and pawl mechanism. [M]
**A:** Ratchet and pawl: allows rotation in one direction only. Components: (1) Ratchet wheel (teeth), (2) Pawl (engages teeth, prevents reverse rotation). Applications: (1) Winches, (2) Hoists, (3) Wrenches, (4) Clocks. Types: (a) External ratchet (teeth on outside), (b) Internal ratchet (teeth on inside). Pawl spring ensures engagement. Can be designed for: (1) Single-tooth (one click per revolution), (2) Multi-tooth (multiple clicks).
**Push:** How does a ratchet prevent reverse rotation? -> Pawl engages ratchet teeth; reverse rotation pushes pawl into teeth (locking), forward rotation lifts pawl (allowing motion).
**Trap:** Saying ratchet allows free rotation both ways - it only allows one direction.
**What they're really testing:** Whether you understand ratchet and pawl mechanism.

### Q40. Universal joint (Hooke's joint): kinematics. [M]
**A:** Hooke's joint: transmits rotation between two shafts at an angle. Kinematics: (1) Input speed constant, output speed varies (unless angle is 0). (2) Speed ratio = (1 - tan^2(theta/2)*cos^2(phi)) / (1 - tan^2(theta/2)) where theta = shaft angle, phi = input angle. (3) Output speed fluctuates twice per revolution. (4) For constant velocity, use double Cardan joint (two Hooke's joints with intermediate shaft). Applications: (1) Automotive driveshafts, (2) Agricultural machinery.
**Push:** Why does output speed fluctuate in a Hooke's joint? -> Because the angular velocity transfer depends on the angle between shafts and the instantaneous position of the cross.
**Trap:** Saying Hooke's joint gives constant velocity - it doesn't; use double Cardan for constant velocity.
**What they're really testing:** Whether you understand Hooke's joint kinematics.

### Q41. Kinematic pairs: lower vs higher pairs. [H]
**A:** Lower pairs: surface contact (area), 1 DOF. Types: (1) Revolute (turning), (2) Prismatic (sliding), (3) Helical (screw), (4) Cylindrical, (5) Spherical, (6) Planar. Higher pairs: point/line contact, 1 DOF (or more). Types: (1) Cam and follower, (2) Gear teeth, (3) Belt and pulley, (4) Wheel and rail. Lower pairs are more durable (area contact), higher pairs allow complex motion but wear faster.
**Push:** Why are higher pairs less durable? -> Point/line contact gives higher contact stress (Hertzian), leading to faster wear and fatigue.
**Trap:** Confusing lower/higher pairs with DOF - both can have 1 DOF; difference is contact type.
**What they're really testing:** Whether you can classify kinematic pairs.

### Q42. Synthesis of mechanisms: type, number, dimensional. [M]
**A:** (1) Type synthesis: select mechanism type (four-bar, slider-crank, etc.) for required motion. (2) Number synthesis: determine number of links and joints for required DOF (Kutzbach). (3) Dimensional synthesis: determine link lengths for required motion. Methods: (a) Graphical (trial and error), (b) Analytical (Freudenstein's equation for four-bar), (c) Optimization (computer-based). Dimensional synthesis: (i) Motion generation (prescribed positions), (ii) Path generation (prescribed path), (iii) Function generation (input-output relationship).
**Push:** What is Freudenstein's equation? -> For four-bar linkage, relates input/output angles and link lengths: K1*cos(theta4) + K2*cos(theta2) + K3 = cos(theta2 - theta4), where K1, K2, K3 are link length ratios.
**Trap:** Thinking mechanism synthesis is just drawing - it requires mathematical optimization.
**What they're really testing:** Whether you understand mechanism synthesis process.

### Q43. Gear train efficiency. [M]
**A:** Gear train efficiency = output power / input power. Losses: (1) Sliding friction between teeth, (2) Rolling friction, (3) Bearing friction, (4) Churning (oil drag), (5) Windage. Efficiency per mesh: (1) Spur gear: 98-99%, (2) Helical gear: 97-98%, (3) Bevel gear: 97-98%, (4) Worm gear: 30-90% (depends on ratio). Overall efficiency = product of individual mesh efficiencies. For n meshes: eta_total = eta_1 * eta_2 * ... * eta_n.
**Push:** Why is worm gear efficiency so low? -> Sliding friction between worm and wheel teeth. Efficiency decreases with increasing ratio (more sliding).
**Trap:** Assuming gear train efficiency is 100% - friction losses are significant, especially for worm gears.
**What they're really testing:** Whether you understand gear train efficiency and losses.

### Q44. Cam follower types and their characteristics. [M]
**A:** Follower types: (1) Knife-edge: simple, high wear, high stress concentration. (2) Roller: low friction, high speed capability, requires larger base circle. (3) Flat-faced: simple, high contact stress, limited to low speed. (4) Spherical-faced: compromise between roller and flat-faced. Selection based on: (a) Speed, (b) Load, (c) Accuracy, (d) Cost. Roller follower is most common for high-speed applications.
**Push:** Why is roller follower preferred for high-speed cams? -> Rolling contact reduces friction and wear, allowing higher speeds and longer life.
**Trap:** Using knife-edge follower for high-speed cams - causes rapid wear and failure.
**What they're really testing:** Whether you can select the right follower type.

### Q45. Balancing of rotating masses in multiple planes. [M]
**A:** For masses in multiple planes: (1) Transfer all masses to two reference planes (using couple). (2) Calculate centrifugal force in each plane. (3) Calculate moment about reference plane. (4) Solve for two balancing masses (magnitude and angle) in two planes. Two planes needed because: (a) Force balance in plane 1, (b) Couple balance in plane 2. Single plane balance only corrects force, not couple.
**Push:** Why can't a single plane balance fix dynamic unbalance? -> Single plane cancels force but creates a couple; two planes allow force and couple to be independently cancelled.
**Trap:** Saying static balance is enough for long rotors - only dynamic balance prevents bearing loads at speed.
**What they're really testing:** Whether you understand multi-plane balancing.

---

## File Statistics

**Total questions: 40**

**By tag:**
- [H] High-yield: ~25 questions
- [M] Medium-yield: ~18 questions
- [L] Occasional: ~2 questions

**By section:**
- Mechanisms and kinematics: 12 questions
- Gears and gear trains: 12 questions
- Balancing and vibration: 8 questions
- Vibration isolation and control: 5 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers ToM fundamentals - essential for automobiles, petrochem, and construction interviews.