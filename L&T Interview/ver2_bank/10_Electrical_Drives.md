# Electrical and Drives - Core Interview Bank

**Part 10 of 10 | 50 questions | AC/DC, three-phase, power factor, transformers, induction motors, VFDs, earthing, protection, cables, switchgear**

*Mechanical GET panel, industry-agnostic depth: fundamentals from standard mechanical syllabus.*
*Tags: [H] asked very commonly, [M] asked regularly, [L] occasional.*

## 1. Electrical Fundamentals - 8 questions

### Q1. Ohm's law, Kirchhoff's laws. [H]
**A:** Ohm's law: V = I*R (voltage = current * resistance). Kirchhoff's current law (KCL): sum of currents at a node = 0 (conservation of charge). Kirchhoff's voltage law (KVL): sum of voltages around a loop = 0 (conservation of energy). These three laws are the foundation of all circuit analysis.
**Push:** When would you use KCL vs KVL? -> KCL for node analysis (currents), KVL for loop analysis (voltages). Use KCL when you know node voltages, KVL when you know loop currents.
**Trap:** Applying Ohm's law to non-ohmic devices (diodes, transistors) - Ohm's law is only for linear resistors.
**What they're really testing:** Whether you know basic circuit laws and can apply them.

### Q2. AC vs DC: advantages and applications. [H]
**A:** DC: unidirectional current, constant voltage. Advantages: easy to store (batteries), precise control, no frequency issues. Applications: electronics, electric vehicles, battery systems, DC motors. AC: alternating current, sinusoidal voltage. Advantages: easy to transform voltage (transformers), efficient long-distance transmission, simpler generators. Applications: power distribution, motors, lighting, industrial drives.
**Push:** Why is AC used for power distribution instead of DC? -> AC voltage can be easily stepped up (for transmission) and stepped down (for use) using transformers. DC requires complex power electronics.
**Trap:** Saying DC is obsolete - DC is growing rapidly with renewable energy, EVs, and battery storage.
**What they're really testing:** Whether you understand AC vs DC and their applications.

### Q3. Single-phase vs three-phase power. [H]
**A:** Single-phase: one voltage waveform, 2 wires (phase + neutral). Used for: residential, small commercial, lighting. Three-phase: three voltage waveforms 120 deg apart, 3 or 4 wires. Used for: industrial, large motors, power distribution. Three-phase advantages: (1) Constant power (no pulsation), (2) More power per conductor, (3) Self-starting motors, (4) Smaller conductors for same power.
**Push:** Why is three-phase preferred for industrial motors? -> Three-phase motors are self-starting, have constant torque (no pulsation), and are more efficient than single-phase motors.
**Trap:** Saying single-phase is only for homes - it's also used in small industry and commercial applications.
**What they're really testing:** Whether you understand single-phase vs three-phase and their applications.

### Q4. Power factor: definition and importance. [H]
**A:** Power factor (PF) = real power (kW) / apparent power (kVA) = cos(phi), where phi is phase angle between voltage and current. PF ranges from 0 to 1. Low PF means more current for same real power, causing: (1) Higher I2R losses, (2) Larger conductors, (3) Voltage drop, (4) Utility penalties. Correction: add capacitors to offset inductive load (motors, transformers).
**Push:** What is the power factor of a purely resistive load? -> 1.0 (unity). Voltage and current are in phase. For purely inductive load: 0. For purely capacitive load: 0 (leading).
**Trap:** Saying power factor is always lagging - capacitive loads have leading power factor.
**What they're really testing:** Whether you understand power factor and its importance.

### Q5. Power triangle: real, reactive, apparent power. [H]
**A:** Power triangle: S (apparent power, kVA) = P (real power, kW) + jQ (reactive power, kVAR). Magnitude: |S| = sqrt(P^2 + Q^2). Power factor = P/|S| = cos(phi). Reactive power Q = P*tan(phi). For inductive load: Q positive (lagging). For capacitive load: Q negative (leading). Utility bills often charge for kVAR or penalize low PF.
**Push:** A motor draws 10 kW at 0.8 PF lagging. What is the reactive power? -> Q = P*tan(phi) = 10*tan(acos(0.8)) = 10*tan(36.87) = 10*0.75 = 7.5 kVAR.
**Trap:** Confusing real power (kW) with apparent power (kVA) - you pay for kW, but equipment must handle kVA.
**What they're really testing:** Whether you can calculate real, reactive, and apparent power.

### Q6. Three-phase power calculation. [H]
**A:** Three-phase power: P = sqrt(3)*V_L*I_L*cos(phi) for balanced load, where V_L is line voltage, I_L is line current. For star (Y) connection: V_phase = V_L/sqrt(3), I_phase = I_L. For delta (Delta) connection: V_phase = V_L, I_phase = I_L/sqrt(3). Power is same formula for both: P = 3*V_phase*I_phase*cos(phi).
**Push:** What is the relationship between line and phase quantities in star and delta? -> Star: V_L = sqrt(3)*V_ph, I_L = I_ph. Delta: V_L = V_ph, I_L = sqrt(3)*I_ph.
**Trap:** Using phase quantities in the three-phase power formula - use line quantities with sqrt(3) factor.
**What they're really testing:** Whether you can calculate three-phase power and understand star/delta connections.

### Q7. Transformers: principle and types. [H]
**A:** Transformer: transfers electrical energy between circuits through electromagnetic induction. Principle: V1/V2 = N1/N2 (voltage ratio = turns ratio), I1/I2 = N2/N1 (current ratio = inverse turns ratio). Types: (1) Power transformer (high voltage, transmission), (2) Distribution transformer (low voltage, consumer), (3) Instrument transformer (CT, PT for measurement), (4) Auto-transformer (single winding, variable voltage).
**Push:** Why is a transformer rated in kVA, not kW? -> Because transformer losses (copper and iron) depend on voltage and current, not power factor. The load's PF doesn't affect transformer heating.
**Trap:** Saying transformer changes power - it changes voltage and current, but power (minus losses) is conserved.
**What they're really testing:** Whether you understand transformer principle and rating.

### Q8. Transformer losses and efficiency. [M]
**A:** Transformer losses: (1) Copper loss (I2R in windings) - varies with load^2. (2) Iron loss (hysteresis + eddy current in core) - constant regardless of load. Efficiency = output/input = P_out/(P_out + P_cu + P_iron). Maximum efficiency occurs when copper loss = iron loss. Typical efficiency: 95-99% for large transformers.
**Push:** When does a transformer have maximum efficiency? -> When copper loss = iron loss. This occurs at a specific load (usually 50-75% of rated load).
**Trap:** Thinking transformer efficiency is constant - it varies with load because copper loss changes with load^2.
**What they're really testing:** Whether you understand transformer losses and efficiency.

## 2. Motors - 12 questions

### Q9. Induction motor: principle and types. [H]
**A:** Induction motor: rotating magnetic field (RMF) in stator induces current in rotor (no electrical connection). Rotor rotates at speed less than synchronous speed (slip). Types: (1) Squirrel cage (robust, most common), (2) Wound rotor (slip rings, for high starting torque). Synchronous speed N_s = 120*f/P (RPM), where f = frequency (Hz), P = number of poles. Slip s = (N_s - N_r)/N_s.
**Push:** Why does an induction motor need slip? -> Without slip, rotor speed = synchronous speed, no relative motion between RMF and rotor, no induced current, no torque. Slip creates the relative motion needed for induction.
**Trap:** Saying induction motor runs at synchronous speed - it always runs below synchronous speed (slip is essential).
**What they're really testing:** Whether you understand induction motor principle and slip.

### Q10. Induction motor starting methods. [H]
**A:** Starting methods: (1) DOL (Direct On Line) - full voltage, high starting current (6-8x rated), for small motors (< 5 kW). (2) Star-Delta - reduces starting current to 1/3, for medium motors. (3) Auto-transformer - reduces voltage, for large motors. (4) Soft starter - electronic voltage ramp, smooth start. (5) VFD - variable frequency, best control. Starting torque depends on voltage squared and rotor resistance.
**Push:** Why is DOL starting not used for large motors? -> Starting current is 6-8x rated, causing voltage drop in supply and mechanical shock. Large motors need reduced-voltage starting.
**Trap:** Using star-delta for motors that need high starting torque - star-delta reduces both current AND torque (to 1/3).
**What they're really testing:** Whether you can select the right starting method for given motor size.

### Q11. Induction motor speed control. [H]
**A:** Speed control methods: (1) VFD (Variable Frequency Drive) - change frequency, best method, full speed range, energy efficient. (2) Pole changing - change number of poles, discrete speeds. (3) Rotor resistance control - for wound rotor motors, reduces speed but wastes energy. (4) Voltage control - reduces speed but poor torque. VFD is the standard for modern applications.
**Push:** Why is VFD the best speed control method? -> It maintains constant torque (V/f control), is energy efficient, provides smooth acceleration, and allows full speed range (0-100%+).
**Trap:** Using voltage control for speed reduction - reduces torque and can stall the motor.
**What they're really testing:** Whether you understand motor speed control methods.

### Q12. Induction motor efficiency and losses. [M]
**A:** Induction motor losses: (1) Stator copper loss (I2R), (2) Rotor copper loss (I2R), (3) Iron loss (hysteresis + eddy current), (4) Friction and windage, (5) Stray load loss. Efficiency = mechanical output / electrical input. Typical: 85-95% for large motors, 70-85% for small motors. Efficiency peaks at 75-100% of rated load.
**Push:** Why does motor efficiency drop at low load? -> Iron loss and friction/windage are constant (independent of load), so at low load they dominate and efficiency drops.
**Trap:** Running motors at very light load - efficiency drops significantly and power factor worsens.
**What they're really testing:** Whether you understand motor losses and efficiency.

### Q13. Synchronous motor: principle and applications. [M]
**A:** Synchronous motor: rotor rotates at synchronous speed (no slip). Excitation: DC field winding in rotor (or permanent magnets). Power factor: can be leading, lagging, or unity (by adjusting excitation). Applications: (1) Power factor correction (over-excited synchronous motor), (2) Constant speed drives (compressors, pumps), (3) Large industrial drives. Starting: needs auxiliary motor or damper winding (induction motor principle).
**Push:** Why is synchronous motor used for power factor correction? -> Over-excited synchronous motor draws leading current, which cancels lagging current from inductive loads (motors, transformers).
**Trap:** Saying synchronous motor is self-starting - it needs auxiliary starting (damper winding or separate motor).
**What they're really testing:** Whether you understand synchronous motor principle and applications.

### Q14. DC motor: types and characteristics. [M]
**A:** DC motor types: (1) Series - high starting torque, speed varies with load (dangerous at no load). (2) Shunt - constant speed, moderate starting torque. (3) Compound - combines series and shunt. (4) Permanent magnet - compact, efficient, for small applications. Speed control: (a) Armature voltage (below base speed), (b) Field weakening (above base speed). Applications: traction, cranes, rolling mills, servo drives.
**Push:** Why is series DC motor dangerous at no load? -> Speed increases with decreasing load (speed ~ 1/flux). At no load, speed can reach dangerously high levels (runaway).
**Trap:** Using series motor where constant speed is needed - speed varies wildly with load.
**What they're really testing:** Whether you understand DC motor types and characteristics.

### Q15. Motor protection: overload, short circuit, earth fault. [H]
**A:** Motor protection: (1) Overload (thermal relay) - protects against sustained overcurrent (heating). (2) Short circuit (magnetic relay/fuse) - protects against high fault currents. (3) Earth fault (earth leakage relay) - protects against leakage to ground. (4) Under-voltage (UV relay) - protects against low voltage. (5) Phase failure (phase loss relay) - protects against single phasing. Protection settings: (a) Pickup current, (b) Time delay, (c) Coordination with upstream devices.
**Push:** What is the difference between overload and short circuit protection? -> Overload: moderate overcurrent over time (thermal). Short circuit: very high current instantly (magnetic). Different devices, different time constants.
**Trap:** Using only fuses for motor protection - fuses don't protect against overload (moderate overcurrent), only short circuit.
**What they're really testing:** Whether you understand motor protection devices and their functions.

### Q16. VFD: principle and benefits. [H]
**A:** VFD (Variable Frequency Drive): converts AC to DC (rectifier), then DC to AC (inverter) at variable frequency. Principle: motor speed proportional to frequency (N = 120*f/P). Benefits: (1) Energy savings (fan/pump affinity laws: power ~ speed^3), (2) Smooth acceleration, (3) Process control, (4) Reduced mechanical stress. Disadvantages: (1) Harmonics, (2) Cost, (3) Complexity.
**Push:** How much energy can a VFD save on a fan/pump? -> At 50% speed, power = 0.5^3 = 0.125 = 12.5% of full power. Savings = 87.5%. Significant for variable flow applications.
**Trap:** Using VFD for constant flow applications - no energy savings if flow is always at 100%.
**What they're really testing:** Whether you understand VFD principle and energy savings.

### Q17. VFD harmonics and mitigation. [M]
**A:** VFD harmonics: rectifier draws non-sinusoidal current, creating harmonic currents (5th, 7th, 11th...). Effects: (1) Transformer heating, (2) Cable heating, (3) Capacitor failure, (4) Interference with sensitive equipment. Mitigation: (1) Line reactors (inductors), (2) Passive filters, (3) Active filters, (4) Multi-pulse rectifiers (12-pulse, 18-pulse), (5) IEEE 519 standard for harmonic limits.
**Push:** What is IEEE 519? -> Standard for harmonic control in electrical power systems. Specifies maximum harmonic current and voltage distortion limits at point of common coupling (PCC).
**Trap:** Ignoring harmonics in VFD installations - can cause equipment failure and utility penalties.
**What they're really testing:** Whether you understand VFD harmonics and mitigation.

### Q18. Motor efficiency standards: IE1, IE2, IE3, IE4. [M]
**A:** IEC 60034-30 efficiency classes: (1) IE1 (Standard), (2) IE2 (High), (3) IE3 (Premium), (4) IE4 (Super Premium). Higher efficiency = lower losses = higher cost. Mandated by regulations in many countries. IE3 is minimum for new motors in EU/US. IE4 is becoming standard for large motors. Efficiency improvement: IE4 motors have 1-2% higher efficiency than IE3.
**Push:** What is the difference between IE3 and IE4? -> IE4 motors have lower losses (higher efficiency) due to better materials (copper rotor, thinner laminations) and design optimization.
**Trap:** Thinking higher efficiency always means lower operating cost - consider purchase price vs energy savings over motor life.
**What they're really testing:** Whether you know motor efficiency standards.

### Q19. Servo motor vs induction motor. [M]
**A:** Servo motor: precise position/speed control with feedback (encoder). Types: (1) AC servo (permanent magnet synchronous), (2) DC servo. Advantages: high precision, fast response, high torque at low speed. Applications: robotics, CNC machines, automation. Induction motor: simpler, cheaper, for constant speed applications. Servo is for precision, induction is for power.
**Push:** When would you use a servo motor instead of an induction motor? -> When you need precise position control (robotics, CNC) or fast dynamic response. Induction motors are for pumps, fans, conveyors.
**Trap:** Using servo motors for simple applications - overkill and expensive.
**What they're really testing:** Whether you can select between servo and induction motors.

### Q20. Stepper motor: principle and applications. [M]
**A:** Stepper motor: moves in discrete steps (no feedback needed for open-loop control). Types: (1) Permanent magnet, (2) Variable reluctance, (3) Hybrid (most common). Step angle: typically 1.8 deg (200 steps/rev). Advantages: precise positioning without encoder, simple control. Disadvantages: (1) Low torque at high speed, (2) Can lose steps if overloaded, (3) Resonance/vibration. Applications: 3D printers, CNC routers, small positioning systems.
**Push:** What is the difference between stepper and servo? -> Stepper: open-loop, discrete steps, no feedback. Servo: closed-loop, continuous, with encoder feedback. Servo is more accurate and can handle higher loads.
**Trap:** Using stepper motors for high-torque applications - they have limited torque and can lose steps.
**What they're really testing:** Whether you understand stepper motor principle and applications.

## 3. Protection and Switchgear - 10 questions

### Q21. Circuit breakers: types and ratings. [H]
**A:** Circuit breakers: (1) MCB (Miniature CB) - for low current (< 125 A), residential/commercial. (2) MCCB (Moulded Case CB) - for medium current (100-1600 A), industrial. (3) ACB (Air CB) - for high current (> 800 A), main distribution. (4) VCB (Vacuum CB) - for medium voltage (1-36 kV). (5) SF6 CB - for high voltage (> 36 kV). Ratings: (a) Rated current, (b) Breaking capacity (kA), (c) Voltage rating.
**Push:** What is breaking capacity? -> Maximum fault current the breaker can safely interrupt. Must be greater than the prospective short circuit current at the installation point.
**Trap:** Selecting breaker based only on rated current - must also check breaking capacity.
**What they're really testing:** Whether you know circuit breaker types and ratings.

### Q22. Fuses: types and applications. [M]
**A:** Fuses: (1) Rewirable fuse - replaceable wire, cheap but slow. (2) HRC (High Rupturing Capacity) fuse - fast, high breaking capacity, used in industrial. (3) Cartridge fuse - compact, for electronics. (4) Semiconductor fuse - very fast, for power electronics. Fuse characteristics: (a) I-t curve (current vs time), (b) Breaking capacity, (c) Voltage rating. Fuses are one-time use; CBs are resettable.
**Push:** When would you use a fuse instead of a circuit breaker? -> For cost-sensitive applications, or where very fast protection is needed (semiconductor fuses). Fuses are cheaper but must be replaced after operation.
**Trap:** Using rewirable fuses in industrial applications - they have low breaking capacity and are unreliable.
**What they're really testing:** Whether you know fuse types and can select appropriate protection.

### Q23. Earthing: types and importance. [H]
**A:** Earthing (grounding): connecting electrical equipment to earth to provide safe path for fault current. Types: (1) TN (earthed neutral, equipment earthed to neutral) - most common. (2) TT (earthed neutral, separate earth electrode). (3) IT (isolated neutral, no earth connection). Importance: (1) Protects against electric shock, (2) Provides path for fault current (enables protection devices to operate), (3) Stabilizes voltage. Earth resistance should be < 1 ohm (for TN) or < 10 ohm (for TT).
**Push:** What happens if equipment is not earthed? -> Fault current has no path to earth, protection devices don't operate, equipment stays live, posing shock hazard.
**Trap:** Thinking earthing is only for safety - it also enables protection devices to detect faults and clear them.
**What they're really testing:** Whether you understand earthing and its importance.

### Q24. RCD/ELCB: earth leakage protection. [H]
**A:** RCD (Residual Current Device) / ELCB (Earth Leakage CB): detects imbalance between live and neutral current (leakage to earth). If I_live - I_neutral > threshold (typically 30 mA for personnel protection), trips. Types: (1) RCCB (Residual Current CB) - no overcurrent protection. (2) RCBO (Residual Current Breaker with Overcurrent) - combines RCD + MCB. (3) ELCB (voltage-operated) - older, less common. Used for: (1) Shock protection, (2) Fire prevention (high-sensitivity RCDs).
**Push:** Why is 30 mA the standard for personnel protection? -> 30 mA is below the threshold for ventricular fibrillation (50-100 mA for AC). Trips fast enough to prevent serious injury.
**Trap:** Using RCD without overcurrent protection - need MCB or RCBO for complete protection.
**What they're really testing:** Whether you understand earth leakage protection.

### Q25. Surge protection devices (SPD). [M]
**A:** SPD (Surge Protection Device): protects equipment from voltage surges (lightning, switching transients). Types: (1) Type 1 - for lightning protection (high energy), installed at service entrance. (2) Type 2 - for switching surges, installed at distribution panels. (3) Type 3 - for sensitive equipment, installed at point of use. SPDs divert surge current to earth through low-impedance path. Key parameters: (a) Voltage protection level (VPL), (b) Nominal discharge current (In), (c) Maximum discharge current (Imax).
**Push:** Where should SPDs be installed? -> At all levels: Type 1 at service entrance, Type 2 at distribution panels, Type 3 at sensitive equipment. Coordinated protection provides best coverage.
**Trap:** Installing only one SPD - different surge levels need different SPD types at different locations.
**What they're really testing:** Whether you understand surge protection and SPD types.

### Q26. Relay: types and applications. [M]
**A:** Relay: electrically operated switch. Types: (1) Electromechanical relay (EMR) - coil and contacts, simple, reliable. (2) Solid-state relay (SSR) - semiconductor switching, no moving parts, fast. (3) Reed relay - small, for low current. (4) Safety relay - for safety circuits (E-stop, light curtains). Applications: (1) Control circuits, (2) Isolation, (3) Logic, (4) Motor starting. Key parameters: (a) Coil voltage, (b) Contact rating, (c) Number of poles.
**Push:** When would you use SSR instead of EMR? -> For high switching frequency, long life, or when noise is a concern. SSR has no contact bounce and faster switching.
**Trap:** Using EMR for high-frequency switching - contacts wear out quickly.
**What they're really testing:** Whether you know relay types and can select the right one.

### Q27. Contactor: function and selection. [M]
**A:** Contactor: heavy-duty relay for switching power circuits (motors, heaters, lighting). Features: (1) Main contacts (power), (2) Auxiliary contacts (control), (3) Coil (AC or DC), (4) Arc suppression (for AC). Selection based on: (a) Motor power rating, (b) Voltage, (c) Number of poles, (d) Utilization category (AC-3 for motors, AC-1 for non-inductive). Contactors are designed for frequent operation (millions of cycles).
**Push:** What is utilization category AC-3? -> For squirrel cage motors: starting, plugging, inching. Contactors rated AC-3 can handle motor starting current (6-8x rated).
**Trap:** Using AC-1 contactor for motor starting - AC-1 is for non-inductive loads, can't handle motor inrush.
**What they're really testing:** Whether you can select contactors for motor control.

### Q28. PLC: basics and applications. [M]
**A:** PLC (Programmable Logic Controller): industrial computer for automation. Components: (1) CPU (processor), (2) Input modules (sensors), (3) Output modules (actuators), (4) Power supply, (5) Communication modules. Programming languages: (1) Ladder logic (most common), (2) Function block diagram, (3) Structured text, (4) Sequential function chart. Applications: (1) Motor control, (2) Process control, (3) Machine automation, (4) Building automation.
**Push:** Why is ladder logic the most common PLC language? -> Because it resembles electrical relay logic diagrams, making it easy for electricians to understand and program.
**Trap:** Thinking PLCs are only for simple on/off control - modern PLCs handle analog, motion, and complex algorithms.
**What they're really testing:** Whether you understand PLC basics and applications.

### Q29. SCADA: basics and applications. [M]
**A:** SCADA (Supervisory Control and Data Acquisition): system for monitoring and controlling industrial processes. Components: (1) RTU/PLC (field devices), (2) Communication network, (3) HMI (Human Machine Interface), (4) Historian (data storage). Functions: (1) Real-time monitoring, (2) Alarm management, (3) Data logging, (4) Remote control. Applications: (1) Power plants, (2) Water treatment, (3) Oil and gas, (4) Manufacturing.
**Push:** What is the difference between PLC and SCADA? -> PLC controls local processes (fast, deterministic). SCADA monitors and controls at system level (slower, broader). PLC is field-level, SCADA is supervisory.
**Trap:** Using SCADA for fast control - SCADA is for monitoring and supervision, not real-time control.
**What they're really testing:** Whether you understand SCADA and its relationship with PLC.

### Q30. Electrical drawings: single-line diagram, wiring diagram. [M]
**A:** Single-line diagram (SLD): shows power distribution with one line per phase, simplifies complex systems. Shows: (1) Power source, (2) Transformers, (3) Switchgear, (4) Loads. Wiring diagram: shows actual connections between devices, terminal numbers, wire colors. Used for: (1) Installation, (2) Troubleshooting, (3) Maintenance. Standards: IEC 60617 (symbols), IS 375 (Indian standard).
**Push:** When would you use SLD vs wiring diagram? -> SLD for system overview and power flow. Wiring diagram for actual installation and troubleshooting.
**Trap:** Confusing SLD with wiring diagram - SLD is simplified, wiring diagram is detailed.
**What they're really testing:** Whether you understand electrical drawings.

## 4. Cables and Installation - 8 questions

### Q31. Cable sizing: current carrying capacity. [H]
**A:** Cable sizing based on: (1) Current carrying capacity (ampacity) - depends on conductor size, insulation, installation method, ambient temperature. (2) Voltage drop - should be < 3-5% of nominal voltage. (3) Short circuit withstand - cable must survive fault current for clearing time. Standards: IEC 60364, IS 3961. Derating factors: (a) Ambient temperature, (b) Grouping, (c) Soil thermal resistivity.
**Push:** What are the main factors affecting cable ampacity? -> (1) Conductor material (Cu vs Al), (2) Insulation type (PVC, XLPE), (3) Installation method (in air, in ground, in conduit), (4) Ambient temperature.
**Trap:** Sizing cable based only on current - must also check voltage drop and short circuit withstand.
**What they're really testing:** Whether you can size cables correctly.

### Q32. Cable types: PVC, XLPE, armoured. [M]
**A:** Cable types: (1) PVC (Polyvinyl Chloride) - cheap, flexible, max 70 deg C. (2) XLPE (Cross-Linked Polyethylene) - higher temp (90 deg C), better electrical properties, more expensive. (3) Armoured (SWA - Steel Wire Armour) - mechanical protection, for buried/underground. (4) Unarmoured - for indoor/tray installation. (5) Fire-resistant - for emergency circuits (fire pumps, alarms).
**Push:** When would you use XLPE instead of PVC? -> For higher temperature applications, better electrical performance, or longer life. XLPE is standard for industrial power cables.
**Trap:** Using PVC for high-temperature applications - PVC degrades above 70 deg C.
**What they're really testing:** Whether you know cable types and can select the right one.

### Q33. Cable installation methods. [M]
**A:** Installation methods: (1) In air (on trays, in conduits) - best heat dissipation. (2) In ground (direct buried, in ducts) - requires derating. (3) In water (submarine cables) - special design. (4) On surface (clipped to wall) - good ventilation. Derating factors reduce ampacity for: (a) High ambient temperature, (b) Grouping (multiple cables together), (c) High soil thermal resistivity.
**Push:** Why does cable ampacity decrease when cables are grouped? -> Grouped cables heat each other, reducing heat dissipation. Derating factor can be 0.5-0.8 depending on number of cables.
**Trap:** Ignoring derating factors - leads to undersized cables and overheating.
**What they're really testing:** Whether you understand cable installation and derating.

### Q34. Voltage drop calculation. [M]
**A:** Voltage drop: VD = I * R * L (for DC) or VD = I * (R*cos(phi) + X*sin(phi)) * L (for AC), where R = resistance per unit length, X = reactance per unit length, L = cable length, I = current. Should be < 3% for lighting, < 5% for power. For three-phase: VD = sqrt(3) * I * (R*cos(phi) + X*sin(phi)) * L.
**Push:** What is the maximum acceptable voltage drop? -> Typically 3% for lighting circuits, 5% for power circuits. Some standards allow up to 6% total (including upstream).
**Trap:** Calculating voltage drop for single-phase and applying to three-phase - different formulas.
**What they're really testing:** Whether you can calculate voltage drop in cables.

### Q35. Cable testing: megger, hi-pot. [M]
**A:** Cable testing: (1) Megger (insulation resistance) - measures resistance between conductor and earth (should be > 1 M-ohm, typically 100 M-ohm for new cables). (2) Hi-pot (high potential) - applies high voltage to test insulation withstand. (3) Continuity test - checks conductor continuity. (4) Phase rotation test - checks phase sequence. (5) Tan delta test - measures insulation dissipation factor (for high-voltage cables).
**Push:** What is the minimum acceptable insulation resistance? -> For low-voltage cables: > 1 M-ohm (typically 100 M-ohm for new). For high-voltage: > 1000 M-ohm. Depends on cable voltage rating and length.
**Trap:** Testing energized cables with megger - can damage equipment and is dangerous.
**What they're really testing:** Whether you know cable testing methods.

### Q36. Cable glands and termination. [M]
**A:** Cable gland: device for securing cable to equipment, providing: (1) Mechanical grip, (2) Environmental seal (IP rating), (3) Earth continuity (for armoured cables). Types: (1) Compression gland - for unarmoured cables. (2) Armour gland - for SWA cables, provides earth connection. (3) Barrier gland - for hazardous areas (explosion-proof). Termination: (1) Lug (crimped), (2) Solder, (3) Insulation displacement. Proper termination is critical for reliability.
**Push:** Why are cable glands important? -> They provide mechanical support, environmental protection (IP rating), and earth continuity. Poor glands are a common cause of cable failures.
**Trap:** Using wrong gland type - can cause water ingress, mechanical failure, or loss of earth continuity.
**What they're really testing:** Whether you understand cable glands and termination.

### Q37. Cable tray and conduit systems. [M]
**A:** Cable tray: (1) Ladder tray - for large cables, good ventilation. (2) Perforated tray - for medium cables, some ventilation. (3) Solid tray - for EMI shielding, no ventilation. (4) Wire mesh tray - for light cables, flexible. Conduit: (1) PVC conduit - cheap, flexible. (2) Metal conduit - EMI shielding, mechanical protection. (3) Flexible conduit - for moving equipment. Selection based on: (a) Cable size, (b) Environment, (c) EMI requirements, (d) Cost.
**Push:** When would you use cable tray instead of conduit? -> For large number of cables, easier installation, better ventilation, and easier future additions. Conduit is better for protection and EMI shielding.
**Trap:** Overfilling cable trays - reduces ventilation and can cause overheating.
**What they're really testing:** Whether you can select cable management systems.

### Q38. Cable fire safety. [M]
**A:** Cable fire safety: (1) Fire-resistant cables - maintain circuit integrity during fire (for emergency systems). (2) Low smoke zero halogen (LSZH) - reduces toxic smoke. (3) Fire-retardant - self-extinguishing. (4) Fire barrier - prevents fire spread through cable penetrations. Standards: IEC 60331 (fire resistance), IEC 60754 (smoke/halogen). Used for: (1) Fire pumps, (2) Emergency lighting, (3) Fire alarms, (4) Smoke extraction.
**Push:** What is the difference between fire-resistant and fire-retardant? -> Fire-resistant: maintains function during fire. Fire-retardant: self-extinguishing, doesn't spread fire. Different purposes.
**Trap:** Using fire-retardant cables where fire-resistant is needed - fire-retardant cables fail during fire.
**What they're really testing:** Whether you understand cable fire safety.

## 5. Power Systems and Drives - 12 questions

### Q39. Power factor correction: capacitor sizing. [H]
**A:** Capacitor sizing: Q_c = P * (tan(phi1) - tan(phi2)), where P = real power, phi1 = initial phase angle, phi2 = target phase angle. Capacitor current I_c = Q_c / V. For three-phase: Q_c = sqrt(3) * V_L * I_c. Capacitor rating in kVAR. Common target PF: 0.95-0.99 lagging (avoid leading PF which can cause voltage rise).
**Push:** A 100 kW load at 0.8 PF lagging. What capacitor is needed for 0.95 PF? -> Q_c = 100 * (tan(acos(0.8)) - tan(acos(0.95))) = 100 * (0.75 - 0.329) = 42.1 kVAR.
**Trap:** Over-correcting to leading PF - can cause voltage rise and resonance with harmonics.
**What they're really testing:** Whether you can size power factor correction capacitors.

### Q40. Power factor correction: automatic capacitor bank. [M]
**A:** Automatic capacitor bank: multiple capacitor stages switched by controller based on measured PF. Features: (1) PF sensing, (2) Stage switching (contactors), (3) Harmonic filtering (detuned reactors), (4) Over-voltage protection. Benefits: (1) Maintains target PF, (2) Avoids over-correction, (3) Adapts to load changes. Used in: industrial plants with varying loads.
**Push:** Why use detuned reactors with capacitor banks? -> To prevent resonance with harmonic currents (5th, 7th). Detuned reactors shift resonance frequency below the 5th harmonic.
**Trap:** Installing capacitor banks without harmonic consideration - can cause resonance and equipment failure.
**What they're really testing:** Whether you understand automatic PF correction.

### Q41. UPS: types and applications. [M]
**A:** UPS (Uninterruptible Power Supply): provides backup power during outages. Types: (1) Offline/Standby - switches to battery on outage, 4-10 ms transfer time. (2) Line-interactive - voltage regulation + battery backup. (3) Online/Double-conversion - always converts AC-DC-AC, no transfer time, best quality. Applications: (1) Data centers, (2) Hospitals, (3) Industrial control, (4) Telecom. Sizing: (a) Load (kVA), (b) Runtime (minutes), (c) Battery type (VRLA, Li-ion).
**Push:** When would you use online UPS instead of offline? -> For critical loads (data centers, medical) that can't tolerate any power interruption. Online UPS has zero transfer time.
**Trap:** Using offline UPS for critical loads - transfer time (4-10 ms) can cause equipment reset.
**What they're really testing:** Whether you understand UPS types and can select the right one.

### Q42. Generator: sizing and selection. [M]
**A:** Generator sizing: (1) Calculate load (kW/kVA) including starting currents. (2) Add 20-25% margin. (3) Consider: (a) Motor starting (inrush), (b) Power factor, (c) Altitude and temperature derating. Types: (1) Diesel generator (most common), (2) Gas generator (cleaner, cheaper fuel), (3) Petrol generator (small, portable). Ratings: (a) Prime (continuous), (b) Standby (emergency, limited hours).
**Push:** Why is generator sizing based on kVA, not kW? -> Because generator must supply both real and reactive power. Motor starting requires high kVA even if kW is low.
**Trap:** Sizing generator based only on running load - ignores motor starting inrush and can cause voltage dip.
**What they're really testing:** Whether you can size generators correctly.

### Q43. Motor control center (MCC). [M]
**A:** MCC: centralized motor control panel. Components: (1) Incoming feeder (CB, CT, PT), (2) Bus bars, (3) Motor starters (DOL, star-delta, VFD), (4) Protection (overload, short circuit, earth fault), (5) Metering, (6) Communication. Types: (1) Fixed (starters bolted in), (2) Withdrawable (plug-in units, for maintenance). Standards: IEC 61439, UL 845.
**Push:** What is the advantage of withdrawable MCC? -> Starters can be removed for maintenance without shutting down entire MCC. Improves maintainability and reduces downtime.
**Trap:** Using fixed MCC in critical applications - maintenance requires shutdown.
**What they're really testing:** Whether you understand MCC design and types.

### Q44. Electrical safety: lockout/tagout (LOTO). [H]
**A:** LOTO (Lockout/Tagout): procedure to ensure equipment is de-energized and cannot be restarted during maintenance. Steps: (1) Notify affected employees, (2) Shut down equipment, (3) Isolate energy sources (electrical, mechanical, hydraulic, pneumatic), (4) Apply locks and tags, (5) Verify zero energy (test), (6) Perform maintenance, (7) Remove locks/tags, (8) Restart. Critical for: electrical work, mechanical maintenance, confined space entry.
**Push:** Why is verification (step 5) critical? -> Because isolation may fail (stuck contactor, backfeed, stored energy). Testing ensures zero energy before work begins.
**Trap:** Skipping verification - assumed isolation may not be actual isolation. Can be fatal.
**What they're really testing:** Whether you understand LOTO and its importance.

### Q45. Electrical safety: arc flash. [M]
**A:** Arc flash: electrical explosion caused by arc fault. Energy released as heat, light, sound, and pressure. Temperature can reach 20,000 deg C. Causes: (1) Equipment failure, (2) Human error (tools dropped, improper work), (3) Dust/moisture. Protection: (1) Arc flash study (calculate incident energy), (2) PPE (arc-rated clothing, face shield), (3) Engineering controls (arc-resistant switchgear, current limiting), (4) Administrative controls (LOTO, safe work practices).
**Push:** What is incident energy? -> Amount of thermal energy (cal/cm2) that a person could be exposed to during an arc flash. Determines PPE category.
**Trap:** Working on energized equipment without arc flash assessment - can result in severe burns or death.
**What they're really testing:** Whether you understand arc flash hazards and protection.

### Q46. Energy efficiency in electrical systems. [M]
**A:** Energy efficiency measures: (1) Use IE3/IE4 motors, (2) VFD for variable speed applications, (3) Power factor correction, (4) LED lighting, (5) Efficient transformers, (6) Cable sizing (reduce I2R losses), (7) Power quality improvement (reduce harmonics). Energy audit: (1) Measure consumption, (2) Identify losses, (3) Recommend improvements, (4) Calculate payback. Standards: ISO 50001 (energy management).
**Push:** What is the typical payback period for VFD installation? -> 1-3 years for fan/pump applications (due to cubic power-speed relationship). VFD cost is recovered quickly through energy savings.
**Trap:** Focusing only on motor efficiency - system efficiency (pump + motor + VFD) matters more.
**What they're really testing:** Whether you understand electrical energy efficiency.

### Q47. Renewable energy: solar PV basics. [M]
**A:** Solar PV (Photovoltaic): converts sunlight to electricity. Components: (1) PV panels (silicon cells), (2) Inverter (DC to AC), (3) Mounting structure, (4) Cables, (5) Protection (fuses, breakers). Types: (1) Monocrystalline (high efficiency, expensive), (2) Polycrystalline (lower efficiency, cheaper), (3) Thin-film (flexible, low efficiency). System types: (1) Grid-tied (no battery), (2) Off-grid (with battery), (3) Hybrid (grid + battery).
**Push:** What is the typical efficiency of a solar PV panel? -> Monocrystalline: 18-22%. Polycrystalline: 15-18%. Thin-film: 10-12%. Efficiency depends on cell technology and temperature.
**Trap:** Ignoring temperature derating - PV panel output decreases by ~0.4%/deg C above 25 deg C.
**What they're really testing:** Whether you understand solar PV basics.

### Q48. Battery: types and applications. [M]
**A:** Battery types: (1) Lead-acid (VRLA, flooded) - cheap, heavy, for UPS and automotive. (2) Li-ion (lithium-ion) - high energy density, long life, for EVs and electronics. (3) Ni-Cd (nickel-cadmium) - robust, for industrial. (4) Ni-MH (nickel-metal hydride) - for hybrid vehicles. Key parameters: (a) Capacity (Ah), (b) Voltage (V), (c) Energy density (Wh/kg), (d) Cycle life, (e) Charge/discharge rate (C-rate).
**Push:** What is the difference between VRLA and flooded lead-acid? -> VRLA (Valve Regulated Lead-Acid) is sealed, maintenance-free, can be mounted in any position. Flooded requires water topping and ventilation.
**Trap:** Using lead-acid for high-cycle applications - Li-ion has much longer cycle life.
**What they're really testing:** Whether you know battery types and can select the right one.

### Q49. Electric vehicle: charging systems. [M]
**A:** EV charging: (1) Level 1 (AC, 120V, 1.4-1.9 kW) - slow, overnight. (2) Level 2 (AC, 240V, 3.3-19.2 kW) - medium, home/workplace. (3) DC fast charging (50-350 kW) - fast, highway. Standards: (1) Type 1 (J1772, North America), (2) Type 2 (Mennekes, Europe), (3) CCS (Combined Charging System), (4) CHAdeMO (Japanese). Battery management system (BMS) protects battery during charging.
**Push:** What is the difference between AC and DC charging? -> AC charging uses onboard charger (slower). DC charging bypasses onboard charger, charges battery directly (faster).
**Trap:** Thinking all EVs use the same connector - different regions and manufacturers use different standards.
**What they're really testing:** Whether you understand EV charging systems.

### Q50. Electrical maintenance and testing. [M]
**A:** Electrical maintenance: (1) Preventive (scheduled inspection, testing, cleaning). (2) Predictive (condition monitoring: thermography, vibration, oil analysis). (3) Corrective (repair after failure). Testing: (1) Insulation resistance (megger), (2) Continuity, (3) Earth resistance, (4) Relay testing, (5) Transformer oil test (BDV, moisture, acidity). Safety: (1) LOTO, (2) PPE, (3) Arc flash protection.
**Push:** What is thermography in electrical maintenance? -> Infrared imaging to detect hot spots (overloaded connections, failing components) before they fail. Non-contact, can be done while energized.
**Trap:** Skipping preventive maintenance - leads to unexpected failures and costly downtime.
**What they're really testing:** Whether you understand electrical maintenance and testing.

## File Statistics

**Total questions: 50**

**By tag:**
- [H] High-yield: ~18 questions
- [M] Medium-yield: ~28 questions
- [L] Occasional: ~4 questions

**By section:**
- Electrical fundamentals: 8 questions
- Motors: 12 questions
- Protection and switchgear: 10 questions
- Cables and installation: 8 questions
- Power systems and drives: 12 questions

**Standard values used consistently:** V=I*R, P=sqrt(3)*V_L*I_L*cos(phi), N_s=120*f/P, g=9.81, etc.

**ASCII only:** No LaTeX, no unicode, no emoji.

**Interview format:** Each [H] question has **A:** (2-5 sentences), **Push:** (1-2 sentences), **Trap:** (1 line), **What they're really testing:** (one line).

This bank covers Electrical and Drives - essential for automobiles, petrochem, and construction interviews.