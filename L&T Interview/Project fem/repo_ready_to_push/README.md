# FEA-Sims-

Design iteration study on a cantilever bracket, in SolidWorks Simulation.

Three geometry variants (held as SolidWorks **configurations**), each analysed as its own study,
each one changed because of what the previous one showed me.

|  | Iteration 1 | Iteration 2 | Iteration 3 |
|---|---|---|---|
| Configuration | Parent Model | Supposedly child | Child Reborn |
| Geometry | solid box-section arm | lightening slots | triangulated truss arm |
| Mass | 406.23 kg | 321.07 kg | **269.82 kg** |
| Reaction force | 5,534 N | 4,699 N | **4,196 N** |
| Peak von Mises | 6.35 MPa | 26.77 MPa | **10.85 MPa** |
| Max tip deflection | 0.122 mm | 0.301 mm | **0.216 mm** |
| Mesh nodes / elements | 1.46 M / 0.94 M | 10.4 M / 6.9 M | 0.46 M / 0.24 M |
| Max aspect ratio | 4.34 | 40,657 | 9.29 |
| Time to mesh | 1 min 02 s | 44 min 51 s | 35 s |

**What the iterations actually showed**

1. **The parent was over-designed.** 6.35 MPa of stress against a 620 MPa yield is a factor of
   safety of 98. Most of that mass was not doing any work.
2. **Lightening slots backfired.** They removed 21% of the mass and raised peak stress 4.2x. The
   hot spot moved to the *end of the slot* - a stress concentration, because a slot end is a hole
   with a sharp end. The mesh on that model was also bad (aspect ratio 40,657, 6.9 M elements,
   45 min to mesh), so those numbers were not trustworthy either.
3. **Re-architecting the arm as a truss fixed it.** Moving the material out of the web and into
   the top and bottom chords, with a zig-zag of diagonals between them: peak stress down 2.4x
   from iteration 2, deflection down 28%, another 16% of the mass gone, and the hot spot moved
   back to the mount - which is where the bending moment peaks on a cantilever.

Final geometry: **33.6% lighter** than the parent, factor of safety **57** on yield, first natural
frequency **31.9 Hz** with 41.6% mass participation in the vertical.

**Load case (identical in all six studies):** fixed mounting face; 500 N normal force on 3 faces;
gravity 9.81 m/s2 on the body; 5 kg remote mass on 2 faces.
**Material:** Alloy Steel, linear elastic isotropic, E = 210 GPa, nu = 0.28, yield 620.4 MPa.

**Studies run:** Static Structural (x3 geometries) | Frequency (Modal) | Modal Time History
(base excitation) | Linear Dynamic (Harmonic).

**Known limitations of this study** (stated up front, because they are real): the load case is
dominated by the part's own weight, so the three geometries are not a perfectly clean structural
comparison - a common load case with gravity off would be needed for that; there is no mesh
convergence study, only mesh quality metrics; and this is simulation only, with no physical test.

**Plots:** `README_images/` - 01/04/07 are the three geometries, 02/05/08 the three stress plots,
03/06/09 the displacement plots, 10 the final mesh.
**Reports:** the six SolidWorks Simulation Word reports are in `reports/`.
