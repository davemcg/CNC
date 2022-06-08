# CNC

Machine: Sienci Longmill 30x30 Mk2

# Milling Checklist:

1. Secure workpiece
  - like *REALLY* well. If it is even sort of loose in some direction it will probably slide and cause havoc. 
3. Power on CNC, connect USB cable to computer, open gSender, and load grbl/nc code
4. Install bit (consider UNPLUGGING THE ROUTER for extra safety)
5. Move bit to XY start position (in relation to work piece and design)
6. **Zero XY axes**
7. Move Z axis far above work piece
8. Run "Outline" to ensure the bit is moving where you expect and won't strike any clamps / etc
9. Drop bit to right above work piece (use piece of paper)
10. **Zero Z** axis
11. Position dust shield
12. Ensure vacuum hose isn't tangled or encumbered 
13. **Are you wearing dust mask, eye and hearing protection?????**
14. Turn on router (is it plugged in now?)
15. Start program
16. Be ready to mash the "kill" button

# Fusion 360 Design / Manufacture Notes

- Measure work piece Z height with caliper
- Manufacture parameters to change:
  - Tool
    - [Param suggestions](https://resources.sienci.com/view/lmk2-feeds-and-speeds/)
    - Spindle speed
    - Cutting feedrate
    - Plunge feedrate
  - Geometry
    - Select contours (cut out) / pockets (cut everything within) / adaptive ("smarter" cut everything within?)
    - Add tabs if necesary. Don't skimp.
    - Suggest "adaptive" 2D/3D clearing as it appears (as of 2022-06) to do a better job at removing the right amount of material (was runnning into some issues where a 3D pocket clearing wasn't taking enough material for a box joint)
  - Heights
    - Make certain "Bottom Height" is "Stock bottom"
  - Passes
    - **SELECT "Multiple Depths"** 
    - Change "Maximum Roughing Stepdown" to 1-4mm, depending on [this](https://resources.sienci.com/view/lmk2-feeds-and-speeds/)
  - Export gcode (as .nc) by right clicking on the setup and selecting "Post process" 
    - Set the bit retract height to the Fusion 360 retract height as the bit can plunge into the material if something is wonky about the G28 (?) param. 

# Machining notes

1. Get bit at the zero position (XYZ). Drill (manually) through the base material. Now you have (one) reference point on both sides. Remember to machine the other side you will have to flip the origin to the other X dimension
2. Consider two points (can manually jog the bit up X/Y) for better precision
3. Resist the urge to skip the dust shoe. Everything makes a lot of mess. 
4. If you are doing an outside cut on thick (Z) material, place some blocking wood to semi-contain the wood bits that will be flung away
5. Remember, if you use a ball noise bit on a flat cut, it will have annoying grooves

