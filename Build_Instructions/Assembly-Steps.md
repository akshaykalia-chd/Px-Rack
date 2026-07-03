## 2-Node PX-Rack — Assembly Steps

This guide sequences the build from the [parts list](README.md). Part quantities below assume a **2-Node** enclosure. Cross-check against the [renders](../img/2-Node.png) and the [4-Node build photos](../img/4-Node) (the 2-Node is the bottom half of a 4-Node) before final tightening, since this sequence is derived from the BOM and photos rather than a dimensioned drawing.

> ⚠️ Mains voltage work (IEC inlet, ATX PSU wiring) is involved. If you are not comfortable opening an ATX PSU or wiring an AC inlet, stop and have it done by someone qualified. Always work with PSUs unplugged and discharged.

### 0. Before you start
1. Print all parts per [STL/ABS/README.md](../STL/ABS/README.md) and [STL/PLA_PETG/README.md](../STL/PLA_PETG/README.md) print settings, and confirm counts against the [parts list](README.md).
2. Sort hardware into labeled trays: M4 T-nuts (150), M4/M3 bolts by length (10/12/16 mm — 20 each), M3 standoffs (30), M3 headless nuts (30), corner brackets (16), in-corner slot connectors (8).
3. Cut the 20×20 mm aluminium extrusions to length on the miter saw: six 350 mm, four 300 mm, four 200 mm. Deburr all cut ends.
4. Have your tool set ready: M2/M3/M4 screwdrivers and Allen keys, T2/T3/T4 Torx, soldering iron (for wiring safety net).

### 1. Build the outer frame
The frame has three extrusion positions front-to-back: **front** and **back** (the true corners) plus a **middle** position that sits between them. Looking at the rack from the left side: front is on the right, back is on the left, and the middle extrusions sit between the two — this is the mounting line for every module's back plate (MB-Mount-Back-Plate, HDD-Mount-Back-Plate, Power-Mount-Back-Plate).

1. Build two identical rectangles — one for the top, one for the bottom — each from two 300 mm extrusions (depth direction, front-to-back) and two 200 mm extrusions (width direction, left-to-right), joined at the four corners with **in-corner slot connectors**. These four corners are the front-left, front-right, back-left, and back-right positions.
2. Slide **M4 sliding T-nuts** into every extrusion channel that will receive a bolted part before you close up the frame — it's far easier to load them now than after the box is closed.
3. Stand the two rectangles apart and join front-left↔back-left and front-right↔back-right with four of the six 350 mm extrusions (the front and back verticals), using in-corner slot connectors. Reinforce all 8 corner joints with **corner brackets** (16 total, 2 per corner).
4. Fit the remaining two 350 mm extrusions as the **middle** verticals (left and right), positioned mid-span along the 300 mm depth rails — not at a corner. Secure each to the depth rails at top and bottom with a sliding T-nut and bracket. These are the back-plate mounting extrusions referenced in steps 3–5.
5. Check the frame is square before fully tightening.

### 2. Attach the feet
1. Bolt the 4x **Foot.stl** parts to the underside corners of the bottom frame rectangle using M4 bolts into the T-nuts already in the channel.

### 3. Build the power module
1. Assemble the power bay shell: **Power-Mount-Base**, **Power-Mount-Back-Plate**, and **Power-Mount-Grill**.
2. Open both ATX PSUs and remove the internal PCB from each shell.
3. Mount both PSU PCBs onto the **Power-Mount-PCB-Holder-Plate** using M3 standoffs (female-to-female, 10 mm), secured with M3 headless nuts (12 mm) — this one plate holds both PSUs.
4. Secure the loaded PCB-Holder-Plate into the Power-Mount-Base.
5. Wire the AC power aggregation ahead of final panel closure:
   - Terminate the IEC C14 10A inlet leads with the **push-fit lugs**.
   - Use the **LT-633** and **LT-933** quick-connect terminals to split/aggregate the inlet's Live and Neutral onto both PSUs' AC inputs in parallel, using the 3-core 1.5 mm² cable.
   - Route Earth to both PSU chassis grounds.
6. Mount the Power-Mount-Grill over the PSU intake and secure the assembly into the bottom bay of the frame.

### 4. Build each motherboard module (repeat ×2)
1. Fit M3 standoffs (female-to-female, 10 mm) into the **MB-Mounting-Plate** at the motherboard's standoff pattern, secured with M3 screws.
2. Mount the Mini-ITX motherboard onto the standoffs.
3. Attach the **MB-IO-Panel** over the board's rear I/O shield opening.
4. Mount the 2 push buttons for this node into the MB-IO-Panel using their push-button wire sets. Wiring these to the motherboard's front-panel power/reset headers is out of scope for this empty-enclosure build and is covered separately.
5. Fit the **MB-Mount-Back-Plate** behind the plate to close off and support the module.
6. Slide the completed module into its bay in the frame and bolt through the extrusion T-nuts.

### 5. Build each HDD module (repeat ×2)
1. Seat 2.5" drives into the **HDD-Mount**.
2. Close it out with the **HDD-Mount-Back-Plate**.
3. Mount the HDD module into the frame adjacent to its node's motherboard module, and wire SATA power/data to the corresponding motherboard.

### 6. Install fans
1. Fit the 4x **Fan-Cut-120** grills at the intake/exhaust cutouts — one pair (push-pull) for the node compartment, one pair for the power compartment.
2. Mount the 2 additional 120mm fans (beyond the 2 built into the ATX PSUs) behind these grills, oriented for push-pull airflow with the PSU fans.
3. Wire fans to PSU fan headers or a dedicated fan power tap.

### 7. Close up the panels and covers
1. Fit the **Left-Side-Panel-120mm-Fan-Power-Cut** on the side that carries the IEC inlet and power cutout.
2. Fit the 3x **Right-Side-Panel-120mm-Fan-Cut** panels on the remaining side positions (node bay ×2 sides + power bay).
3. Attach the 2x **Back-Cover** panels over the rear/IO side.
4. Fit the **Bottom-cover** and **Top-Cover**.
5. Attach the 2x **Handel** (handle) parts to the top cover.
6. Fit the **25x265 Banding** strips (2x) as retention/cable-management banding across the relevant bay.

### 8. Cable dress and final checks
1. Route all internal wiring (PSU-to-motherboard, SATA, fan, push-button) along the frame rails, away from fan blades, and secure with the banding parts.
2. Double-check the AC wiring: continuity, no shorts to chassis, correct Live/Neutral/Earth landing on both PSUs.
3. Re-torque all M4/M3 fasteners and confirm the frame is still square.
4. Power on with no motherboards seated first (PSU + fans only) to confirm the aggregated AC wiring and fan wiring are correct before re-seating and powering the nodes.
5. Power on both nodes via the front push buttons and confirm boot, then close and label the unit.

### Reference
- [Parts list / BOM](README.md)
- [STL — ABS print settings](../STL/ABS/README.md)
- [STL — PLA/PETG print settings](../STL/PLA_PETG/README.md)
- [2-Node render](../img/2-Node.png)
- [4-Node build photos](../img/4-Node) (2-Node = bottom half of this build)
