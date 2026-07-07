## 2-Node PX-Rack — Assembly Steps

This guide sequences the build from the [parts list](README.md). Part quantities below assume a **2-Node** enclosure. Cross-check against the [renders](../img/2-Node.png) and the [4-Node build photos](../img/4-Node) (the 2-Node is the bottom half of a 4-Node) before final tightening, since this sequence is derived from the BOM and photos rather than a dimensioned drawing.

> ⚠️ Mains voltage work (IEC inlet, ATX PSU wiring) is involved. If you are not comfortable opening an ATX PSU or wiring an AC inlet, stop and have it done by someone qualified. Always work with PSUs unplugged and discharged.

### 0. Before you start
1. Print all parts per [STL/ABS/README.md](../STL/ABS/README.md) and [STL/PLA_PETG/README.md](../STL/PLA_PETG/README.md) print settings, and confirm counts against the [parts list](README.md).
2. Sort hardware into labeled trays: M4 T-nuts (150), M4/M3 bolts by length (10/12/16 mm — 20 each), M3 standoffs (30), M3 headless nuts (30), corner brackets (16), in-corner slot connectors (8).
3. Cut the 20×20 mm aluminium extrusions to length on the miter saw: six 350 mm, four 300 mm, four 200 mm. Deburr all cut ends.
4. Have your tool set ready: M2/M3/M4 screwdrivers and Allen keys, T2/T3/T4 Torx, soldering iron (for wiring safety net).

### 1. Build a frame using 20mm x 20mm extrusions
The frame has three extrusion positions front-to-back: **front** and **back** (the true corners) plus a **middle** position that sits between them. Looking at the rack from the left side: front is on the right, back is on the left, and the middle extrusions sit between the two — this is the mounting line for every module's back plate (MB-Mount-Back-Plate, HDD-Mount-Back-Plate, Power-Mount-Back-Plate).

1. Build two identical rectangles — one for the top, one for the bottom — each from two 300 mm extrusions (depth direction, front-to-back) and two 200 mm extrusions (width direction, left-to-right), joined at the four corners with **in-corner slot connectors**. These four corners are the front-left, front-right, back-left, and back-right positions.
2. Slide **M4 sliding T-nuts** into every extrusion channel that will receive a bolted part before you close up the frame — it's far easier to load them now than after the box is closed.
3. Stand the two rectangles apart and join front-left↔back-left and front-right↔back-right with four of the six 350 mm extrusions (the front and back verticals), using in-corner slot connectors. Reinforce all 8 corner joints with **corner brackets** (16 total, 2 per corner).
4. Fit the remaining two 350 mm extrusions as the **middle** verticals (left and right), positioned mid-span along the 300 mm depth rails — not at a corner. Secure each to the depth rails at top and bottom with a sliding T-nut and bracket. These are the back-plate mounting extrusions referenced in later steps.
5. The gap between the middle and back verticals is reserved for cable management (on the 4-Node build, this same slot also houses a vertically-mounted 1U switch — not applicable to the 2-Node's parts list).
6. Check the frame is square before fully tightening.

### 2. Attach the feet
1. Bolt the 4x **Foot.stl** parts to the underside corners of the bottom frame rectangle using M4 bolts into the T-nuts already in the channel.

> Note: Feet placement must align with the feet cutouts in the **Bottom-cover** — position them to match before final tightening, otherwise the bottom cover won't seat correctly in step 10.

### 3. Assemble the PSU mounting
Builds the standalone PSU-mount unit from **Power-Mount-Base**, **Power-Mount-Grill**, and **Power-Mount-PCB-Holder-Plate** (the PCB Holder is the tall slotted plate the harvested PSU PCBs will mount to in step 5; the Grill is the vented side panel; the Base is the flat tray both sit in).

1. Position the Grill and PCB-Holder-Plate together at the ridge where they meet, and seat both into the Power-Mount-Base.
2. Secure through the screw holes along the Base's lip with all nuts and bolts, and fully tighten.
3. Only once everything is bolted and tightened, pin stake / hot pin the Grill-to-PCB-Holder ridge (heat-staked plastic pins) as the final, permanent weld between the two parts.

### 4. ATX PSU dismantling
1. With both 400W ATX PSUs unplugged and discharged, open each case and remove the internal PCB from its metal shell. Keep each PSU's original screws/fan aside in case they're needed for the fan-mount in step 9.

### 5. Mount the harvested PCBs on the PCB Holder
1. Using the slotted holes on the PCB-Holder-Plate, mount each harvested PSU PCB with an M3 headless screw (12 mm), placing a 10 mm M3 spacer on both sides of the plate at each mounting point (spacer — PCB Holder — spacer). The slots allow the mounting position to be adjusted to match each PSU PCB's hole pattern.

### 6. Wire the power module and install it in the frame
1. Wire the AC power aggregation:
   - Terminate the IEC C14 10A inlet leads with the **push-fit lugs**.
   - Use the **LT-633** and **LT-933** quick-connect terminals to split/aggregate the inlet's Live and Neutral onto both PSUs' AC inputs in parallel, using the 3-core 1.5 mm² cable.
   - Route Earth to both PSU chassis grounds.
2. Fit the **Power-Mount-Back-Plate** to the frame's middle extrusion for this bay.
3. Secure the completed PSU-mount assembly (base + grill + PCB holder + PSUs) into the bottom bay of the frame, against the back plate.

### 7. Build each motherboard module (repeat ×2)
1. Fit M3 standoffs (female-to-female, 10 mm) into the **MB-Mounting-Plate** at the motherboard's standoff pattern, secured with M3 screws.
2. Mount the Mini-ITX motherboard onto the standoffs.
3. Attach the **MB-IO-Panel** over the board's I/O shield opening, at the front of the module — the motherboards are oriented I/O-out-front, not rear.
4. Mount the 2 push buttons for this node into the MB-IO-Panel using their push-button wire sets. Wiring these to the motherboard's front-panel power/reset headers is out of scope for this empty-enclosure build and is covered separately.
5. Fit the **MB-Mount-Back-Plate** behind the plate to close off and support the module.
6. Slide the completed module into its bay in the frame and bolt through the extrusion T-nuts.

### 8. Build each HDD module (repeat ×2)
1. Seat 2.5" drives into the **HDD-Mount**.
2. Close it out with the **HDD-Mount-Back-Plate**.
3. Mount the HDD module into the frame adjacent to its node's motherboard module, and wire SATA power/data to the corresponding motherboard.

### 9. Install fans
1. Fit the 4x **Fan-Cut-120** grills at the intake/exhaust cutouts — one pair (push-pull) for the node compartment, one pair for the power compartment.
2. The 2 PSU fans (built into the ATX PSUs) connect directly to each PSU's own fan pins — no separate wiring needed.
3. Mount the 2 additional 120mm fans behind the remaining grills, oriented for push-pull airflow with the PSU fans. These can be PWM or 12V fans, per user choice.
4. Power the 2 additional fans either from the motherboard's fan header (PWM or 12V, depending on fan type) or from a 12V PSU Molex connector — whichever the user prefers.

### 10. Cable dress and final checks
Do this before the back panels go on in step 11 — you need access to the wiring for this.

1. Route all internal wiring (PSU-to-motherboard, SATA, fan, push-button) along the frame rails, away from fan blades, and secure with the banding parts.
2. Double-check the AC wiring: continuity, no shorts to chassis, correct Live/Neutral/Earth landing on both PSUs.
3. Re-torque all M4/M3 fasteners and confirm the frame is still square.
4. Power on with no motherboards seated first (PSU + fans only) to confirm the aggregated AC wiring and fan wiring are correct before re-seating and powering the nodes.
5. Power on both nodes via the front push buttons and confirm boot.

### 11. Close up the panels and covers
1. Fit the **Left-Side-Panel-120mm-Fan-Power-Cut** on the side that carries the IEC inlet and power cutout.
2. Fit the 3x **Right-Side-Panel-120mm-Fan-Cut** panels on the remaining side positions (node bay ×2 sides + power bay).
3. Attach the 2x **Back-Cover** panels over the true rear of the enclosure — these are plain panels with no I/O or vent cutouts, since the motherboard I/O faces front.
4. Fit the **Bottom-cover** and **Top-Cover**.
5. Attach the 2x **Handel** (handle) parts to the top cover.
6. Fit the **25x265 Banding** strips (2x) as retention/cable-management banding across the relevant bay.
7. Close up and label the unit.

### Reference
- [Parts list / BOM](README.md)
- [STL — ABS print settings](../STL/ABS/README.md)
- [STL — PLA/PETG print settings](../STL/PLA_PETG/README.md)
- [2-Node render](../img/2-Node.png)
- [4-Node build photos](../img/4-Node) (2-Node = bottom half of this build)
