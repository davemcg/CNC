# CNC

Machine: Sienci Longmill 30x30 Mk2

# Milling Checklist:

1. Secure workpiece
    - like *REALLY* well. If it is even sort of loose in some direction it will probably slide and cause havoc. 
2. Power on CNC, connect USB cable to computer, open gSender, and load grbl/nc code
3. Install bit (consider UNPLUGGING THE ROUTER for extra safety)
4. Move bit to XY start position (in relation to work piece and design)
5. **Zero XY axes**
6. Move Z axis far above work piece
7. Run "Outline" to ensure the bit is moving where you expect and won't strike any clamps / etc
8. Drop bit to right above work piece (use piece of paper)
9. **Zero Z** axis
10. Position dust shoe
11. Ensure vacuum hose isn't tangled or encumbered 
12. **Are you wearing dust mask, eye and hearing protection?????**
13. Turn on router 
14. Start program
15. Be ready to mash the "kill" button

# Fusion 360 Design / Manufacture Notes

- Measure work piece Z height with caliper
- Lay out as follows <img width="211" alt="Screenshot 2025-05-10 at 9 49 52 PM" src="https://github.com/user-attachments/assets/b9b8db5b-e74a-4b73-86e0-e7e58514897a" /> (bottom is towards garage door).
- Multiply body (Modify -> Scale) * 1.015 for Y axis to meet reality. Still have to verify X axis.
- Set origin (usually) to the top of the material to cut!
- Add extra stock around the model (otherwise tabs are not possible)
- Manufacture parameters to change:
  - Tool
    - [Param suggestions](https://resources.sienci.com/view/lmk2-feeds-and-speeds/)
    - Spindle speed
    - Cutting feedrate
    - Plunge feedrate
  - Geometry
    - Select contours (cut out) / pockets (cut everything within) / adaptive ("smarter" cut everything within?)
    - Select the *bottom* of the material for contour selection. You may have to mix and match face and chain contours.
    - Add tabs if necesary. Avoid tabs on curves.
    - Suggest "adaptive" 2D/3D clearing as it appears (as of 2022-06) to do a better job at removing the right amount of material (was runnning into some issues where a 3D pocket clearing wasn't taking enough material for a box joint)
    - Run Simulate to ensure nothing wacky is happening
  - Heights
    - **If** you selected the top of the model for contour selection, make certain "Bottom Height" is "Stock bottom"
  - Passes
    - **SELECT "Multiple Depths"** 
    - Change "Maximum Roughing Stepdown" to 1-4mm, depending on [this](https://resources.sienci.com/view/lmk2-feeds-and-speeds/)
  - Remove Lead-In and Lead-Out if the bit is striking the material
  - Export gcode (as .nc) by right clicking on the setup and selecting "Post process" 
    - Set the bit retract height to the Fusion 360 retract height as the bit can plunge into the material if something is wonky about the G28 (?) param. 

# Machining notes

1. Get bit at the zero position (XYZ). Drill (manually) through the base material. Now you have (one) reference point on both sides. Remember to machine the other side you will have to flip the origin to the other X dimension
2. Consider two points (can manually jog the bit up X/Y) for better precision
3. If you are doing an outside cut on thick (Z) material, place some blocking wood to semi-contain the wood bits that will be flung away
4. Remember, if you use a ball noise bit on a flat cut, it will have annoying grooves

