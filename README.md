# CNC

Machine: Sienci Longmill 30x30 Mk2

# Milling Checklist:

1. Secure workpiece
2. Power on CNC, connect USB cable to computer, open gSender, and load grbl/nc code
3. Install bit
4. Move bit to XY start position (in relation to work piece and design)
5. **Zero XY axes**
6. Move Z axis far above work piece
7. Run "Outline" to ensure the bit is moving where you expect and won't strike any clamps / etc
8. Drop bit to right above work piece (use piece of paper)
9. **Zero Z** axis
10. Position dust shield
11. Ensure vacuum hose isn't tangled or encumbered 
12. **Are you wearing dust mask, eye and hearing protection?????**
13. Turn on router
14. Start program

# Fusion 360 Design / Manufacture Notes

- Measure work piece Z height with caliper
- Manufacture parameters to change:
  - Tool
    - [Param suggestions](https://resources.sienci.com/view/lmk2-feeds-and-speeds/)
    - Spindle speed
    - Cutting feedrate
    - Plunge feedrate
  - Geometry
    - Select contours (cut out) / pockets (cut everything within)
    - Add tabs (increase distance as Fusion 360 loves tabs)
  - Heights
    - Make certain "Bottom Height" is "Stock bottom"
  - Passes
    - **SELECT "Multiple Depths"** 
    - Change "Maximum Roughing Stepdown" to 1-4mm, depending on [this](https://resources.sienci.com/view/lmk2-feeds-and-speeds/)
  - Export gcode (as .nc) by right clicking on the setup and selecting "Post process" 
