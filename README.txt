========================================================================
ENTERPRISE AI INFRASTRUCTURE SIZING TOOL
========================================================================
An interactive, high-performance web platform designed for AI systems engineers, 
data center architects, and infrastructure specialists to size, model, and plan 
accelerated computing clusters (compute, high-speed network fabric, thermal, 
power, and space requirements).

------------------------------------------------------------------------
TABLE OF CONTENTS
------------------------------------------------------------------------
1. Key Features
2. Quick Start / How to Run Locally
3. Usage Instructions
4. Project File Structure
5. Customizing Hardware & Network Presets

------------------------------------------------------------------------
1. KEY FEATURES
------------------------------------------------------------------------
- Dynamic Compute Node Sizing: Model clusters by total GPUs or exact server node counts.
- High-Speed Network Fabric Sizing: Supports InfiniBand (Quantum-2/Quantum-X800) and Ethernet (Spectrum-4/Spectrum-X).
- Live Topology Rendering: Visual interactive Fat-Tree, Leaf-Spine, and Storage fabric SVG diagrams that update dynamically based on node counts.
- Facility & Environmental Estimations: Real-time power load (kW/kVA), thermal cooling requirements (BTU/hr & CRAC/CRAH Tons), and rack space footprint.
- Spec Sheet & JSON Export: One-click export options for engineering documentation.
- Standalone HTML Architecture: Zero dependencies or build steps required.

------------------------------------------------------------------------
2. QUICK START / HOW TO RUN LOCALLY
------------------------------------------------------------------------

METHOD 1: Direct File Launch (Easiest)
  Simply double-click the `ai_infra_sizer.html` file to open and run it directly in any modern web browser (Chrome, Edge, Firefox, Safari). No installation or terminal commands required!

METHOD 2: Using a Local HTTP Server

  If using Python:
    $ python -m http.server 8000
    Open browser at: http://localhost:8000/ai_infra_sizer.html

  If using Node.js (npx serve):
    $ npx serve .
    Open browser at: http://localhost:3000/ai_infra_sizer.html

  If using VS Code Live Server Extension:
    Right-click `ai_infra_sizer.html` -> "Open with Live Server"

------------------------------------------------------------------------
3. USAGE INSTRUCTIONS
------------------------------------------------------------------------
1. Select System Preset: Choose a standard reference architecture (e.g., H100 8-GPU, H200 High-Memory, B200, GB200 NVL72, or Custom).
2. Set Node / Server Count: Type the exact number of server nodes or click quick-select buttons (e.g., 64, 128, 512 nodes).
3. Configure Network Fabric: Choose between InfiniBand or Ethernet fabrics, specify switch radix (32 to 144 ports), and select blocking ratios (1:1 Non-blocking vs 2:1 Oversubscribed).
4. Facility Inputs: Adjust Power Usage Effectiveness (PUE) ratio and rack power envelopes (max kW per rack).
5. Inspect Interactive Topology: Toggle between "Full Fat-Tree", "Rail Focus", and "Storage Fabric" views. Hover over switches/nodes to inspect active links.
6. Export: Click "Copy Spec Sheet" for plain-text technical specs, or "Export Config JSON" for machine-readable architecture data.

------------------------------------------------------------------------
4. PROJECT FILE STRUCTURE
------------------------------------------------------------------------
ai-sizer/
├── ai_infra_sizer.html   # Main Single-File Application (or index.html)
└── README.txt            # Application documentation

------------------------------------------------------------------------
5. CUSTOMIZING HARDWARE & NETWORK PRESETS
------------------------------------------------------------------------
You can customize hardware specs directly in `ai_infra_sizer.html` by modifying the `PRESET_NODES` and `FABRIC_TYPES` objects inside the `<script>` section.

========================================================================
