# Internship answers - BHEL Hyderabad, TC & GT division
**L&T GET (core, mechanical) | 2027 pass-out | 21 Oct 2026**

This document is meant to be read, not memorised. Every answer here starts by teaching you the
substance, so that by the time you answer, you know the content and are only choosing words for
something you already understand. The single most important idea is this: the question "tell me
about your internship" is not really asking "what did you do". You had no design task, so there is
no deliverable to describe. What the panel is testing is whether you can see how a thing is
actually made, and whether you can talk about it clearly. So your answer is: what did you see, what
did you understand, and how did that change the way you think about engineering.

---

## 1. Get the frame right (read this once, then stop re-reading it)

### The honest frame, in two sentences

Say this once, near the start, in your own words, and then stop talking about the visit's
organisation:

> "It was a guided plant training visit at BHEL Hyderabad, in the Turbines, Compressors and Gas
> Turbine division. I was given no design ownership - it was a technical run-down with the
> division, and I kept four pages of handwritten notes from the shop floor."

Two sentences. No apology, no hedging, no "but I did a lot". You state it as a fact and then move
straight into the substance.

### The three sentences that will sink you, and why

1. **"I worked on the steam turbine rotor at BHEL."**
   This is a lie by implication and the panel can smell it. There was no rotor project, no drawing
   you touched, no file you opened. If you say this and they ask "which stage did you work on?",
   you are finished.

2. **"The document was my project" / "I prepared a report on the TC and GT division."**
   The handout was BHEL's own company and product material with the turbine and compressor theory
   in it. It was given to the batch as a run-down to read before the visit. Calling it yours is the
   easiest way to get caught, because a panelist who has been to a plant will know exactly what a
   plant training handout looks like.

3. **"It was a great learning experience."**
   This is the red-flag sentence. It has no content in it, and interviewers name it out loud as the
   answer that shows the candidate has not processed anything. If you say it, everything you said
   before it gets discounted.

Note what is *not* on this list: saying that the visit was short, or that the role was small.
Honesty about scope is safe. Vagueness is not.

### The pivot: from "I was there" to "I understood how it is actually made"

The difference between a weak answer and a strong answer is not how much you say about the visit.
It is whether your answer ends up on content. A candidate who says "I saw machines" has said
nothing. A candidate who says "I saw a nineteen-operation route for machining a rotor, with a
balance gate after the blades were fitted, and that is what made me understand that a drawing is
only a third of the job" has given the panel something to work with.

So the shape of every answer is: the frame (once), then the content, then what it changed in how
you think. The content comes from three observations, and they are the strongest thing you have:

- A rotor is machined, not designed.
- The drawing is only a third of the job - the process route and the inspection gate are the rest.
- Scale and tooling logic: a twelve-metre job in one setup, and why solid, tipped and indexable
  tools are chosen differently.

### When they push: "but did you do any work?"

They will ask this. Answer it straight, in one sentence, without defensiveness, and move on:

> "Not design work, no. It was a guided visit. What I did do was treat it like a study - I wrote
> down every machine specification, the tooling choices and the rotor machining sequence, and I
> asked the shop floor why things were done the way they were."

Then you are back on content. Do not apologise. Do not add a second explanation of why you had no
deliverable. One sentence, then move.

---

## 2. Before you answer anything - understand these six things

If you can explain these six to a non-mechanical friend, you can answer any follow-up under
pressure. Read them once, understand them, then you never need to look at this section again.

### 2.1 What a steam turbine actually is, and how the steam path works

**In plain language.** A steam turbine is a heat engine that turns the energy in hot steam into
rotation. Steam comes in at high pressure and high temperature. It is pushed through a series of
fixed nozzles that squeeze it and make it fast, and then it hits blades that are mounted on a
spinning shaft. The blades catch that fast steam and push the shaft around. That is all it is. The
trick is that the steam does not just hit the blades once and leave - it expands as it goes, so it
keeps pushing all the way down the length of the machine, and you get a lot of work out of it.

Think of a hose nozzle pointed at a paddle wheel, except the "water" is steam that keeps expanding
as it travels, so the pushing never stops until the steam is nearly at atmospheric pressure at the
exhaust end.

**The engineering terms.** Steam enters at the **HP (high pressure)** end and expands through
successive **stages**. Each stage has two rows: a fixed row of **stator blades (nozzles)** and a
rotating row of **rotor blades**. The nozzle row accelerates the steam, the rotor row extracts
work from it. Rows alternate so the steam keeps entering the next set of nozzles at the right
angle. The machine has an HP section, often an **intermediate (IP)** section, and an **LP (low
pressure)** section. The steam leaves at the LP end and goes to the condenser, where it gives up
its remaining heat as a liquid. Since the turbine must keep turning at the same speed no matter how
much load the grid puts on it, it has a **governing** system - centrifugal flyweight,
hydro-mechanical, hydro-dynamic, electro-hydraulic, electronic - whose job is to change how much
steam is admitted.

**Why it matters for you.** A turbine is really two big halves: a rotating half (the rotor) and a
static half (the casing), plus the accessories that make them safe - bearings, glands, valves. The
rotor and the casing are exactly the two things you saw being made at BHEL, so when you describe
the machine you are describing something you actually stood in front of.

### 2.2 The rotor - why it is the hard part

**In plain language.** The rotor is the whole spinning assembly: a huge alloy-steel shaft, with
discs or wheels on it, and blades fitted into those wheels. For a large turbine it is metres long
and weighs many tonnes, and it spins at thousands of rpm. Every single kilogram of it has to be
balanced, because a rotor that is even slightly out of balance creates a force that grows with the
square of speed. Doubling the speed quadruples the force. So a rotor that is fine at low speed can
destroy itself at full speed.

The other reason it is hard: the blade roots are not glued on. They are cut into the rim of each
wheel as **fir-tree grooves**, and the blade is dropped into the groove and locked mechanically.
Then a metal **shroud** is welded around the blade tips to form a near-continuous ring. The shroud
stops steam from leaking around the tip, and it also damps the blades aerodynamically so they do
not flutter. So the rotor goes from a single forged lump, to a machined wheel, to a wheel with
dozens of blades in it, to a blade assembly that must then be balanced - and every one of those
steps changes the mass distribution.

**The engineering terms.** Rotor = shaft forging + discs/wheels + blades + shrouding + balancing.
Dynamic balancing, residual imbalance, **specific allowance** (the imbalance permitted per unit
mass), and stage-wise balancing - balancing after each major assembly stage rather than only at
the end, because it is much easier to correct a small imbalance before the machine is half
built. Also thermal growth: a rotor heats up and expands, axially and radially, so its supports
must be able to move with it, which is a big part of why the bearings are what they are.

**Why it matters for you.** This is the answer to "what was the most technical thing you saw", and
it is the reason you can talk for two minutes without filler. A rotor is not designed and then
made - it is **machined**, in a fixed sequence, and the sequence is the design.

### 2.3 The casing, the joint, and the taper pins

**In plain language.** The casing is the big static shell around the rotor. It has to hold the
steam pressure, and it has to come apart so the rotor can be put in or taken out. So it is split -
either horizontally or vertically - and the two halves are the ones that have to meet perfectly.
They are located by **taper pins**: small tapered dowels, like a slightly conical pin, that sit in
matching holes in the two halves. Push the taper in and the two halves are pulled together and
located accurately, with friction holding them there.

A horizontal split has a **metal-to-metal fit** - the two joint faces touch each other directly,
no soft gasket in between. And here is the part that surprised you: the faces are **colour-matched
by scraping**. The faces are put together, and the shop scrapes one against the other until the
contact pattern comes up even all the way round - you literally check it by putting a marking
compound on the joint and looking at where it marks. If the contact is patchy, the joint is not
acceptable, because a patchy joint is a leak path and, worse, a place where the two halves can
vibrate against each other. After the joint is accepted, the casing goes to hydrostatic pressure
test, then grit blasting, then painting.

**The engineering terms.** Split casing (horizontal split / vertical split), taper pin location,
metal-to-metal joint, contact pattern / blueing, **hydrostatic pressure test**, grit blasting and
painting as the surface prep and corrosion protection stages.

**Why it matters for you.** It shows that the shop has acceptance criteria that are physical and
visible - a contact pattern you can look at, a pressure test you can watch - not just numbers on
a drawing. That is exactly the culture L&T's manufacturing and site businesses run on, and it is a
clean, concrete example of why the drawing is only a third of the job.

### 2.4 Bearings - journal and thrust (Kingsbury), and why a rotor must not touch the casing

**In plain language.** A rotor weighing tonnes, spinning fast, held up only at its ends - the
bearings are the part that stops the whole machine from falling down. There are two jobs and they
are different jobs.

The **journal bearing** handles the weight. It is **spherically seated**, which means the bearing
shell sits in a spherical recess, so if the shaft deflects even slightly under load, the bearing
tilts a little by itself and stays lined up. It is lined with **Babbitt** - an alloy of tin, copper
and antimony that is deliberately soft. The point of a soft lining is that it takes the damage
instead of the journal: if anything gets in there, the Babbitt beds in and wears, rather than
scoring the expensive precision journal surface.

The **thrust bearing** handles the push along the shaft. Steam flowing through the blades pushes
the rotor forward, so something has to take that axial load, and it has to be a different bearing
from the one taking the weight. The one you saw is a **Kingsbury bearing** - a pivoted shoe that
sits on a pivot block and tilts to follow the rotating collar. "Double acting" means it can take
the thrust in either direction. In this machine it is on a front pedestal and it takes the
**residual axial thrust**, the part that is left over after the main thrust is taken at the other
end.

And the rule underneath all of it: **the rotor must never touch the casing**. The running clearance
between rotor and casing is deliberately large - thousands of times larger than a bearing
clearance - because a rotor rubbing on a casing at speed means metal-to-metal contact at enormous
relative speed. That is fire. The bearings are the only thing the rotor is allowed to touch.

**The engineering terms.** Journal bearing, spherically seated / spherical seat, **Babbitt**
lining (tin-copper-antimony), Kingsbury / pivoted shoe thrust bearing, double-acting, residual
axial thrust, rotor-to-casing clearance, oil film.

**Why it matters for you.** It explains the whole layout of a turbine machine in one shot: the
rotor hangs in bearings, the casing floats around it, and everything else - glands, valves,
turning gear - exists to keep the two halves from each other and to keep the rotor safe when
something goes wrong.

### 2.5 Labyrinth glands, the emergency stop valve, and the turning gear

Three accessories. All three are on the casing, and all three exist because a turbine is a
pressure vessel full of steam that keeps spinning after the electricity is gone.

**Labyrinth glands.** Wherever a shaft passes out through the casing, steam will leak along the
shaft. At the ends of the machine that leaking steam would get into the bearing housings and
worsen it. A **labyrinth gland** is a ring of interlocking teeth with a small controlled gap, and
it does not seal by touching the shaft - it seals by making the leak go through a narrow, tortuous
path so the pressure drops across it. The neat part, which you noted: the leakage steam is not
thrown away. It still has energy in it, so it is **returned to the low-pressure circuit** instead
of being dumped.

**Emergency stop valve.** This sits on the casing. Its job is the emergency case: when the load is
thrown off suddenly, the steam already inside the turbine is still sitting on the blades and still
pushing them. If you just close the inlet, that trapped steam keeps accelerating the rotor, and the
machine **over-speeds**. So the emergency stop valve vents the trapped steam so the rotor coasts
down instead of running away.

**Turning gear.** A worm-driven motor mounted on the casing that turns the rotor slowly when the
machine is not running. Why? Because a rotor that is hot and sitting still under its own weight
**bows** - it sags, and the sag is one-sided. If you keep turning it slowly, the bow rotates around
with the rotor instead of staying in one bad place, and the machine cools evenly all round. It also
means the rotor is ready to be restarted without a long soak.

**The engineering terms.** Labyrinth gland (nozzle type / clearance type), gland steam return to
the LP circuit, emergency stop valve / stop valve and case venting, over-speed, **thermal bow**,
turning gear (worm geared), casing creep / differential expansion.

**Why it matters for you.** It is the easiest technical answer to make sound confident without
over-claiming, because it is pure explanation and pure observation. If the panel wants to check
that you were actually paying attention, this is the kind of detail that proves it.

### 2.6 Process plan and inspection gates - the idea that a drawing is only a third of the job

**In plain language.** A drawing tells you what the finished part must look like and how accurate
it must be. It does not tell you how to make it. For that there are two other things.

The first is the **process plan** - the route card, the ordered list of operations, each one with
the machine, the tool, the cutting parameters and the inspection. Machining is sequential and
order matters enormously. You cannot drill the flange holes before you face the flange and turn
the bore. You cannot balance a rotor before the blades are on it. Get the order wrong and the
part is scrap, or it is scrap later.

The second is the **inspection gate**. At each operation, the part is measured against the drawing
and it either passes or it does not. If it does not pass, it does not move forward. On the machines
you saw, the gauges were right there on the table - **vernier, micrometer, pin gauge, bore gauge and
slip gauge** - because the inspection happens at the machine, not weeks later in a room. And every
part carries its **heat number**, so the material can be traced, with **0.01 mm** level
traceability on the machining.

**The engineering terms.** Process plan, route card, operation sequence, manufacturing
feasibility, inspection gate / hold point, first article inspection, heat number and material
traceability, tolerance stack-up, GDT. And the division's own definition of process planning,
which is the single best line you can quote:

> "Scrutiny of engineering drawings for manufacturing feasibility and developing the sequence of
> operations in an economical way."

Note the two halves of that definition: feasibility (can we make it at all, and how) and
economy (in the cheapest sensible sequence). Both halves matter. A route that is possible but
costs lakhs more than another route is not the route.

**Why it matters for you.** This is your headline idea and it is the honest bridge to L&T. It also
answers the "what surprised you" question without you having to pretend you built anything. And
when the panel asks a process-planning question - which they will, because the division's own
definition is right there - you can quote a real shop definition instead of a textbook one.

---

## 3. The questions they will actually ask, with answers

---

### Q1. Tell me about your internship.

**The idea:** This is the opening question and it is the one you set the frame on. Say what it was,
say you had no design ownership, and then move to content in the same breath. A panelist is
listening for one thing here: whether you were a visitor who watched, or someone who understands.
Prove the second one with specifics - the division, the four pages of notes, and one observation
that shows you were paying attention.

**How to say it:** It was a plant training visit to BHEL Hyderabad, in the Turbines, Compressors
and Gas Turbine division. I went with a batch, and the division gave us a technical run-down on
what they build. There was no design task and no deliverable, so the honest version is that I
watched, asked and wrote things down. I kept four pages of handwritten notes from the shop floor:
CNC machine specifications, the tooling choices, and the nineteen-operation rotor machining
sequence. What I took from it was a much clearer picture of what heavy manufacturing actually
involves, and that is the part I can talk about in detail.

**If they push:** "So what was the point of it, then?" - Answer honestly: it was the closest thing
to heavy manufacturing I could get to see, it gave me the vocabulary of the shop floor, and it
showed me what my degree does not cover, which is how things actually get made.

**Do not say:** "It was a great learning experience." Also do not describe the handout as your
project.

---

### Q2. What exactly did you do there?

**The idea:** Be concrete about what your days actually consisted of, so the answer sounds like
something real rather than a formality. Walk, watch, note, ask. Name the machines by what they
were doing, not by a list of numbers. The point is to show that you converted a tour into study.

**How to say it:** There was no assigned task, so I made the visit a study visit. I wrote down the
machine specifications as I walked - a CNC floor-type vertical machining centre for milling,
drilling and threading mild-steel castings, a CNC horizontal lathe for turning, boring, grooving
and lapping, and the heavy-duty CNC lathe that is the biggest machine in that plant. I noted the
tooling logic, why the shop runs solid, tipped and indexable tools in roughly an eight to four to
one ratio. And I wrote down the full nineteen-operation route for machining a rotor. I was asking
questions the whole time, mostly about why a job is set up in a particular order.

**If they push:** "Did you get to operate anything?" - No, it was a visit and I was not cleared to
work on the machines. Say it plainly, then ask what they would have let you do if they had asked
you to. That turns a weakness into a question you want to ask.

**Do not say:** "I was involved in machining" or anything that implies you were cleared to work on
the shop floor.

---

### Q3. What was your contribution?

**The idea:** This is the trap question, and honesty is the winning move. Say plainly that your
contribution was notes and questions, and then make the notes themselves the substance. What you
can claim is that you did the studying properly - you wrote things down, you asked why, and you can
now explain the machine. That is a real contribution and it does not need dressing up.

**How to say it:** My contribution was notes and questions, not design work, and I would rather say
that straight than dress it up. I wrote up four pages of handwritten notes: machine specifications,
the tooling choices, the nineteen-operation rotor sequence, the casing joint and taper pin
location, the bearing arrangement. But the part I am actually proud of is that I did not just
accept the tour. Every time I saw something, I asked the shop floor why it was done that way and
wrote the answer down. That is what turned a walk-through into something I can now explain to you
in detail.

**If they push:** "So you basically just watched?" - Yes, I watched with intent. The difference
between watching and watching is whether you can explain it afterwards, and I can explain the rotor
route, the inspection gates and the tooling logic.

**Do not say:** Any form of "I was responsible for", "I was part of the team that", or "my task
was". Also do not apologise here - stating the scope plainly is confidence, not weakness.

---

### Q4. What did you learn from it? / What surprised you?

**The idea:** Lead with the surprise, because surprise is memorable and it proves you processed
what you saw. The strongest surprise you have is that the rotor is not designed, it is machined -
and the corollary that a drawing is only a third of the job. Keep it to one big idea and one
supporting observation, then say what it changed about how you think.

**How to say it:** The thing that surprised me most was that a turbine rotor is not designed, it is
machined. The real work is taking one big alloy-steel forging through nineteen fixed operations -
facing, centre drilling, proving the program, turning the journals and thrust collars, cutting the
fir-tree grooves the blades lock into, fitting the blades, welding on the shroud, and then
balancing. And the drawing is only a third of the job: the other two thirds are the process route
and the inspection gate at each step. The smaller surprise that stuck with me was the casing joint.
It is not sealed with a gasket, it is scraped against itself until the contact pattern comes up
even.

**If they push:** "What does that change about how you work?" - I now think of engineering as a
chain from process plan to inspection gate, not as a drawing on a screen, and I am much more
interested in the manufacturing end than I was before the visit.

**Do not say:** "I learned about teamwork" or "I learned about professional behaviour." Generic
soft skills are not learning. Name a machine, a number, or a step.

---

### Q5. Why did you intern at BHEL when you want to join L&T?

**The idea:** The logic is simple and it is honest: BHEL Hyderabad is the closest thing in India
to what L&T's power and heavy-engineering businesses do. Big forgings, big machine tools, heavy
machining, real quality gates, a safety culture, and a plant where a small process decision costs
lakhs. Say it that way and there is nothing to defend.

**How to say it:** I did not pick BHEL because it was a famous name, I picked it because it was the
most relevant thing I could get to see. L&T is an EPC and engineering conglomerate - heavy
engineering, construction, power, manufacturing technology, project sites. BHEL's Hyderabad TC and
GT division does almost exactly that work: big forgings, big machine tools, heavy machining, formal
quality gates, a safety culture on the floor. So the visit was a preview of the environment I am
asking to work in, and honestly it is the main reason I am aiming at heavy manufacturing rather
than design-only work. I want to be on the floor where the part gets made, not only in the room
where it gets drawn.

**If they push:** "Do you see L&T as similar to BHEL?" - Similar in the work, different in the
model. BHEL is a public sector manufacturer focused on its own product lines; L&T is an EPC
conglomerate, so the same manufacturing discipline shows up on customer projects, on site, with
schedule and cost pressure attached. That is exactly the part I want to learn.

**Do not say:** Do not say BHEL is the same as L&T, and do not say the visit made you want L&T
specifically. Say it made you want heavy manufacturing, and L&T is where you want to do it.

---

### Q6. What is the most technical thing you saw?

**The idea:** This is the question to win the interview on, and you have a genuinely good answer:
the nineteen-operation rotor route. The panel's job is to find the candidate who can hold a
detailed technical story. Give them the sequence, then give them the reason the sequence is what
it is - you cannot balance a rotor before the blades are on it, and you cannot cut the blade grooves
before the wheel is turned. Finish with why the balancing machine exists.

**How to say it:** The most technical thing I saw was the rotor machining route - nineteen
operations in a fixed sequence. You start by inspecting the forging and its test certificates,
then dimensional inspection, face milling and centre drilling, program proving, and turning the
journals, thrust collars, flange partitions and T-blade grooves on the centre lathe. Then the
fir-tree grooves that the blades lock into, the coupling-flange holes on the horizontal boring
machine, the balancing holes, the caulking and machining of the sealing fins, then HP, LP and
fir-tree blade assembly with shrouding, then balancing on the balancing machine. The sequence is
the design, because you cannot cut grooves before you turn the wheel, or balance a rotor before
the blades are on it.

**If they push:** "Why does the rotor need balancing twice, or stage-wise?" - Because every
operation that adds or removes mass changes the distribution. Correcting a small imbalance early,
while the wheel is still accessible, is far cheaper than correcting it at the end. And the reason
the biggest machine in the plant is dedicated to first-job balancing is that imbalance force goes
as the square of speed - a small imbalance that is harmless at low speed becomes a large force at
full speed.

**Do not say:** Do not say the route was your work, or that you "followed" the route as a job
responsibility. You observed and wrote down the sequence.

---

### Q7. How would you describe the shop floor / what was it like?

**The idea:** This is a chance to show you can read a place, not just recall a machine. Talk about
scale, noise, discipline, the discipline of traceability, and the fact that everything is
sequenced and gated. One concrete detail beats three adjectives. And it is a chance to show you
already understand what L&T's shop floors and site yards are like.

**How to say it:** It was heavy, noisy and very organised. The machines were enormous - the biggest
one I saw was a heavy-duty CNC lathe with a 170 kilowatt main drive and twelve metres between
centres, and it takes work up to a hundred tonnes. But what struck me more than the size was the
discipline. Parts carry a heat number so you can trace them. Every operation has an inspection
before the part moves on, with the gauges kept at the machine. Nothing moves forward until it is
accepted. It looked less like a workshop and more like a production line where the rule is that
the next operation is only ever started on a part that has been proved.

**If they push:** "What would you find difficult about it?" - Honestly, the discipline of the gates.
I am used to being able to move on when something is roughly right, and there is no roughly here.
And the scale of the responsibility - a part that passes the gate goes into something that will
run for decades.

**Do not say:** Do not make it a generic "it was disciplined and safety-focused" answer with no
detail in it. The gauges at the machine and the heat numbers are what make it real.

---

### Q8. How does what you saw connect to what L&T does?

**The idea:** Draw the line explicitly and honestly. The same manufacturing logic - process plan,
inspection gate, traceability, heavy machining, safety - is what runs in L&T's heavy engineering
and manufacturing businesses, and on EPC project sites it shows up as shop drawings, method
statements, inspection and test plans, and quality hold points before a client accepts a system.
He has seen the shop version of it, and it is the same discipline at a different scale.

**How to say it:** In two ways. First, the same manufacturing logic - process planning, inspection
gates, traceability of material, the discipline of only moving on an accepted part - is exactly
what runs in L&T's heavy engineering and manufacturing business. Second, on the project side it
shows up as the same logic in a different form: shop drawings, method statements, inspection and
test plans, and hold points where a client will not accept a system until it is proved. What I saw
was the shop-floor version of that discipline. And that is why I want the manufacturing and site
exposure in a GET role rather than only design work - I want to be part of the chain that actually
proves the thing.

**If they push:** "What would you actually want to do at L&T?" - Machine and production engineering
on heavy components, and eventually process and quality work on the project side, where the
process plan and the inspection gate meet the site.

**Do not say:** Do not claim you have worked on L&T projects or that you know L&T's internal
systems. Speak about the logic you have seen and the logic L&T works to.

---

### Q9. What would you have liked to have been allowed to do?

**The idea:** This is a good question to be enthusiastic about, because the honest answer is
"exactly the thing I was not allowed to do". Wanting to run a part yourself, to see a program
proved on a machine, to sit with a process engineer and read a route card - it shows drive without
claiming anything. Keep it concrete.

**How to say it:** I would have liked to run one part end to end myself. Even something simple on
the machining centre - face it, drill it, measure it, and see whether my numbers matched the
drawing. What I actually got was the theory side of it: the route, the tooling, the acceptance
criteria. Seeing the operation would have made the route card make sense. The other thing I would
have wanted is to sit with a process engineer and read a real route card for a rotor, and watch how
the sequence and the inspection gates are actually written and revised. That is the job I think I
would enjoy.

**If they push:** "What would you do first if you got into the shop?" - Get the drawing, get the
route card, and ask what the operation before mine has to hand over for my operation to be
possible. Then make sure my own inspection gate is defined before I start, not after.

**Do not say:** Do not imply you were waiting for a chance to be given real work, or that the visit
wasted your time. Keep it forward-looking.

---

### Q10. If you could go back tomorrow, what would you ask?

**The idea:** Finish on the strongest note you have: that you would go deeper on the things you
already noticed. Specific questions sound like a person who is still thinking about the work the
night after. Then let the panel see that you are already asking the questions of the job.

**How to say it:** I would ask the shop floor three things. First, on the rotor route - how often
does the sequence actually get revised, and what triggers a change, because that tells you where
the real difficulty lives. Second, on the casing joint - how they set the taper pins and what
tolerance they hold on the contact pattern, because that is the part I could not fully picture from
a drawing. Third, on the balancing machine - what the acceptable residual imbalance is for a rotor
of that class and how they decide it. Those are the three things I left with questions about, and
each of them is a question about how the decision gets made, not about how the part looks.

**If they push:** "Ask one of those questions now." - Then ask it. The balance question is the
easiest to ask out loud and the hardest to bluff.

**Do not say:** Do not ask something that suggests you want to skip the visit, like "how fast can I
join". Keep it technical.

---

## 4. The three observations, in detail

These are the ammunition for "what surprised you" and "what was the most technical thing you saw".
Each one has a shape: what you saw, why it is interesting, what it teaches you about how things
get made, and one number you can quote.

### 4.1 A rotor is machined, not designed

**What you saw.** A turbine rotor does not exist as a finished part on a drawing. It exists as a
forging - one large piece of alloy steel - and it is converted into a rotor by a fixed sequence of
nineteen machining and assembly operations. The sequence you wrote down runs: inspect the forging
and its test certificates, dimensional inspection, face milling and centre drilling, program
proving, turning the journals, thrust collars, flange partitions and T-blade grooves on the
centre lathe, inspection, fir-tree grooves, drilling the coupling-flange holes on the CNC
horizontal boring machine, balancing holes and lockway milling, caulking the sealing fins,
machining the sealing fins, HP blade assembly, lock blade drilling, lock blade tapping, gland fin
assembly, shroud machining, LP blade assembly, fir-tree blade assembly, and finally rotor
balancing on the balancing machine.

**Why it is interesting.** Every step in that list is forced by the step before it. You cannot cut
fir-tree grooves before you have turned the wheel that will hold them. You cannot fit blades before
the grooves exist, and you cannot drill and tap the lock blades until the blade roots are in place.
You cannot balance the rotor until the blades and shrouding are on, because all of that mass
changes where the centre of gravity is. So the route is not a convenience - it is the actual
engineering content of making a rotor.

**What it teaches you about how things get made.** Design and manufacture are not two separate
worlds with a handover in between. For a component like this, the design and the manufacturing
sequence are the same thought, developed together. The person who chooses how to machine it is
making an engineering decision as real as choosing the blade profile.

**The number to quote: nineteen operations.** If you only say one thing: "a steam turbine rotor
goes through nineteen operations in a fixed sequence before it is balanced." And if they push on
why that matters: imbalance force goes as the square of speed, which is why the largest machine in
that plant - a 170 kilowatt heavy-duty CNC lathe with twelve metres between centres - is
dedicated to first-job rotor balancing.

### 4.2 The drawing is only a third of the job

**What you saw.** The division's own definition of process planning: *"scrutiny of engineering
drawings for manufacturing feasibility and developing the sequence of operations in an economical
way."* Then the practical version of it on the floor. The gauges - vernier, micrometer, pin gauge,
bore gauge, slip gauge - kept at the machine. Every part carrying its heat number, with 0.01 mm
traceability. The casing split horizontally or vertically, located by taper pins, with a
metal-to-metal joint that has to be **colour-matched by scraping** until the contact pattern is
even, and then hydrostatic pressure tested, grit blasted and painted.

**Why it is interesting.** The scraping detail is the one that stays with you, because it is
proof that acceptance on a shop floor can be physical. Somebody scrapes two faces against each
other, marks them, and looks at the pattern. If it is patchy, the joint is rejected. No drawing
dimension in the world can tell you that - only the physical contact can. It is also proof that
the two halves of a casing are not just bolted together; they are located, held, and proved to be
in contact.

**What it teaches you about how things get made.** A drawing is a statement of the intent. The
process plan is the translation of that intent into a sequence of things that can actually be
done, on machines that exist, in an economical order. The inspection gate is the proof that the
translation was executed correctly. Three layers, and the first one alone is what most students
think engineering is.

**The number to quote: 0.01 mm traceability with a heat number on every part.** Say it like this:
"every part on that floor carried a heat number and was traced at 0.01 mm, and the inspection
happened at the machine - vernier, micrometer, pin gauge, bore gauge, slip gauge - not in a
separate room." If they ask why that matters, the answer is that material traceability is what
lets you answer "what was this part made of, and who approved it" years later, and it is the
same logic behind an L&T quality record on a project.

### 4.3 Scale, and the tooling logic

**What you saw.** The heavy-duty CNC lathe, the biggest machine in that plant: centre height
2100 mm, swing over bed 3600 mm, and 4200 mm once the telescopic covers are removed, distance
between centres 12000 mm, main drive 170 kW, work up to 100 tonnes with steady rests. It runs a
twelve-metre-long job in one setup. A 4.2 m diameter job only fits without the telescopic cover.

And the tooling: **solid** tools (HSS, coated carbide), **tipped** tools (two-material, carbide
brazed onto a steel shank), and **indexable inserts** (CNMG and DNMG). The shop's split was
roughly **8 : 4 : 1**. Alloying with chromium, vanadium and molybdenum. Machine beds in cast iron
(air or self-lubricating) against aluminium (ferrocone).

**Why it is interesting.** The twelve-metre job in one setup is the line that makes a fresh
graduate sit up. You do not re-chuck a job like that - if you re-chuck it, you lose concentricity
and straightness across the whole length, and a rotor is unforgiving about straightness. So the
machine is built around the job, not the other way round. The 4.2 m diameter part only fitting
without the telescopic cover is the same idea in the other direction: the machine's envelope was
designed around the work.

The tooling split is the same kind of thinking. Solid and tipped tools get used where you want
the job done with the tool you already have and the geometry suits the operation. Indexable
inserts get used where you want speed and consistency - you swap the insert, not the whole tool,
and the grade is selected for the material and the cut. The alloying note (chromium, vanadium,
molybdenum) is what lets a tool hold its edge against a hard alloy-steel forging at those speeds.

**What it teaches you about how things get made.** Tool choice is not a preference, it is a
decision with a cost attached to it, made by someone who understands the material, the operation
and the machine. The 8 : 4 : 1 split is a shop's accumulated answer to "what do we actually use",
and it is the reason process planning is a job of its own.

**The numbers to quote: 12 m in one setup, and 170 kW.** "The heaviest machine there was a heavy
duty CNC lathe - twelve metres between centres, 170 kilowatt main drive, and it runs a
twelve-metre-long job in a single setup so you never have to re-chuck and lose concentricity."

---

## 5. Numbers he can quote (and what they mean)

Only these. If it is not on this table, do not say it in the interview. The three marked
**MEMORISE** are the ones worth being able to say without looking.

| Number | What it is | The one sentence that makes it meaningful |
|---|---|---|
| **19 operations** (MEMORISE) | The number of operations in the steam turbine rotor machining route | "A rotor is not designed, it is machined - nineteen fixed operations, and the sequence itself is the engineering." |
| **8 : 4 : 1** | The shop's rough split of solid tools : tipped tools : indexable inserts | "Eight solid, four tipped, one indexable - because an insert you can swap is worth it where you want speed and consistency, and not where you do not." |
| **170 kW, 12000 mm between centres** (MEMORISE) | Main drive and distance between centres of the heavy-duty CNC lathe, the biggest machine in that plant | "A 170 kilowatt lathe with twelve metres between centres, dedicated to first-job rotor balancing, because imbalance force goes as the square of speed." |
| **4200 mm swing / 4.2 m diameter** | Swing over bed with the telescopic covers removed | "A 4.2 metre diameter job only fits on that machine without the telescopic cover - the machine was built around the work." |
| 2100 mm centre height | Centre height of the heavy-duty CNC lathe | "Half the size of the swing - that tells you instantly how big the machine is." |
| 100 tonnes | The work the heavy lathe takes, with steady rests | "It takes work up to a hundred tonnes, supported by steady rests." |
| 0.01 mm | Traceability level on the shop floor, with heat number | "Every part carried a heat number and was traced at 0.01 mm, and the gauges sat at the machine." |
| TK6920, 1000 x 500 mm, 200 mm spindle | The CNC floor-type vertical machining centre, its travel and spindle | "A machining centre with a metre of travel on one axis, doing face and side milling, drilling, end milling and threading on mild-steel castings." |
| 350 - 500 rpm | Spindle speed on that machining centre | "Modest spindle speeds, which tells you the constraint was rigidity and reach, not raw speed." |
| 600 mm centre height, 800 mm centre distance, 100 mm spindle bore, 540 mm quill stroke, 60-90 deg internal taper | The CNC horizontal lathe | "A horizontal lathe for turning, boring, grooving, threading and lapping, with an internal taper of 60 to 90 degrees." |
| 250 MW | The upper end of the gas turbines the Hyderabad TC and GT division builds | "That division builds gas turbines up to about 250 megawatts - so the scale of the components is not academic." |
| 1962 | The year BHEL was founded, from the merger of electrical and mechanical works | "BHEL came out of the merger of the electrical and mechanical works in 1962 - heavy engineering, power plant equipment, turbines, generators, boilers, transformers." |

---

## 6. The 30-second version, and the 90-second version

The panel may give you thirty seconds or give you room. Have both ready.

**30 seconds.** Use this when they cut you off early, or as the answer to a quick follow-up.

> "It was a plant training visit at BHEL Hyderabad, in the Turbines, Compressors and Gas Turbine
> division - a guided visit with a technical run-down, no design work for me. I kept four pages of
> handwritten notes. The biggest thing I took from it: a turbine rotor is not designed, it is
> machined, through nineteen fixed operations, and it has to be balanced stage-wise because
> imbalance force goes as the square of speed. And the drawing is only a third of the job - the
> process route and the inspection gate at each step are the other two thirds. That is why I want
> heavy manufacturing rather than design-only work."

**90 seconds.** This is the one you should want to give when they say "tell me about your
internship" and then sit back. Same content as the short version, but with the machine in it.

> "My internship was a plant training attachment at BHEL Hyderabad, in the Turbines, Compressors
> and Gas Turbine division. To be straight about it, I was not given any design ownership - it was
> a guided visit with the division's technical run-down, and I spent the time taking notes on
> everything I saw. Three things stuck with me.
>
> First, a steam turbine rotor is not designed, it is machined. A big alloy-steel forging goes
> through a fixed sequence of nineteen operations - on the centre lathe and the horizontal boring
> machine - the blades are locked into fir-tree grooves, shrouding is welded on, and it is
> balanced stage-wise before the casing closes over it. The largest machine in that plant is
> dedicated to first-job rotor balancing, and the reason is that imbalance force goes as the
> square of speed, so a small imbalance at low speed is a large force at full speed.
>
> Second, the drawing is only a third of the job. The process route is the second third and the
> inspection gate at every operation is the third. I watched the casing's horizontal joint get
> located by taper pins and then scraped against itself until the contact pattern came up even,
> before it went for hydrostatic test. That is a level of proof a drawing cannot give you.
>
> Third, the scale. I watched a twelve-metre-long job run in one setup on a 170 kilowatt heavy-duty
> CNC lathe, centre height 2100 mm, 4200 mm swing without the telescopic cover, and a 4.2 metre
> diameter job only fits with that cover off. No re-chucking, because re-chucking would cost you
> concentricity across twelve metres. I wrote down the tooling logic as well - solid, tipped and
> indexable inserts in roughly an eight to four to one ratio - because I wanted to understand why
> they choose one over another.
>
> What I took from it is that I now think of engineering as a chain from process plan to
> inspection gate, not as a drawing on a screen. And it is why I want heavy manufacturing rather
> than design-only work."

Note that this is longer than the memorised script, but it is the same argument. Say it in your own
words and it will sound like thinking rather than reciting.

---

## 7. If you blank out

**When you cannot remember a number.** Do not guess, and do not go silent. Say the thing you do
know, and use the shape of the thing you do not:

> "I do not remember the exact figure, but I remember it was a heavy-duty CNC lathe with a very
> large swing - over four metres - and the point of it was that you could machine a long job in
> one setup."

A specific shape plus a reason beats a wrong number every time. A panelist forgives "I do not
remember" completely; they do not forgive an invented figure, because an invented figure tells them
you will invent figures on a project.

**How to buy time.** Two moves, both legitimate:

- "That is a good question, let me take a second to get it right." Then think. Silence of three or
  four seconds reads as careful, not as lost.
- Repeat the question in your own words and answer the easy half first: "If I am understanding you
  right, you are asking about how I made sure the work was correct - so, the inspection gates..."
  You get thinking time and you look structured.

**How to say "I do not know" without it sounding fatal.** Say it cleanly, say what you would do, and
move on:

> "I do not know that one, and I would rather say so than guess. If it came up on the job, I would
> check the drawing, the standard or the process document rather than assume."

That answer is better than a wrong one, and it is what a graduate who is honest and trainable looks
like.

**The three sentences that always work, whatever is asked:**

1. "Let me make sure I answer the question you are actually asking."
2. "The part I am confident about is X; on the other part I would want to check my notes."
3. "That connects to what I saw at BHEL, and the link is..."

Those three buy you time, sound like thought, and never put you on the back foot.

---

## 8. One-page cheat sheet

Glance at this ten minutes before the interview. Nothing else.

**The frame (say once, then move to content):**
"It was a guided plant training visit at BHEL Hyderabad, in the Turbines, Compressors and Gas
Turbine division. I was given no design ownership - a technical run-down, and I kept four pages of
handwritten notes from the shop floor."

**The three observations, one line each:**
- A rotor is machined, not designed - nineteen fixed operations, stage-wise balancing, imbalance
  force goes as speed squared.
- The drawing is only a third of the job - the process route and the inspection gate are the rest.
- Scale and tooling - twelve metres in one setup on a 170 kW lathe; solid : tipped : indexable is
  roughly 8 : 4 : 1.

**Five numbers:**
19 operations | 8 : 4 : 1 tooling split | 170 kW main drive | 12000 mm between centres | 4200 mm
swing (4.2 m job)

**Three traps:**
1. Never say you worked on, designed, or were responsible for anything at BHEL.
2. Never call the handout your project - it was BHEL's own material, given to the batch.
3. Never say "it was a great learning experience" - say what you saw instead.

**If they push:** "Not design work, no. It was a guided visit. I wrote down every machine spec, the
tooling choices and the rotor sequence, and I asked the shop floor why things were done that
way." Then move on.

