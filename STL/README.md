This folder contains all STL files needed to 3D print the various parts of the PX-Rack.

The `Templates/` subfolder contains DXF files used as importable modules within the part designs. Where multiple parts require the exact same cut (side panels, top/bottom covers, and the switch bush), the cut was defined once as a DXF template and imported into each design for consistency, rather than being redrawn each time.

## FAQs ##

### What is STL? ###

In 3D printing, STL files are the most common file format used to describe 3D models. STL stands for STereoLithography (or sometimes Standard Triangle Language) and encodes the surface geometry of an object using triangular facets that slicing software can interpret. A slicing software is the tool that converts a 3D model (like an STL file) into layer-by-layer instructions (G-code) that a printer can understand and execute. 

### What is ABS? ###

ABS stands for Acrylonitrile Butadiene Styrene. It is a thermoplastic polymer widely used in 3D printing, especially with FDM (Fused Deposition Modeling) printers. Known for being strong, durable, and impact-resistant, ABS is the same material used in LEGO bricks, car dashboards, and protective housings.

The glass transition temperature of ABS is between 100 and 120 °C. Hence, it is best suited for components operating close to heat-generating parts in the PX-Rack.

### What is PETG? ### 

PETG stands for Polyethylene Terephthalate Glycol-modified. It is a thermoplastic derived from PET (the same plastic used in water bottles), with glycol added to improve durability and reduce brittleness. PETG combines the ease of printing of PLA with the strength and heat resistance of ABS, making it a versatile middle-ground filament.

The glass transition temperature of PETG is between 80 and 100 °C. While it can be used for external parts, it is not suitable for components operating in the vicinity of heat-generating elements in the PX-Rack.

### What is PLA? ###

PLA stands for Polylactic Acid. It is a biodegradable thermoplastic made from renewable resources such as corn starch or sugarcane. PLA is the most widely used filament in desktop 3D printing because it is easy to print, affordable, and environmentally friendly compared to petroleum-based plastics like ABS.

However, the glass transition temperature of PLA lies between 60 and 80 °C. As a result, a large number of PX-Rack components cannot be manufactured using PLA.

PLA should only be used for printing PX-Rack parts as a last resort when printing in PETG is not possible.

### What quality parameters should be used for 3D prints? ###

You can find these details in the README files located under /STL/ABS and /STL/PLA_PETG.
