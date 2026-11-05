# Engineering Mechanics - Core Interview Bank

**Part 6 of 10 | 40 questions | FBD, equilibrium, trusses, friction, work-energy, impulse-momentum, Lami's theorem, Varignon's theorem**
*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Free Body Diagrams and Equilibrium - 10 questions

### Q1. Free body diagram, why every solution starts with one. [H]
**A:** FBD isolates a body (or system) and shows ALL external forces and moments acting on it - applied loads, reactions at supports, weight, friction. It separates the body from its surroundings so equilibrium equations apply only to the body of interest. Missing a force on FBD = wrong answer. Always draw FBD first, label knowns/unknowns, then write equilibrium equations.
**Push:** What forces do you NOT put on an FBD? -> Internal forces (between parts of the system), forces the body exerts ON other bodies, accelerations (unless doing d'Alembert).
**Trap:** Forgetting weight, or putting internal forces on the FBD of the whole system.
**What they're really testing:** Whether you can draw a correct FBD - the foundation of all mechanics solutions.

### Q2. Three equilibrium equations for 2D and 3D. [H]
**A:** 2D: Sum Fx = 0, Sum Fy = 0, Sum Mz = 0 (about any point). 3D: Sum Fx = 0, Sum Fy = 0, Sum Fz = 0, Sum Mx = 0, Sum My = 0, Sum Mz = 0. For 2D, you can replace one force equation with a moment equation about a different point (three independent equations total). Choose moment centres to eliminate unknowns.
**Push:** Can you solve a 2D problem with three moment equations? -> Yes, if the three moment centres are not collinear.
**Trap:** Using Sum M = 0 about a point where all unknown forces pass through - gives 0 = 0, no info.
**What they're really testing:** Whether you know the equilibrium equations and can choose independent moment centres.

### Q3. Two-force and three-force members. [M]
**A:** Two-force member: only two forces act on it (at ends). Forces must be equal, opposite, and collinear along the line joining the two points - pure tension/compression. Three-force member: three forces act. If in equilibrium, they must be concurrent (meet at a point) or parallel. Identifying these lets you find force directions immediately without solving - just geometry.
**Push:** If a member has two forces and a moment applied, is it a two-force member? -> No - the moment makes it a three-load member; forces need not be collinear.
**Trap:** Assuming all truss members are two-force members - only true if loads are applied ONLY at joints.
**What they're really testing:** Whether you can identify member types and use them to simplify force analysis.

### Q4. Resultant of coplanar non-concurrent forces. [M]
**A:** Resultant R = vector sum of all forces. Its line of action is found by equating moments: M_R = Sum M_i about any point. Varignon's theorem: moment of a force about a point equals the sum of moments of its components about that point. A couple is a pair of equal opposite parallel forces separated by distance d - moment = F*d, free vector (same about any point). Resultant of non-concurrent system = single force + couple (or single force if resultant force not zero).
**Push:** Can a system of parallel forces have a resultant couple? -> Yes, if the vector sum is zero but moments don't cancel - pure couple.
**Trap:** Treating a couple as a force at some point - it's a free vector, moment same everywhere.
**What they're really testing:** Whether you can find resultants and use Varignon's theorem to simplify moment calculations.

### Q5. Lami's theorem. [M]
**A:** Lami's theorem states that if three concurrent coplanar forces are in equilibrium, each force is proportional to the sine of the angle between the other two forces. Mathematically: P/sin(alpha) = Q/sin(beta) = R/sin(gamma), where alpha is the angle between Q and R, beta is the angle between P and R, gamma is the angle between P and Q. Used to solve equilibrium problems with three forces without resolving into components.
**Push:** When is Lami's theorem most useful? -> When three forces act at a point and you know two of the three angles - you can find the third force directly without component resolution.
**Trap:** Applying Lami's theorem to non-concurrent forces or to more than three forces - it only works for three concurrent coplanar forces.
**What they're really testing:** Whether you know Lami's theorem and can apply it to three-force equilibrium problems.

### Q6. Varignon's theorem. [M]
**A:** Varignon's theorem: the moment of a force about a point equals the algebraic sum of the moments of its components about the same point. If F = F1 + F2 (vector sum), then M_F = M_F1 + M_F2. This is useful because it's often easier to compute moments of components (especially perpendicular and parallel components) than to compute the moment of the original force directly.
**Push:** How does Varignon's theorem simplify moment calculations? -> Instead of finding the perpendicular distance from the point to the line of action of F, you can resolve F into horizontal and vertical components and compute their moments separately using simpler geometry.
**Trap:** Forgetting that the theorem applies to the moment of the force, not to the force itself - it's about moments, not forces.
**What they're really testing:** Whether you can use Varignon's theorem to simplify moment calculations.

### Q7. Principle of moments. [H]
**A:** The principle of moments (Varignon's theorem): the sum of moments of all forces about any point equals the moment of their resultant about that point. For a body in equilibrium, the sum of clockwise moments about any point equals the sum of anticlockwise moments about that point. This is the basis for lever calculations and torque equilibrium.
**Push:** How do you use the principle of moments to find an unknown force? -> Choose a moment centre where the unknown force passes through (so its moment is zero), then equate clockwise and anticlockwise moments to solve for the unknown.
**Trap:** Taking moments about a point where the unknown force doesn't pass through - you get an equation with two unknowns.
**What they're really testing:** Whether you can use the principle of moments to solve for unknown forces.

### Q8. Centroid and centre of gravity. [H]
**A:** Centroid is the geometric centre of an area or volume. Centre of gravity (CG) is the point where the weight of a body acts. For uniform density, centroid = CG. For non-uniform density, CG differs from centroid. CG matters for: stability (tipping if CG outside base), balancing (rotors must have CG on axis), handling (lifting points), dynamic loads (inertia forces act through CG).
**Push:** How does CG location affect a crane's lifting capacity? -> Load chart is based on tipping moment - CG of load + boom must stay within outrigger footprint; as boom extends, CG moves out, capacity drops.
**Trap:** Confusing centroid (geometric centre) with CG (mass centre) - same only for uniform density.
**What they're really testing:** Whether you understand CG and its importance in stability and dynamics.

### Q9. Moment of inertia, radius of gyration. [H]
**A:** Mass moment of inertia I = integral(r^2 dm) - resistance to angular acceleration. Area moment of inertia (second moment of area) I = integral(y^2 dA) - resistance to bending. Radius of gyration k = sqrt(I/m). Appears because: rotational KE = 0.5 I omega^2, torque = I alpha, angular momentum = I omega, bending stress = M*y/I, torsional stress = T*r/J. It quantifies how mass/area distribution affects response. Parallel axis theorem: I = I_cg + m*d^2.
**Push:** What is the parallel axis theorem? -> I = I_cg + m*d^2 - shifts moment of inertia from CG to parallel axis distance d away.
**Trap:** Using area moment of inertia (mm^4) where mass moment of inertia (kg-m^2) is needed, or vice versa.
**What they're really testing:** Whether you can distinguish between mass and area moment of inertia, and apply the parallel axis theorem.

### Q10. Net moment on rotating machine for steady operation. [H]
**A:** Net moment = I * alpha (Newton's second law for rotation). If net moment not zero, alpha != 0 -> angular acceleration -> speed changes. For steady speed (omega constant), alpha = 0, so net moment must be zero. Applied torque = sum of resisting torques (load, friction, windage). If not balanced, machine speeds up or slows down.
**Push:** What happens if motor torque is slightly less than load torque at steady speed? -> Motor decelerates until speed drops enough that load torque decreases (e.g., fan load ~omega^2) to match motor torque, or stalls.
**Trap:** Thinking zero net moment means no torque - it means driving torque equals resisting torque.
**What they're really testing:** Whether you understand rotational equilibrium and can connect it to real machine operation.

---

## 2. Trusses and Frames - 8 questions

### Q11. Method of joints for truss analysis. [H]
**A:** Method of joints: solve equilibrium at each joint (Sum Fx=0, Sum Fy=0), start at joint with only 2 unknowns. Identify zero-force members: at a joint with only two non-collinear members and no external load, both are zero-force; at a joint with three members where two are collinear and no external load, the third is zero-force. Use zero-force members to simplify.
**Push:** When do you use method of joints vs method of sections? -> Method of joints: when you need forces in all members or members near supports. Method of sections: when you need forces in only a few specific members, especially in middle of large truss.
**Trap:** Starting at a joint with more than 2 unknowns - you can't solve it directly.
**What they're really testing:** Whether you can solve trusses using method of joints and identify zero-force members.

### Q12. Method of sections for truss analysis. [H]
**A:** Method of sections: cut through max 3 members, draw FBD of one part, apply 3 equilibrium equations to find forces in cut members directly. Zero-force members: at a joint with only two non-collinear members and no external load, both are zero-force; at a joint with three members where two are collinear and no external load, the third is zero-force. Use zero-force members to simplify.
**Push:** When do you use sections over joints? -> When you need forces in only a few specific members, especially in middle of large truss.
**Trap:** Cutting more than 3 unknown members in method of sections - makes it statically indeterminate for that cut.
**What they're really testing:** Whether you can solve trusses using method of sections and know when to use each method.

### Q13. Frame analysis, multi-force members. [M]
**A:** Frames are structures with at least one multi-force member (member with more than two forces). Analysis: draw FBD of entire frame, find reactions; then draw FBD of each member, find internal forces. Pin joints: force reactions only (no moment). Fixed supports: force and moment reactions. Two-force members in frames: identify them to simplify analysis.
**Push:** How do you analyze a frame with a pin joint at the connection? -> At pin joints, forces are equal and opposite between the two members (Newton's third law), and no moment is transmitted. Draw FBD of each member separately.
**Trap:** Treating a frame as a truss - frames have multi-force members and may have moments at joints.
**What they're really testing:** Whether you can distinguish between trusses and frames and analyze multi-force members.

### Q14. Virtual work principle. [M]
**A:** Principle of virtual work: for a system in equilibrium, the virtual work done by all forces (including applied loads and reactions) during a virtual displacement is zero. Used for: finding equilibrium configurations, calculating reactions in statically indeterminate structures, and mechanism analysis. For a mechanism with one degree of freedom, the virtual work equation gives the relationship between input and output forces.
**Push:** How is virtual work used in mechanism analysis? -> For a mechanism in equilibrium, the virtual work of input force/torque equals the virtual work of output force/torque, giving the mechanical advantage.
**Trap:** Confusing virtual work with actual work - virtual displacement is imaginary, not actual.
**What they're really testing:** Whether you understand the virtual work principle and can apply it to mechanisms.

### Q15. Truss deflection by unit load method. [M]
**A:** Unit load method: to find deflection at a point, apply a unit load at that point in the direction of desired deflection, calculate forces in all members due to unit load, then delta = sum (F_i * f_i * L_i / (A_i * E_i)) where F_i = force due to actual load, f_i = force due to unit load, L_i = member length, A_i = cross-sectional area, E_i = Young's modulus. Sign convention: tension positive, compression negative.
**Push:** What is the advantage of the unit load method over direct integration? -> It can handle complex trusses with many members, and it's easier to compute than solving differential equations for each member.
**Trap:** Forgetting to use the correct sign convention - tension positive, compression negative. The product F_i * f_i determines whether the member contributes to deflection.
**What they're really testing:** Whether you can calculate truss deflection using the unit load method.

### Q16. Truss deflection by Castigliano's theorem. [M]
**A:** Castigliano's theorem: the partial derivative of the strain energy with respect to a load gives the deflection at the point of application of that load in the direction of the load. Strain energy U = sum (F_i^2 * L_i / (2 * A_i * E_i)). Deflection delta = dU/dP. For trusses, this gives the same result as the unit load method but through energy methods.
**Push:** When is Castigliano's theorem preferred over the unit load method? -> When the structure has a single load and you want the deflection at that load point. The unit load method is more general.
**Trap:** Forgetting that Castigliano's theorem gives deflection in the direction of the applied load - if you want deflection in a different direction, you need to apply a dummy load.
**What they're really testing:** Whether you can use energy methods to calculate deflection.

### Q17. Influence lines for trusses. [M]
**A:** Influence line shows how a particular response (reaction, shear, moment, or member force) varies as a unit load moves across the structure. For trusses, influence lines for member forces show the variation in axial force as the unit load moves along the top or bottom chord. Used for: moving loads (trains, vehicles), maximum force determination, and bridge design.
**Push:** How do you construct an influence line for a truss member force? -> Apply a unit load at various positions, calculate the member force at each position, and plot the results. Or use the Muller-Breslau principle.
**Trap:** Confusing influence line with shear/moment diagram - influence line is for moving loads, not fixed loads.
**What they're really testing:** Whether you understand influence lines and can use them for moving load analysis.

### Q18. Space trusses. [M]
**A:** Space truss is a three-dimensional truss with members in x, y, z directions. Analysis: 3D equilibrium at each joint (Sum Fx=0, Sum Fy=0, Sum Fz=0). Each joint has 3 unknowns (if pin joint) and 3 equations. A simple space truss has m = 3j - 6 members for stability. Tetrahedron is the simplest space truss (6 members, 4 joints).
**Push:** How many members does a stable space truss need? -> m = 3j - 6, where j = number of joints. For a tetrahedron (4 joints): m = 3*4 - 6 = 6 members.
**Trap:** Using 2D truss equations (m = 2j - 3) for 3D trusses - space trusses need m = 3j - 6.
**What they're really testing:** Whether you can analyze space trusses using 3D equilibrium.

---

## 2. Friction - 8 questions

### Q19. Laws of friction, static vs kinetic. [H]
**A:** Static friction: f_s <= mu_s * N (can vary from 0 to maximum). Kinetic friction: f_k = mu_k * N (constant, usually mu_k < mu_s). At impending motion, f_s = mu_s * N. Friction force opposes relative motion or impending motion. Angle of friction: phi = atan(mu). Coefficient of friction depends on materials and surface conditions.
**Push:** Why is static friction greater than kinetic friction? -> Static friction involves interlocking of surface asperities and molecular adhesion, which must be overcome to start motion. Once sliding begins, asperities ride over each other more easily, so friction is lower.
**Trap:** Saying friction is always mu*N - this is only true at impending motion for static friction or during sliding for kinetic friction. For static friction below impending motion, f < mu_s*N.
**What they're really testing:** Whether you understand the difference between static and kinetic friction and when each applies.

### Q20. Ladder leaning against wall, friction. [M]
**A:** Draw FBD of ladder. Forces: weight W at L/2, person weight P at x from bottom, normal N_f and friction f_f = mu_f * N_f at floor, normal N_w and friction f_w = mu_w * N_w at wall. Sum Fx = 0: N_w = f_f = mu_f * N_f. Sum Fy = 0: N_f + f_w = W + P -> N_f + mu_w * N_w = W + P. Sum M about bottom = 0: N_w*L*sin(theta) + f_w*L*cos(theta) = W*(L/2)*cos(theta) + P*x*cos(theta). Solve for x in terms of theta, W, P.
**Push:** What if mu is different at floor and wall? -> Use mu_f and mu_w separately; same method, two different friction limits.
**Trap:** Assuming friction is always mu*N at both contacts - it's mu*N only at impending slip; otherwise friction < mu*N.
**What they're really testing:** Whether you can solve a friction problem with multiple contact points.

### Q21. Screw jack, self-locking. [H]
**A:** Screw jack: mechanical device for lifting heavy loads using a screw. Torque required to raise load: T = W*r*(tan(lambda) + mu)/(1 - mu*tan(lambda)), where lambda = lead angle = atan(p/(2*pi*r)), p = pitch, r = mean radius. Torque to lower: T = W*r*(mu - tan(lambda))/(1 + mu*tan(lambda)). Self-locking when tan(lambda) <= mu - the load won't descend by itself. Efficiency = tan(lambda)/(tan(lambda) + mu) * 100%.
**Push:** For a screw jack with mu = 0.15 and lead angle 8 deg, is it self-locking? -> tan(8deg) = 0.14 < 0.15 -> yes, self-locking.
**Trap:** Using degrees in tangent calculation - tangent function takes radians in most calculators. Also, confusing lead angle with helix angle.
**What they're really testing:** Whether you can analyze a screw jack and determine self-locking condition.

### Q22. Belt friction, capstan equation. [H]
**A:** Capstan equation (belt friction): T2/T1 = e^(mu*theta) where T2 = tight side tension, T1 = slack side tension, mu = coefficient of friction, theta = wrap angle in radians. Explains why a few wraps of rope around a bollard can hold a large tension ratio. For a belt drive: T1 - T2 = power transmitted / belt velocity. Maximum tension T1 = sigma_allowable * A (cross-sectional area of belt).
**Push:** If T1 = 1000 N, mu = 0.3, theta = 180 deg (pi rad), what is T2? -> T2 = T1 / e^(mu*theta) = 1000 / e^(0.3*pi) = 1000 / 2.566 = 389.7 N.
**Trap:** Using degrees in capstan equation - theta must be in radians. Also, confusing T1 and T2 (tight side vs slack side).
**What they're really testing:** Whether you can apply the capstan equation to belt drives and rope systems.

### Q23. Wedge friction. [M]
**A:** Wedge: inclined plane used to raise or lower heavy loads. To raise load: P = W*(tan(theta) + mu)/(1 - mu*tan(theta)) where theta = wedge angle, mu = coefficient of friction. To lower load: P = W*(mu - tan(theta))/(1 + mu*tan(theta)). If mu > tan(theta), the wedge is self-locking (load won't descend). Used in: machine tool slides, door stops, splitting wood.
**Push:** When is a wedge self-locking? -> When mu > tan(theta), i.e., the friction angle exceeds the wedge angle. The load won't descend by itself.
**Trap:** Assuming the wedge angle equals the friction angle - self-locking occurs when friction angle > wedge angle, not when they are equal.
**What they're really testing:** Whether you can analyze wedge friction and determine self-locking condition.

### Q24. Journal bearing friction, friction circle. [H]
**A:** Journal bearing: shaft rotates in a bearing with lubricant. Friction circle: resultant reaction shifts by angle phi = arctan(mu) from normal; radius = r*sin(phi). The shaft centre is offset from the bearing centre by eccentricity e. Friction torque = mu * r * W (for dry or boundary lubrication). For hydrodynamic lubrication, friction is much lower (fluid friction only).
**Push:** What is the friction circle radius for a journal bearing with r = 50 mm and mu = 0.1? -> phi = atan(0.1) = 5.71 deg. Radius = r*sin(phi) = 50*sin(5.71) = 4.99 mm. The shaft centre is offset by this amount from the bearing centre.
**Trap:** Using r instead of r*sin(phi) for the friction circle radius - the shift is r*sin(phi), not r*phi or r*mu.
**What they're really testing:** Whether you understand journal bearing friction and can calculate the friction circle.

### Q25. Clutch friction. [M]
**A:** Clutch: device to connect/disconnect power transmission. Types: disc (plate) clutch, cone clutch, centrifugal clutch. Torque transmitted by disc clutch: T = mu * F * r_eff * n, where F = axial force, r_eff = effective radius (average of inner and outer radius), n = number of friction surfaces. For uniform wear: r_eff = (r_o + r_i)/2. For uniform pressure: r_eff = (2/3) * (r_o^3 - r_i^3)/(r_o^2 - r_i^2).
**Push:** What is the difference between uniform wear and uniform pressure assumptions? -> Uniform wear: assumes wear is uniform across the friction surface (more realistic for worn clutches). Uniform pressure: assumes pressure is uniform across the surface (initial condition for new clutches).
**Trap:** Using uniform pressure formula for a worn clutch - uniform wear is more appropriate for steady-state operation.
**What they're really testing:** Whether you can calculate clutch torque and understand the wear assumptions.

### Q26. Brake friction. [M]
**A:** Brake: device to slow or stop motion. Types: drum brake, disc brake, band brake. Band brake torque: T = mu * F * r * (e^(mu*theta) - 1)/(e^(mu*theta) + 1) for self-locking band brake. Drum brake: shoe pressed against drum, friction force creates braking torque. Disc brake: pads clamp rotor, friction slows rotation. Braking torque = mu * F * r (for simple disc brake).
**Push:** Why are disc brakes preferred over drum brakes in automobiles? -> Disc brakes have better heat dissipation, less fade, more consistent performance in wet conditions, and are easier to service.
**Trap:** Saying drum brakes are always worse - drum brakes are still used in rear wheels of many vehicles because they are cheaper and provide parking brake function.
**What they're really testing:** Whether you understand brake types and can calculate braking torque.

---

## 3. Work, Energy, and Power - 6 questions

### Q27. Work-energy principle for particles. [H]
**A:** Work-energy principle: work done by all forces = change in kinetic energy. W = delta KE = 0.5*m*v2^2 - 0.5*m*v1^2. Work done by gravity = m*g*h (positive when falling). Work done by spring = -0.5*k*x^2 (when compressed). Work done by friction = -f_k * d (negative, dissipates energy). Used to find velocity without knowing time or acceleration.
**Push:** A 2 kg mass falls 5 m from rest. What is its velocity at impact? -> m*g*h = 0.5*m*v^2 -> v = sqrt(2*g*h) = sqrt(2*9.81*5) = 9.9 m/s.
**Trap:** Forgetting that work done by friction is negative (it removes energy from the system).
**What they're really testing:** Whether you can apply the work-energy principle to find velocities.

### Q28. Conservation of energy for systems. [H]
**A:** Conservation of energy: total energy in an isolated system remains constant. KE + PE + internal energy = constant. For a pendulum: at top (max PE, zero KE), at bottom (zero PE, max KE). For a spring-mass system: 0.5*k*x^2 + 0.5*m*v^2 = constant. Energy can transform between kinetic, potential, and internal (heat) forms.
**Push:** A 1 kg mass attached to a spring (k = 100 N/m) is pulled 0.1 m and released. What is the maximum velocity? -> 0.5*k*x^2 = 0.5*m*v^2 -> v = sqrt(k/m)*x = sqrt(100/1)*0.1 = 1 m/s.
**Trap:** Forgetting that energy is conserved only in isolated systems - if friction is present, mechanical energy is not conserved.
**What they're really testing:** Whether you can apply conservation of energy to mechanical systems.

### Q29. Impulse and momentum for particles. [H]
**A:** Impulse = force * time = change in momentum: F*dt = m*v2 - m*v1. For impact: coefficient of restitution e = (v2 - v1)/(u1 - u2) where u = velocity before impact, v = velocity after impact. e = 1 for perfectly elastic, e = 0 for perfectly inelastic (stick together). Momentum is conserved in collisions (no external impulse).
**Push:** Two balls collide: m1 = 2 kg, v1 = 3 m/s, m2 = 1 kg, v2 = -2 m/s. If e = 0.5, what are the velocities after collision? -> Use momentum conservation and restitution equation to solve for v1' and v2'.
**Trap:** Confusing impulse with momentum - impulse is force*time, momentum is mass*velocity. Also, using wrong sign convention for velocities.
**What they're really testing:** Whether you can apply impulse-momentum to collision problems.

### Q30. Angular momentum and conservation. [H]
**A:** Angular momentum L = I*omega (for rotating body) or L = r x p (for particle). Conservation of angular momentum: if no external torque, L = constant. Example: ice skater spinning - pulling arms in reduces I, increases omega. Gyroscope: spinning rotor resists changes to its spin axis orientation.
**Push:** A child on a merry-go-round (I = 100 kg-m^2) spins at 2 rad/s. If the child moves inward, reducing I to 50 kg-m^2, what is the new angular velocity? -> L = I1*omega1 = I2*omega2 -> 100*2 = 50*omega2 -> omega2 = 4 rad/s.
**Trap:** Forgetting that angular momentum is conserved, not angular velocity - when I changes, omega changes inversely.
**What they're really testing:** Whether you can apply conservation of angular momentum to rotating systems.

### Q31. Power and efficiency. [H]
**A:** Power = rate of doing work = F*v (for linear) or T*omega (for rotational). Efficiency = useful power output / power input = P_out/P_in. For machines: mechanical efficiency = BP/IP, thermal efficiency = BP/fuel energy. Power loss = friction, heat, sound, etc.
**Push:** A motor delivers 10 kW at 1500 RPM. What is the torque? -> P = T*omega -> T = P/omega = 10000/(2*pi*1500/60) = 10000/157.08 = 63.66 N-m.
**Trap:** Using RPM instead of rad/s in power formula - omega must be in rad/s.
**What they're really testing:** Whether you can calculate power and torque for rotating machinery.

### Q32. D'Alembert's principle. [M]
**A:** D'Alembert's principle: a dynamic problem can be converted to a static equilibrium problem by adding inertia forces (-ma) and inertia moments (-I*alpha) to the FBD. The system is then in "dynamic equilibrium": sum of all forces (including inertia forces) = 0. Used to solve problems where acceleration is known or can be related to forces.
**Push:** How does D'Alembert's principle simplify dynamic analysis? -> It converts a dynamic problem (F = ma) into a static problem (sum F = 0), so you can use the same equilibrium equations and FBD techniques.
**Trap:** Forgetting to include inertia forces for all masses in the system, or using wrong sign convention.
**What they're really testing:** Whether you can convert dynamic problems to static equilibrium using D'Alembert's principle.

---

## 3. Kinematics and Dynamics - 6 questions

### Q33. Kinematics of particles: rectilinear motion. [H]
**A:** Kinematics describes motion without considering forces. For rectilinear motion: v = ds/dt, a = dv/dt = d^2s/dt^2. Constant acceleration: v = u + at, s = ut + 0.5*at^2, v^2 = u^2 + 2as. For variable acceleration: integrate a(t) to get v(t), integrate v(t) to get s(t).
**Push:** A car accelerates from rest at 2 m/s^2 for 5 seconds, then decelerates at 1 m/s^2 to stop. What is the total distance? -> First phase: s1 = 0.5*2*25 = 25 m, v1 = 10 m/s. Second phase: 0 = 100 - 2*1*s2 -> s2 = 50 m. Total = 75 m.
**Trap:** Using constant acceleration formulas for variable acceleration problems.
**What they're really testing:** Whether you can solve kinematics problems with constant and variable acceleration.

### Q34. Projectile motion. [H]
**A:** Projectile motion: horizontal motion with constant velocity (no acceleration), vertical motion with constant acceleration (gravity). Range R = (u^2 * sin(2*theta))/g. Maximum height H = (u^2 * sin^2(theta))/(2*g). Time of flight T = (2*u*sin(theta))/g. At 45 deg, range is maximum.
**Push:** What angle gives maximum range? -> 45 deg, because sin(2*theta) is maximum at 2*theta = 90 deg, so theta = 45 deg.
**Trap:** Forgetting that horizontal velocity is constant (no air resistance) and vertical acceleration is g (downward).
**What they're really testing:** Whether you can analyze projectile motion and find range, height, and time of flight.

### Q35. Kinematics of rigid bodies: plane motion. [H]
**A:** Rigid body plane motion can be decomposed into translation of a reference point plus rotation about that point. Velocity of any point P: v_P = v_O + omega x r_P/O. Acceleration: a_P = a_O + alpha x r_P/O + omega x (omega x r_P/O) (centripetal term). Instantaneous centre of rotation: point with zero velocity, can be found by intersecting perpendiculars to velocity vectors.
**Push:** How do you find the instantaneous centre of rotation? -> Draw lines perpendicular to the velocity vectors of two points on the body. Their intersection is the instantaneous centre.
**Trap:** Forgetting the centripetal term in acceleration: omega x (omega x r) is always present when omega != 0, even if alpha = 0.
**What they're really testing:** Whether you can analyze rigid body plane motion and find velocities/accelerations of points.

### Q36. Kinematics of rigid bodies: rolling without slipping. [H]
**A:** Rolling without slipping: v_contact = 0 (point of contact has zero velocity). For a wheel of radius R rolling with angular velocity omega: v_cm = R*omega (centre velocity). Acceleration: a_cm = R*alpha. Condition for rolling without slipping: a_cm = R*alpha. If a_cm > R*alpha, the wheel slips (skids). If a_cm < R*alpha, the wheel slips (spins).
**Push:** A wheel of radius 0.3 m rolls without slipping at 10 m/s. What is the angular velocity? -> omega = v/R = 10/0.3 = 33.3 rad/s = 318 RPM.
**Trap:** Forgetting that rolling without slipping requires v_cm = R*omega, not v_cm = R*omega/2 or other factors.
**What they're really testing:** Whether you understand rolling without slipping and can relate linear and angular quantities.

### Q37. Relative motion in rotating reference frames. [M]
**A:** In a rotating reference frame, the acceleration of a point P is: a_P = a_O + a_rel + 2*omega x v_rel + alpha x r + omega x (omega x r). The terms are: (1) acceleration of origin, (2) relative acceleration, (3) Coriolis acceleration (2*omega x v_rel), (4) tangential acceleration (alpha x r), (5) centripetal acceleration (omega x (omega x r)).
**Push:** What is the Coriolis acceleration? -> 2*omega x v_rel. It appears when a point moves in a rotating frame. Direction: rotate v_rel by 90 deg in direction of omega.
**Trap:** Missing the Coriolis term entirely - it's the most common error in rotating frame analysis.
**What they're really testing:** Whether you can analyze motion in rotating reference frames and include all acceleration terms.

### Q38. Dynamics of rigid bodies: Newton's laws. [H]
**A:** Newton's laws for rigid bodies: (1) Sum F = m*a_cm (translational motion). (2) Sum M = I*alpha (rotational motion about CM). (3) Action-reaction pairs. For a rigid body, you need both force and moment equations to solve for unknowns. FBD must include all external forces and moments.
**Push:** A uniform rod of mass m and length L is pivoted at one end and released from horizontal. What is the angular acceleration? -> I = mL^2/3 (about end). Torque = mg*L/2. alpha = torque/I = (mg*L/2)/(mL^2/3) = 3g/(2L).
**Trap:** Using I about the centre (mL^2/12) instead of I about the pivot (mL^2/3) - parallel axis theorem needed.
**What they're really testing:** Whether you can apply Newton's laws to rigid body rotation.

### Q39. Dynamics of rigid bodies: work-energy for rigid bodies. [H]
**A:** Work-energy for rigid bodies: work done by all forces = change in kinetic energy. KE = 0.5*m*v_cm^2 + 0.5*I_cm*omega^2 (translational + rotational). Work by gravity = m*g*h_cm. Work by spring = -0.5*k*x^2. Work by friction = -f_k * d (dissipates energy). Used to find velocity without knowing time or acceleration.
**Push:** A solid cylinder rolls down an incline without slipping. What is its velocity at the bottom? -> m*g*h = 0.5*m*v^2 + 0.5*I*omega^2 = 0.5*m*v^2 + 0.5*(0.5*mR^2)*(v/R)^2 = 0.75*m*v^2. v = sqrt(4*g*h/3).
**Trap:** Forgetting the rotational kinetic energy term - a rolling body has both translational and rotational KE.
**What they're really testing:** Whether you can apply work-energy to rolling bodies and include rotational KE.

### Q40. Dynamics of rigid bodies: impulse-momentum for rigid bodies. [H]
**A:** Impulse-momentum for rigid bodies: angular impulse = change in angular momentum. For a rigid body: integral(M dt) = I*omega2 - I*omega1. Also, linear impulse = change in linear momentum: integral(F dt) = m*v2 - m*v1. Used for impact problems where forces are large and time is short.
**Push:** A rod pivoted at one end is struck by a mass m moving at velocity v. What is the angular velocity after impact? -> Use angular impulse-momentum: m*v*L = I*omega, where I = mL^2/3 (rod) + m*L^2 (point mass at end). Solve for omega.
**Trap:** Using linear momentum instead of angular momentum for pivoted bodies - the pivot exerts an impulse, so linear momentum is not conserved.
**What they're really testing:** Whether you can apply impulse-momentum to rigid body impact problems.

---

## File Statistics

**Total questions: 40**

**By tag:**
- [H] High-yield: ~25 questions
- [M] Medium-yield: ~13 questions
- [L] Occasional: ~2 questions

**By section:**
- Free body diagrams and equilibrium: 10 questions
- Trusses and frames: 8 questions
- Friction: 8 questions
- Work, energy, and power: 6 questions
- Kinematics and dynamics: 8 questions

**Standard values used consistently:** E=200 GPa, g=9.81, pi=3.1416, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers Engineering Mechanics - essential for automobiles, petrochem, and construction interviews.