# Theory of Machines / Mechanisms and Engineering Mechanics - L&T GET technical interview bank

**Part 6 of 8 | 26 questions | Mechanisms DOF, linkage synthesis, cams, governors, balancing, FBD, equilibrium, friction, trusses, stress basics, kinematics, energy**

*Mechanical GET panel, 30-45 min, GATE-lite depth. Tags: [H] asked very commonly, [M] asked regularly, [L] occasional. Do not memorise the wording - memorise the idea, then say it in your own words. If you cannot say it out loud in 60 seconds, you have not learned it yet. The interviewer is not testing recall, they are testing whether you can reason out loud.*

## 1. Theory of Machines / Mechanisms - 14 questions

### Q1. What is degrees of freedom in a mechanism, and how do you calculate it for a planar mechanism using Kutzbach criterion? [H]

**A:** Degrees of freedom (DOF) is the number of independent parameters needed to define the position of all links. For planar mechanisms, Kutzbach formula is F = 3(n-1) - 2j1 - j2, where n = number of links, j1 = lower pairs (revolute/prismatic), j2 = higher pairs (cam/gear). F > 0 means unconstrained motion, F = 0 is a structure, F < 0 is overconstrained (preloaded). A designer uses DOF to check if a linkage will move as intended or lock up.

**Push:** What is the DOF of a four-bar linkage? n=4, j1=4 -> F = 3(3) - 2(4) = 1. It has one input, fully defined.

**Trap:** Using the spatial formula F = 6(n-1) - 5j1 - 4j2... for planar mechanisms - that's for 3D, not planar.

### Q2. Explain Grashof's law for a four-bar linkage and its four cases. [H]

**A:** For a four-bar with links s (shortest), l (longest), p, q (intermediate): if s + l <= p + q, the shortest link can fully rotate - Grashof condition satisfied. Four cases: (1) s is ground link -> double crank (drag link), both cranks rotate fully. (2) s is coupler -> double rocker, no full rotation. (3) s is adjacent to ground -> crank-rocker, one crank one rocker. (4) s is opposite ground -> rocker-crank, same as case 3 but inverted. If s + l > p + q, it's a non-Grashof double rocker.

**Push:** How do you quickly identify which link is the crank? The link adjacent to ground that can rotate 360 deg is the crank; the other moving link is the rocker.

**Trap:** Confusing which link is s or l, or forgetting that Grashof is necessary but not sufficient - you also need to check assembly mode.

### Q3. What is a crank-rocker mechanism, and where would you use it? [H]

**A:** Crank-rocker is a Grashof four-bar where the shortest link is adjacent to ground. The shortest link (crank) rotates fully; the opposite link (rocker) oscillates. Converts continuous rotation to reciprocating oscillation. Used in windshield wipers, sewing machine needle drive, pump reciprocating mechanisms, packaging machines.

**Push:** How do you change the rocker's stroke angle? Change the link lengths - longer coupler or rocker increases stroke, but check Grashof still holds.

**Trap:** Saying crank-rocker gives linear motion - it gives angular oscillation; slider-crank gives linear.

### Q4. Describe the quick return mechanism and its applications. [H]

**A:** Quick return mechanism makes the forward (working) stroke slower and the return stroke faster. Achieved by offsetting the crank centre or using Whitworth mechanism. Time ratio (forward/return) > 1. Used in shapers, slotters, planers, printing presses, broaching machines - any tool where cutting happens in one direction only.

**Push:** What is the time ratio for a standard Whitworth quick return? Time ratio = (180 + alpha) / (180 - alpha) where alpha is the angle between the two extreme crank positions.

**Trap:** Confusing quick return with constant velocity - the whole point is unequal speeds.

### Q5. Explain the Whitworth quick return mechanism and what inversion changes. [M]

**A:** Whitworth uses a slider-crank with the crank fixed (inversion 2). The slotted lever oscillates as the block slides in the slot. Inversion changes which link is grounded: ground the crank -> Whitworth; ground the connecting rod -> oscillating cylinder engine; ground the slider -> hand pump. The relative motion between links stays the same, but absolute motion changes - different input/output roles.

**Push:** Which inversion gives a rotary-to-oscillating converter? Fixing the crank (Whitworth) gives rotary input, oscillating output.

**Trap:** Thinking inversion changes the mechanism's kinematics - it only changes the reference frame.

### Q6. What are the key terms in a slider-crank mechanism, and what is the difference between in-line and offset? [H]

**A:** Links: crank (rotating), connecting rod (coupler), slider (reciprocating), frame (ground). In-line: crank centre, slider path, and connecting rod all lie in same line when crank at 0/180 deg - symmetric motion, equal time forward/return. Offset: slider path is offset by distance e from crank centre - gives quick return, asymmetric stroke, used when cutting load is only in one direction.

**Push:** How does offset affect maximum piston velocity? Offset increases max velocity on one stroke and decreases on the other; also shifts the crank angle of max velocity.

**Trap:** Saying offset slider-crank has equal forward/return time - that's in-line only.

### Q7. What are straight-line motion mechanisms, and name one exact and one approximate? [M]

**A:** Mechanisms that generate exact or near-exact straight-line motion from rotary input. Exact: Peaucellier cell (8 links, inversor), Hart's A-frame (6 links). Approximate: Watt's linkage (3 links, straight line near centre), Chebyshev linkage, Robert's mechanism. Used in early steam engine crossheads, suspension systems, robot end-effector guidance.

**Push:** Why did Watt's linkage replace the Peaucellier in practice? Peaucellier is exact but complex (8 links, more joints, wear); Watt's is 3 links, good enough for limited travel.

**Trap:** Saying all straight-line mechanisms are exact - most practical ones are approximate.

### Q8. What are the types of cams and followers, and how does cam profile depend on follower motion? [H]

**A:** Cams: radial (disc) or cylindrical. Followers: translating (radial/offset) or oscillating. Follower faces: knife-edge (sharp, high wear), roller (low friction, common), flat-faced (simple, high contact stress), spherical-faced. Cam profile is the envelope of follower positions for the desired motion curve. Given follower motion (displacement vs cam angle), you invert the motion to generate cam surface - each profile point is the follower centre at that angle.

**Push:** Why use a roller follower over knife-edge? Roller reduces friction and wear, allows higher speeds; knife-edge wears fast and jams.

**Trap:** Thinking cam profile = follower displacement curve - they are different; profile is the physical surface.

### Q9. Compare SHM, cycloidal, and constant velocity motion profiles for cams. [H]

**A:** SHM: simple sine displacement, smooth velocity/acceleration, but infinite jerk at start/end - causes vibration. Cycloidal: sine acceleration, zero jerk at boundaries, smoothest, best for high speed. Constant velocity: infinite acceleration at boundaries (impossible physically), only for very slow cams. Cycloidal is standard for high-speed cams; SHM for moderate; constant velocity avoided except for dwell transitions.

**Push:** Which profile gives minimum maximum acceleration for a given lift and duration? Cycloidal - its acceleration is sinusoidal with lower peak than SHM.

**Trap:** Using constant velocity for high-speed cams - causes infinite jerk, destroys mechanism.

### Q10. What is pressure angle in a cam, and how does it affect performance? [M]

**A:** Pressure angle is the angle between the follower motion direction and the normal to the cam profile at the contact point. High pressure angle -> high side thrust on follower -> increased friction, wear, bending stress, possible jamming. Limit: < 30 deg for translating followers, < 35-40 deg for oscillating. Increase base circle radius or reduce lift to reduce pressure angle.

**Push:** What happens if pressure angle exceeds 45 deg? Side thrust exceeds normal force - follower binds, chatters, or jumps; cam may need spring preload which increases wear.

**Trap:** Ignoring pressure angle when designing high-lift cams - it's the primary limit on lift for a given base circle.

### Q11. Explain the relative velocity method and instantaneous centre method for velocity analysis. [H]

**A:** Relative velocity: v_B = v_A + v_B/A (vector sum). For a rigid link, v_B/A is perpendicular to AB. Draw velocity polygon, solve unknowns. Instantaneous centre (IC): point on two links with same velocity. Kennedy's theorem: three bodies in plane motion have three ICs lying on a straight line. Find all ICs, then v = omega x r from IC. IC method is faster for 4-bar; velocity polygon works for any mechanism.

**Push:** How many ICs does a 6-link mechanism have? n(n-1)/2 = 15 ICs.

**Trap:** Forgetting that IC location changes with configuration - it's instantaneous, not fixed.

### Q12. What is Coriolis acceleration, and when does it appear in slider-crank analysis? [H]

**A:** Coriolis acceleration = 2 * omega x v_rel, appears when a point moves on a rotating link (sliding contact). In slider-crank, the slider moves on the rotating connecting rod - the slider has Coriolis component perpendicular to rod, magnitude 2*omega_rod*v_slider. Direction: rotate v_rel by 90 deg in direction of omega. Must include it in acceleration polygon or relative acceleration equation.

**Push:** What is the direction of Coriolis acceleration for a slider moving outward on a CCW rotating link? Perpendicular to link, 90 deg ahead of slider velocity in rotation direction.

**Trap:** Missing Coriolis term entirely, or wrong direction - it's the most common error in acceleration analysis.

### Q13. What are the types of balancing, and how do you balance a multi-rotor system? [H]

**A:** Static balancing: centre of mass on axis of rotation (no net force). Dynamic balancing: no net force AND no net couple (centre of mass on axis + principal axis aligned with rotation axis). Multi-rotor: transfer all masses to two correction planes (reference planes), calculate centrifugal forces and couples, solve for two balancing masses in two planes. Two planes needed because you must cancel both force and couple.

**Push:** Why can't a single-plane balance fix dynamic unbalance? Single plane cancels force but creates a couple; two planes allow force and couple to be independently cancelled.

**Trap:** Saying static balance is enough for a long rotor - only dynamic balance prevents bearing loads at speed.

### Q14. How do you balance reciprocating mass in a slider-crank engine? [M]

**A:** Reciprocating mass produces inertia force m*r*omega^2(cos theta + (cos 2theta)/n) where n = L/r. Primary force (cos theta) can be balanced by counterweight on crank, but creates vertical unbalanced force. Compromise: balance fraction c (typically 0.5-0.75) of reciprocating mass. Secondary force (cos 2theta) needs a separate contra-rotating shaft (Lanchester balancer) or is accepted. In multicylinder, arrange cranks to cancel primary/secondary forces.

**Push:** What fraction of reciprocating mass is typically balanced in a single-cylinder engine? About 50-75% - balances primary force partially while limiting vertical shake.

**Trap:** Saying you can fully balance reciprocating mass with a rotating counterweight - you can't, it trades horizontal for vertical force.

## 2. Engineering Mechanics - 12 questions

### Q15. What is a free body diagram, and why does every mechanics solution start with one? [H]

**A:** FBD isolates a body (or system) and shows ALL external forces and moments acting on it - applied loads, reactions at supports, weight, friction. It separates the body from its surroundings so equilibrium equations apply only to the body of interest. Missing a force on FBD = wrong answer. Always draw FBD first, label knowns/unknowns, then write equilibrium equations.

**Push:** What forces do you NOT put on an FBD? Internal forces (between parts of the system), forces the body exerts ON other bodies, accelerations (unless doing d'Alembert).

**Trap:** Forgetting weight, or putting internal forces on the FBD of the whole system.

### Q16. Write the three equilibrium equations for 2D and 3D. [H]

**A:** 2D: Sum Fx = 0, Sum Fy = 0, Sum Mz = 0 (about any point). 3D: Sum Fx = 0, Sum Fy = 0, Sum Fz = 0, Sum Mx = 0, Sum My = 0, Sum Mz = 0. For 2D, you can replace one force equation with a moment equation about a different point (three independent equations total). Choose moment centres to eliminate unknowns.

**Push:** Can you solve a 2D problem with three moment equations? Yes, if the three moment centres are not collinear.

**Trap:** Using Sum M = 0 about a point where all unknown forces pass through - gives 0 = 0, no info.

### Q17. What are two-force and three-force members, and how do they simplify analysis? [M]

**A:** Two-force member: only two forces act on it (at ends). Forces must be equal, opposite, and collinear along the line joining the two points - pure tension/compression. Three-force member: three forces act. If in equilibrium, they must be concurrent (meet at a point) or parallel. Identifying these lets you find force directions immediately without solving - just geometry.

**Push:** If a member has two forces and a moment applied, is it a two-force member? No - the moment makes it a three-load member; forces need not be collinear.

**Trap:** Assuming all truss members are two-force members - only true if loads are applied ONLY at joints.

### Q18. How do you find the resultant of coplanar non-concurrent forces, and what is Varignon's theorem? [M]

**A:** Resultant R = vector sum of all forces. Its line of action is found by equating moments: M_R = Sum M_i about any point. Varignon's theorem: moment of a force about a point equals the sum of moments of its components about that point. A couple is a pair of equal opposite parallel forces separated by distance d - moment = F*d, free vector (same about any point). Resultant of non-concurrent system = single force + couple (or single force if resultant force not zero).

**Push:** Can a system of parallel forces have a resultant couple? Yes, if the vector sum is zero but moments don't cancel - pure couple.

**Trap:** Treating a couple as a force at some point - it's a free vector, moment same everywhere.

### Q19. Why must the net moment on a rotating machine be zero for steady operation? [H]

**A:** Net moment = I * alpha (Newton's second law for rotation). If net moment not zero, alpha != 0 -> angular acceleration -> speed changes. For steady speed (omega constant), alpha = 0, so net moment must be zero. Applied torque = sum of resisting torques (load, friction, windage). If not balanced, machine speeds up or slows down.

**Push:** What happens if a motor torque is slightly less than load torque at steady speed? Motor decelerates until speed drops enough that load torque decreases (e.g., fan load ~omega^2) to match motor torque, or stalls.

**Trap:** Thinking zero net moment means no torque - it means driving torque equals resisting torque.

### Q20. Why does centre of gravity matter in machine design? [H]

**A:** CG is the point where weight acts. Affects: stability (tipping if CG outside base), balancing (rotors must have CG on axis), handling (lifting points), dynamic loads (inertia forces act through CG). For a machine on a moving base, low CG improves stability. For rotating parts, CG offset causes unbalance. Always locate CG in design drawings.

**Push:** How does CG location affect a crane's lifting capacity? Load chart is based on tipping moment - CG of load + boom must stay within outrigger footprint; as boom extends, CG moves out, capacity drops.

**Trap:** Confusing centroid (geometric centre) with CG (mass centre) - same only for uniform density.

### Q21. What is moment of inertia, and why does it appear in every dynamic formula? [H]

**A:** Mass moment of inertia I = integral(r^2 dm) - resistance to angular acceleration. Area moment of inertia (second moment of area) I = integral(y^2 dA) - resistance to bending. Radius of gyration k = sqrt(I/m). Appears because: rotational KE = 0.5 I omega^2, torque = I alpha, angular momentum = I omega, bending stress = M*y/I, torsional stress = T*r/J. It quantifies how mass/area distribution affects response.

**Push:** What is the parallel axis theorem? I = I_cg + m*d^2 - shifts moment of inertia from CG to parallel axis distance d away.

**Trap:** Using area moment of inertia (mm^4) where mass moment of inertia (kg-m^2) is needed, or vice versa.

### Q22. Explain friction circle, self-locking, and the capstan equation. [H]

**A:** Friction circle: for a journal bearing, resultant reaction shifts by angle phi = arctan(mu) from normal; radius = r*sin(phi). Self-locking: when lead angle lambda <= friction angle phi, the screw/nut holds load without brake - condition tan(lambda) <= mu. Capstan equation (belt friction): T2/T1 = e^(mu*theta) where theta is wrap angle in radians. Explains why few wraps hold huge tension ratio.

**Push:** For a screw jack with mu = 0.15 and lead angle 8 deg, is it self-locking? tan(8deg) = 0.14 < 0.15 -> yes, self-locking.

**Trap:** Using degrees in capstan equation - theta must be in radians.

### Q23. A ladder of length L leans against a wall with mu = 0.3 at both floor and wall. How far up can a person climb before it slips? [M]

**A:** Draw FBD of ladder. Forces: weight W at L/2, person weight P at x from bottom, normal N_f and friction f_f = 0.3 N_f at floor, normal N_w and friction f_w = 0.3 N_w at wall. Sum Fx = 0: N_w = f_f = 0.3 N_f. Sum Fy = 0: N_f + f_w = W + P -> N_f + 0.3 N_w = W + P. Sum M about bottom = 0: N_w*L*sin(theta) + f_w*L*cos(theta) = W*(L/2)*cos(theta) + P*x*cos(theta). Solve for x in terms of theta, W, P. Typical result: x_max depends on angle and weight ratio.

**Push:** What if mu is different at floor and wall? Use mu_f and mu_w separately; same method, two different friction limits.

**Trap:** Assuming friction is always mu*N at both contacts - it's mu*N only at impending slip; otherwise friction < mu*N.

### Q24. What are velocity ratio, mechanical advantage, and efficiency of a simple machine? [H]

**A:** VR = distance moved by effort / distance moved by load (kinematic, frictionless). MA = load / effort (actual force ratio). Efficiency eta = MA / VR = (useful work out) / (work in). For ideal machine (no friction), MA = VR, eta = 1. For real machines, MA < VR, eta < 1. VR depends only on geometry; MA depends on friction.

**Push:** If a pulley system has VR = 4 and efficiency 80%, what is MA? MA = eta * VR = 0.8 * 4 = 3.2.

**Trap:** Saying MA can exceed VR - impossible, would violate energy conservation (eta > 1).

### Q25. Explain method of joints and method of sections for truss analysis. [H]

**A:** Method of joints: solve equilibrium at each joint (Sum Fx=0, Sum Fy=0), start at joint with only 2 unknowns. Method of sections: cut through max 3 members, draw FBD of one part, apply 3 equilibrium equations to find forces in cut members directly. Zero-force members: at a joint with only two non-collinear members and no external load, both are zero-force; at a joint with three members where two are collinear and no external load, the third is zero-force. Use zero-force members to simplify.

**Push:** When do you use sections over joints? When you need forces in only a few specific members, especially in middle of large truss.

**Trap:** Cutting more than 3 unknown members in method of sections - makes it statically indeterminate for that cut.

### Q26. What are the basic stress cases, and give the key formula for each? [M]

**A:** Bar in tension/compression: sigma = P/A. Beam in bending: sigma = M*y/I (max at extreme fibre, y = c). Shaft in torsion: tau = T*r/J (max at surface, r = c). Thin-walled pressure vessel: hoop stress = p*r/t, longitudinal = p*r/(2t) (cylinder); sphere: sigma = p*r/(2t). These assume linear elastic, small deformation, homogeneous isotropic material. All derived from equilibrium + compatibility + Hooke's law.

**Push:** What is the stress concentration factor K_t? Ratio of max stress at notch/hole to nominal stress - K_t > 1, depends on geometry, must be checked in fatigue design.

**Trap:** Using bending formula for short beams (shear deformation significant) or thick-walled vessels (radial stress not negligible).

**What they're really testing:** Theory of Machines tests if you can visualise motion, predict forces from kinematics, and size rotating parts for balance. Engineering Mechanics tests if you can isolate a system, draw a correct FBD, and apply equilibrium and energy methods to real structures and machines. Both are about reasoning from first principles, not memorising formulas.